# 📑 Publications

<small>* indicates equal contribution</small>

{% assign sorted_papers = site.pages | sort: 'path' | reverse %}

## 🌟 First / Co-first Author

{% for page in sorted_papers %}
{% if page.path contains "_pages/includes/papers/" and page.path contains ".md" and page.first_author %}
{% assign authors = page.authors | replace: "<*", "<strong>" | replace: "*>", "</strong>" %}
<div class='paper-box'>
  <div class='paper-box-image'>
    <div class="badge">{{ page.badge }}</div>
    <img src='{{ site.baseurl }}{{ page.image }}' alt="{{ page.title }}" width="320px" height="240px">
  </div>
  <div class='paper-box-text'>
    <p><a href="{{ page.link }}">{{ page.title }}</a></p>
    <p>{{ authors }}</p>
    <p>
      {% for item in page.links %}
        <a href="{{ item.url }}"><strong>{{ item.name }} </strong></a>{% unless forloop.last %}, {% endunless %}
      {% endfor %}
    </p>
  </div>
</div>
{% endif %}
{% endfor %}

## 🤝 Collaborations

{% for page in sorted_papers %}
{% if page.path contains "_pages/includes/papers/" and page.path contains ".md" and page.first_author != true %}
{% assign authors = page.authors | replace: "<*", "<strong>" | replace: "*>", "</strong>" %}
<div class='paper-box'>
  <div class='paper-box-image'>
    <div class="badge">{{ page.badge }}</div>
    <img src='{{ site.baseurl }}{{ page.image }}' alt="{{ page.title }}" width="320px" height="240px">
  </div>
  <div class='paper-box-text'>
    <p><a href="{{ page.link }}">{{ page.title }}</a></p>
    <p>{{ authors }}</p>
    <p>
      {% for item in page.links %}
        <a href="{{ item.url }}"><strong>{{ item.name }} </strong></a>{% unless forloop.last %}, {% endunless %}
      {% endfor %}
    </p>
  </div>
</div>
{% endif %}
{% endfor %}
