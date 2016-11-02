---
title: 'Implementasi Asynchronous pada Feed Reader (C#)'
author: Saiful
layout: post
date: 2015-05-29T14:05:08+00:00
slug: implementasi-asynchronous-pada-feed-reader-c
category:
  - Microsoft Ecosystem

---
Kemarin, saya share mengenai [teknik pemrograman asynchronous pada C# menggunakan `await` dan `async`][1]. Sekarang, saya akan coba kasih contoh nyata dari kode program [POLBAN News Reader][2] yang saya buat. 🙂

Jadi, pada aplikasi saya ada sebuah class bernama `FeedDataSource` yang berfungsi menampung daftar item dari RSS website POLBAN dan mengambil item-item tersebut. Daftar item ditampung pada sebuah properti `Feeds` seperti berikut:

```
private ObservableCollection<FeedItem> _Feeds = new ObservableCollection<FeedItem>();
public ObservableCollection<FeedItem> Feeds
{
    get { return _Feeds; }
}
```

<!--more-->

`ObservableCollection` digunakan agar objek yang di-bind dengan Collection tersebut (misalnya, ListItem) bisa langsung di-refresh ketika ada perubahan pada isi dari `ObservableCollection`. Pada kode di atas, `FeedItem` adalah sebuah class sederhana yang menstrukturkan isi dari sebuah item RSS feed.

```
public class FeedItem
{
    public string Title { get; set; }
    public string Author { get; set; }
    public string Content { get; set; }
    public DateTime PubDate { get; set; }
    public Uri Link { get; set; }
}
```

Nah, di mana asynchronous-nya? Coba lihat method berikut:

```
public async Task GetFeedsAsync()
{
    SyndicationClient client = new SyndicationClient();
    Uri feedUri = new Uri("http://www.polban.ac.id/index.php?format=feed&type=rss");

    try
    {
        SyndicationFeed feed = await client.RetrieveFeedAsync(feedUri);

        if (feed.Items != null && feed.Items.Count &gt; 0)
        {
            foreach (SyndicationItem item in feed.Items)
            {
                FeedItem feedItem = new FeedItem();

                if (item.Title != null && item.Title.Text != null) {
                    feedItem.Title = item.Title.Text;
                }

                if (item.Authors != null && item.Authors.Count > 0) {
                    feedItem.Author = item.Authors[0].Name.ToString();
                }

                if (item.Summary != null && item.Summary.Text != null) {
                    feedItem.Content = item.Summary.Text;
                }

                if (item.PublishedDate != null) {
                    feedItem.PubDate = item.PublishedDate.DateTime;
                }

                if (item.Links != null && item.Links.Count > 0) {
                    feedItem.Link = item.Links[0].Uri;
                }

                _Feeds.Add(feedItem);
            }
        }
    }
    catch (Exception)
    {
        // do nothing (bad practice hehehe)
    }
}
```

Nah, itu dia asynchronous method-nya. Jadi `GetFeedsAsync()` akan mengambil data dari website POLBAN secara asynchronous. Setelah data diperoleh, maka setiap item dari RSS yang sudah diambil dibuatkan sebuah class `FeedItem` dan dimasukkan ke dalam `ObservableCollection` yang sudah didefinisikan di awal.

Any questions? 😀

 [1]: http://saiful.web.id/2015/05/asynchronous-await-async-c/
 [2]: https://github.com/saifulwebid/polban-news-reader/
