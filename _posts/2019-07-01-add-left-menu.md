---
layout: post
title: "Add customizing menu at left menu bar"
date: 2019-07-01
excerpt: "Examples and code for adding customizing menu at lefe menu bar."
tags: [sample post, add, menu, customizing]
comments: true
---

Leni say
> 좌측의 메뉴바는 `_includes/nav.html` 을 수정하여 만들 수 있습니다. <br>
>  모든 페이지의 메뉴바가 수정되어 나타납니다.

<br>

1. 소스를 해석해 볼까요?
  - 저는 Jekyll 이나 HTML, CSS 등의 문법은 잘 모르기 때문에 세세하게 해석하지 않습니다.
  - 큰 단락 별로 분류만 하도록 하겠습니다.


{% highlight html %}
```
<nav id="dl-menu" class="dl-menuwrapper" role="navigation">
  <button class="dl-trigger">Open Menu</button>
  <!-- 여기서 부터 메뉴바의 설정이 시작 됩니다 -->
  <ul class="dl-menu">
    <!-- 좌측 상단 메뉴의 `Home`을 눌렀을 때 동작하는 부분입니다 -->
    <li><a href="{{ site.url }}/">Home</a></li>
    <li>
      <!-- 좌측 상단 메뉴의 `About`을 눌렀을 때 동작하는 부분입니다 -->
      <a href="#">About</a>
      <ul class="dl-submenu">
        <li>
          <img src="{{ site.url }}/{{ site.logo }}" alt="{{ site.title }} photo" class="author-photo">
          <h4>{{ site.title }}</h4>
          <p>{{ site.description }}</p>
        </li>
        <!-- 좌측 상단 메뉴의 `About` 속에 `Learn More`을 눌렀을 때 동작하는 부분입니다. -->
        <li><a href="{{ site.url }}/about/"><span class="btn btn-inverse">Learn More</span></a></li>
                  <!-- 좌측 상단 메뉴의 `About`속에 연락수단으로 등록되는 부분입니다. -->
        {% if site.email %}<li>
                      <a href="mailto:{{ site.email }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-envelope-square"></i> Email</a>
                  </li>{% endif %}
                  {% if site.twitter %}<li>
                      <a href="http://twitter.com/{{ site.twitter }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-twitter-square"></i> Twitter</a>
                  </li>{% endif %}
                  {% if site.facebook %}<li>
                      <a href="http://facebook.com/{{ site.facebook }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-facebook-square"></i> Facebook</a>
                  </li>{% endif %}
                  {% if site.google.plus %}<li>
                      <a href="http://plus.google.com/+{{ site.google.plus }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-google-plus-square"></i> Google+</a>
                  </li>{% endif %}
                  {% if site.linkedin %}<li>
                      <a href="http://linkedin.com/in/{{ site.linkedin }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-linkedin-square"></i> LinkedIn</a>
                  </li>{% endif %}
                  {% if site.xing %}<li>
                      <a href="http://www.xing.com/profile/{{ site.xing }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-xing-square"></i> Xing</a>
                  </li>{% endif %}
                  {% if site.instagram %}<li>
                      <a href="http://instagram.com/{{ site.instagram }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-instagram"></i> Instagram</a>
                  </li>{% endif %}
                  {% if site.tumblr %}<li>
                      <a href="http://{{ site.tumblr }}.tumblr.com" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-tumblr-square"></i> Tumblr</a>
                  </li>{% endif %}
                  {% if site.github-url %}<li>
                      <a href="http://github.com/{{ site.github-url }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-github"></i> Github</a>
                  </li>{% endif %}
                  {% if site.stackoverflow %}<li>
                      <a href="http://stackoverflow.com/users/{{ site.stackoverflow }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-stack-overflow"></i> StackOverflow</a>
                  </li>{% endif %}
                  {% if site.lastfm %}<li>
                      <a href="http://lastfm.com/user/{{ site.lastfm }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-music"></i> LastFm</a>
                  </li>{% endif %}
                  {% if site.dribbble %}<li>
                      <a href="http://dribbble.com/{{ site.dribbble }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-dribbble"></i> Dribble</a>
                  </li>{% endif %}
                  {% if site.pinterest %}<li>
                      <a href="http://www.pinterest.com/{{ site.pinterest }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-pinterest"></i> Pinterest</a>
                  </li>{% endif %}
                  {% if site.foursquare %}<li>
                      <a href="http://foursquare.com/{{ site.foursquare }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-foursquare"></i> Foursquare</a>
                  </li>{% endif %}
                  {% if site.steam %}<li>
                      <a href="http://steamcommunity.com/id/{{ site.steam }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-steam-square"></i> Steam</a>
                  </li>{% endif %}
                  {% if site.youtube %}<li>
                      <a href="https://youtube.com/user/{{ site.youtube }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-youtube-square"></i> Youtube</a>
                  </li>{% endif %}
                  {% if site.youtube-channel %}<li>
                      <a href="https://youtube.com/channel/{{ site.youtube-channel }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-youtube"></i> Youtube</a>
                  </li>{% endif %}
                  {% if site.soundcloud %}<li>
                      <a href="http://soundcloud.com/{{ site.soundcloud }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-soundcloud"></i> SoundCloud</a>
                  </li>{% endif %}
                  {% if site.weibo %}<li>
                      <a href="http://www.weibo.com/{{ site.weibo }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-weibo"></i> Weibo</a>
                  </li>{% endif %}
                  {% if site.flickr %}<li>
                      <a href="http://www.flickr.com/{{ site.flickr }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-flickr"></i> Flickr</a>
                  </li>{% endif %}
                  {% if site.codepen %}<li>
                      <a href="http://codepen.io/{{ site.codepen }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-codepen"></i> Codepen</a>
                  </li>{% endif %}
                  {% if site.keybase %}<li>
                      <a href="https://keybase.io/{{ site.keybase }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-key"></i> Keybase</a>
                  </li>{% endif %}
                  {% if site.xmpp %}<li>
                      <a href="xmpp:{{ site.xmpp }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-lightbulb-o"></i> XMPP</a>
                  </li>{% endif %}
                  {% if site.hackernews %}<li>
                      <a href="https://news.ycombinator.com/user?id={{ site.hackernews }}" target="_blank" rel="noopener noreferrer"><i class="fa fa-fw fa-hacker-news"></i> Hacker News</a>
                  </li>{% endif %}
      </ul><!-- /.dl-submenu -->
    </li>
    <li>
      <!-- 좌측 상단 메뉴의 `Posts`을 눌렀을 때 동작하는 부분입니다. -->
      <a href="#">Posts</a>
      <ul class="dl-submenu">
        <li><a href="{{ site.url }}/posts/">All Posts</a></li>
        <li><a href="{{ site.url }}/tags/">All Tags</a></li>
      </ul>
    </li>
    <!-- ★ ☆ ★ ☆ 여기 ★ ☆ ★ ☆ -->
    {% for link in site.data.navigation %}
      {% if link.url contains 'http' %}
          {% assign domain = '' %}
          {% else %}
          {% assign domain = site.url %}
      {% endif %}
      <li><a href="{{ domain }}{{ link.url }}" {% if link.url contains 'http' %}target="_blank" rel="noopener noreferrer"{% endif %}>{{ link.title }}</a></li>
    {% endfor %}
  </ul><!-- /.dl-menu -->
</nav><!-- /.dl-menuwrapper -->
```
{% endhighlight %}

<br>

2. 그럼 이제 추가해 보도록 하자
  - 좌측 메뉴 목록은 Home, About, Posts, Projects로 이루어져 있습니다.
  -  사실 Projects는 nav.html 파일 속에 적용되어 있지 않은 것 같은데 왜 나오는지 모르겠습니다 'ㅁ'ㅋㅋ, 분명 어딘가에서 추가를 하니까 나오는 거곗죠..... 아시는 분 급구.. 알려주세요.

위 소스 코드 분석에서 <!-- ★ ☆ ★ ☆ 여기 ★ ☆ ★ ☆ --> 인 부분을 수정해 줍니다.
사실 메뉴를 어디에 추가하냐에 따라 위치가 달라지는데 <!-- ★ ☆ ★ ☆ 여기 ★ ☆ ★ ☆ --> 부분에 추가를 해주시면 Posts 위치 밑에 생깁니다.
위치야 원하는 곳에 하시면 되니까 어디든 자유롭게 하시고 어떤 걸 추가해야 하는지 보도록 합시다.

{% highlight html %}
<li>
  <a href="#">메뉴이름</a>
  <ul class="dl-submenu">
    <li><a href="{{ site.url }}/서브메뉴주소/">서브메뉴이름</a></li>
  </ul>
</li>
{% endhighlight %}

위 내용을 적절하게 수정해서 넣어주시면 됩니다.
`메뉴이름 >> 서브메뉴이름 ` 순으로 2차 메뉴가 생성됩니다.

- 같은 깃 레퍼지토리 안에서 생성하실 때는 `서브메뉴주소`가 폴더 이름이 되겠습니다. <br>
ex) <a href="{{ stie.url }}/_posts/"> ... </a>

- 만약 다른 깃 레퍼지토리나 외부 홈페이지를 연결해 주신다면 href 자체의 값을 바꿔주시면 됩니다. <br>
ex) <a href="http://www.github.com"> ...</a>

<br>

> 아? 그런데 나는 Projects 처럼 동작하는 1차 메뉴를 만들고 싶은데요..?

그렇다면 이렇게 만들어 줍니다.

{% highlight html %}
<li>
  <a href="{{ stie.url }}/메뉴주소">메뉴이름</a>
</li>
{% endhighlight %}

  a 태그의 href 속성을 설정하는 방법은 위의 예시와 동일합니다 :)
