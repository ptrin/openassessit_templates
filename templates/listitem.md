{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

<h3> The `{{ item.node.snippet|striptags }}` {{ item.node.explanation|escape|replace('Fix any of the following:', '')|replace('Fix all of the following:', '') }} </h3>

__Visual location:__

![{{ item.node.snippet|striptags }} list with invalid children](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:
Move the offending child elements inside list item `<li>` elements.

{% include 'includes/other-options.md' %}

-
<br>

{% endfor %}

<br>