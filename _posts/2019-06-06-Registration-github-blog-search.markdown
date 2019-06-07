---
layout: post
title:  "Github blog를 검색이 되게 설정하기 ..작성중"
date:   2019-06-06 13:07:45
author: atomic0x90 (Yujun Han)
categories: Jekyll
tags:  Jekyll
sitemap :
  changefreq : daily
  priority : 1.0
cover:  "/assets/instacode.png"
---

github를 이용하여 새로운 블로그를 만들면 포털 사이트에 내 페이지가 검색이 안된다. 
그래서 직접 각 포털 사이트에 내 페이지가 검색이 가능하도록 등록을 해야 한다.

---

## 1. sitemap 만들기

* **플러그인 이용하기**

저는 jekyll theme를 **Centrarium**을 사용했습니다. 
즉 ruby를 사용하여 jekyll page를 만들었습니다.  
저와 같이 ruby를 이용하여 만드신 분들은 
```bash
sudo gem install jekyll-sitemap
```

다음과 같은 명령어를 입력해서 플러그인을 설치하고 
블로그 /root 경로에 있는 **_config.yml** 에 다음과 같이 추가하면 자동으로 sitemap이 생성됩니다.

```
gems:
  - jekyll-sitemap
```

* **직접 sitemap 파일 만들기**

`반드시 블로그 /root 경로에 sitemap.xml 파일을 만든다.`  
**sitemap.xml** 에 다음 전체 내용을 그대로 복사하고 저장한다.  
하위 폴더에 **sitemap.xml** 을 절대로 만들지 않는다.

```
---
layout: null
---
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.sitemaps.org/schemas/sitemap/0.9 http://www.sitemaps.org/schemas/sitemap/0.9/sitemap.xsd" xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
{% raw %}  {% for post in site.posts %} {% endraw %}
    <url>
      <loc>{% raw %}{{ site.url }}{{ post.url }}{% endraw %}</loc>
      {% raw %}{% if post.lastmod == null %}{% endraw %}
        <lastmod>{% raw %}{{ post.date | date_to_xmlschema }}{% endraw %}</lastmod>
      {% raw %}{% else %}{% endraw %}
        <lastmod>{% raw %}{{ post.lastmod | date_to_xmlschema }}{% endraw %}</lastmod>
      {% raw %}{% endif %}{% endraw %}

      {% raw %}{% if post.sitemap.changefreq == null %}{% endraw %}
        <changefreq>weekly</changefreq>
      {% raw %}{% else %}{% endraw %}
        <changefreq>{% raw %}{{ post.sitemap.changefreq }}{% endraw %}</changefreq>
      {% raw %}{% endif %}{% endraw %}

      {% raw %}{% if post.sitemap.priority == null %}{% endraw %}
          <priority>0.5</priority>
      {% raw %}{% else %}{% endraw %}
        <priority>{% raw %}{{ post.sitemap.priority }}{% endraw %}</priority>
      {% raw %}{% endif %}{% endraw %}

    </url>
  {% raw %}{% endfor %}{% endraw %}
</urlset>
```

플러그인을 이용하거나 직접 sitemap 파일을 만들었으면 git에 commit, push를 해서 블로그를 업데이트를 한다. 
블로그 주소/sitemap.xml으로 접속했을 때 다음과 같은 화면이 나오면 정상적으로 sitemap이 등록된 것이다.

<img src="{{site.baseurl}}/assets/post_img/Registration-github-blog-search-sitemap_img01.png" alt="sitemap.xml img" title="my sitemap.xml img">

그리고 post를 작성할 때 changefreq를 다음과 같이 작성한다. changefreq의 주기는 하루 또는 일주일로 한다. 
```
---
layout: post
title:  "post title"
date:   2019-06-06 13:07:45
author: atomic0x90 (Yujun Han)
sitemap :
  changefreq : daily
  priority : 1.0
---
```
* **주의해야 할 점**  
한글이 들어가는 파일의 이름일 경우 URL 주소에 **%** 기호가 들어간다. 이러면 xml이 정상적으로 작동하기 힘들다. 
**따라서 URL으로 쓰이게 되는 파일 이름은 되도록 영문으로 만들고 특수문자 사용도 자제하는 게 좋다.**



---

## 2. RSS feed 만들기

`반드시 블로그 /root 경로에 feed.xml 파일을 만든다.` feed.xml 파일에 다음 전체 내용을 그대로 복사하고 저장한다.

```
---
layout: null
---
<?xml version="1.0" encoding="UTF-8"?>
<rss version="2.0" xmlns:atom="http://www.w3.org/2005/Atom">
  <channel>
    <title>{% raw %}{{ site.title | xml_escape }}{% endraw %}</title>
    <description>{% raw %}{{ site.description | xml_escape }}{% endraw %}</description>
    <link>{% raw %}{{ site.url }}{% endraw %}{% raw %}{{ site.baseurl }}{% endraw %}/</link>
    <atom:link href="{% raw %}{{ "/feed.xml" | prepend: site.baseurl | prepend: site.url }}{% endraw %}" rel="self" type="application/rss+xml"/>
    <pubDate>{% raw %}{{ site.time | date_to_rfc822 }}{% endraw %}</pubDate>
    <lastBuildDate>{% raw %}{{ site.time | date_to_rfc822 }}{% endraw %}</lastBuildDate>
    <generator>Jekyll v{% raw %}{{ jekyll.version }}{% endraw %}</generator>
    {% raw %}{% for post in site.posts limit:30 %}{% endraw %}
      <item>
        <title>{% raw %}{{ post.title | xml_escape }}{% endraw %}</title>
        <description>{% raw %}{{ post.content | xml_escape }}{% endraw %}</description>
        <pubDate>{% raw %}{{ post.date | date_to_rfc822 }}{% endraw %}</pubDate>
        <link>{% raw %}{{ post.url | prepend: site.baseurl | prepend: site.url }}{% endraw %}</link>
        <guid isPermaLink="true">{% raw %}{{ post.url | prepend: site.baseurl | prepend: site.url }}{% endraw %}</guid>
        {% raw %}{% for tag in post.tags %}{% endraw %}
        <category>{% raw %}{{ tag | xml_escape }}{% endraw %}</category>
        {% raw %}{% endfor %}{% endraw %}
        {% raw %}{% for cat in post.categories %}{% endraw %}
        <category>{% raw %}{{ cat | xml_escape }}{% endraw %}</category>
        {% raw %}{% endfor %}{% endraw %}
      </item>
    {% raw %}{% endfor %}{% endraw %}
  </channel>
</rss>
```











