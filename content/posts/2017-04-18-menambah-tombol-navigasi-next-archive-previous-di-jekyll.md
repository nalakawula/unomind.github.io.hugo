---
title: 
date: 2017-04-14T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Beberapa hari ini, saya mainan *static site* dengan memanfaatkan jekyll dan gh-page.

Nah hari ini, setelah saya lihat-lihat *static site* saya ada yang kurang. Dulu pas main wordpress ada yang namanya *next post* sama *previous post*.

Oleh karena itu, hari ini saya menambahkan fitur itu.

## Check this out
1. edit `_layouts/post.html` . Tambahkan sebelum `</article>` biar lokasinya ada dibawah konten utama:
    {% raw %}
    ```html
    <div class="PageNavigation">
      {% if page.previous.url %}
      <a class="prev" href="{{page.previous.url}}"> « {{page.previous.title}}</a>
      {% endif %}

      {% if page.next.url %}
        <a class="next" href="{{page.next.url}}"> {{page.next.title}} »</a>
      {% endif %}
    </div>
    ```
    {% endraw %}

2. edit `css` . Tambahkan:
    {% raw %}
    ```css
     .PageNavigation {
      font-size: 16px;
      display: block;
      width: auto;
      overflow: hidden;
      }

    .PageNavigation a {
      display: block;
      width: 50%;
      float: left;
      margin: 1em 0;
      }

    .PageNavigation .next {
      text-align: right;
      }
    ```
    {% endraw %}

Selesai
<hr>
