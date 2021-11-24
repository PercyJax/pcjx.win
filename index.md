---
layout: default
---

{% assign redirects = site.pages | where_exp: "item", "item.redirect_to != nil" %}
{% for page in redirects %}
  {% if page.browsable==true %}
  [{{ page.url }}]({{ page.url | relative_url }}) 🔀 `{{ page.redirect_to }}`

  > {{ page.title | escape }}

  ---
  {% endif %}
{% endfor %}
