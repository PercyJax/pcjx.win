---
layout: default
---

{% assign redirects = site.pages | where_exp: "item", "item.redirect_to != nil and item.show != nil and item.show" %}
{% for page in redirects %}
  [{{ page.url }}]({{ page.url | relative_url }}) 🔀 `{{ page.redirect_to }}`

  > {{ page.title | escape }}

  ---
{% endfor %}
