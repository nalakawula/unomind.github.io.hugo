---
title: 
date: 2017-04-14T19:39:08+07:00
showDate: true
draft: false
tags: ["blog"]
---
Hari ini, saya ingin menaruh gambar dalam artikel dengan tampilan seperti ini:
![gambar+caption]({{ site.baseurl }}/assets/img/image-caption.png)

Saya, tidak tahu cara yang "benar" dalam jekyll, sehingga saya membuatnya seperti ini:
```markdown
![utilman.png]({{ site.baseurl }}/assets/img/utilman.png)
Gambar 1: utilman.exe (https://www.online-tech-tips.com/)
{: style="color:gray; font-size: 80%; text-align: center;"}
```

Profit, hasilnya dapat dilihat [disini]({{ site.baseurl }}{% post_url 2017-10-24-mudah-bypass-password-windows-10 %})

Referensi: [https://stackoverflow.com/questions/28294959/jekyll-kramdown-how-to-center-text](https://stackoverflow.com/questions/28294959/jekyll-kramdown-how-to-center-text)