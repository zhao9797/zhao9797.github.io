# 📑 Publications

{% assign sorted_papers = site.pages | sort: 'path' | reverse %}
{% for page in sorted_papers %}
{% if page.path contains "_pages/includes/papers/" and page.path contains ".md" %}
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

