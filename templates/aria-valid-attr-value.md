
<a href="https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#info-and-relationships">WCAG 1.3.1</a> <a href="https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#parsing">WCAG 4.1.1</a> <a href="https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#name-role-value">WCAG 4.1.2</a>

{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### This element is using invalid aria attributes.

__Visual location:__

![aria valid attribute value problem](assets/{{ generate_img_filename(data.finalUrl, item.node.selector) }})


__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:

TODO.

{% include 'includes/other-options-w-details.md' %}

{% if not loop.last %}
---
{% endif %}
<br>

{% endfor %}

<br>
