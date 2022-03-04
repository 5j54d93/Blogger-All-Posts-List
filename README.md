# Blogger All Post List

Fetch data from Google Blogger API to list all posts of a blog by time.

> Demo page：[**sharing-life-in-tw.blogspot.com/p/all-posts.html**](https://sharing-life-in-tw.blogspot.com/p/all-posts.html)

## URL

```js
var feedUrl = 'https://sharing-life-in-tw.blogspot.com/feeds/posts/default?max-results=9999&amp;alt=json-in-script&amp;callback=myFunc';
```

You could change `sharing-life-in-tw.blogspot.com` to your Blogger url.

## Separate Posts by Month

```js
if(entries[i].published.$t.substr(0,7) != date) {
  html.push(' <a class="day-blue night fs-4 lh-lg" href="https://sharing-life-in-tw.blogspot.com/');
  html.push(entries[i].published.$t.substr(0,4));
  html.push('/');
  html.push(entries[i].published.$t.substr(5,2));
  html.push('/" style="text-decoration:none;" >');
  html.push(entries[i].published.$t.substr(0,4));
  html.push(' 年 ');
  html.push(entries[i].published.$t.substr(5,2));
  html.push(' 月');
  html.push('<'+'/a>');
  html.push('<'+'br />');
  date = entries[i].published.$t.substr(0,7);
}
```

## Display Posts by List

```js
html.push('<'+'li>')
html.push(entries[i].published.$t.substr(5,2));
html.push('/');
html.push(entries[i].published.$t.substr(8,2));
html.push('： <a class="day-blue night lh-base" href="');
html.push(entries[i].link[4].href);
html.push('" style="text-decoration:none;" >');
html.push(entries[i].title.$t);
html.push('<'+'/a>');
html.push('<'+'/li>');
```
