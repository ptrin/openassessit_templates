
<a href="https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#timing-adjustable">WCAG 2.2.1</a>

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### Meta refresh issue

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

Remove the `{{ item.node.snippet }}` tag from the header.

{% include 'includes/other-options-w-details.md' %}

{% if not loop.last %}
---
{% endif %}
<br>

{% endfor %}

<br>
