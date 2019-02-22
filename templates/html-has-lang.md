
<a href="https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#language-of-page">WCAG 3.1.1</a>

{%- if audit.description %}

{{ audit.description|trim|escape }}

{% endif -%}

{% for item in audit.details['items'] %}

### Add `lang` attribute.

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:
Add a `lang` attribute. For websites in english use `<html lang="en">`. [Other languages references](https://www.w3schools.com/tags/ref_language_codes.asp)

<details>
<summary>_Other options:_</summary>
{{ item.node.explanation|escape|replace('  ', '<br>') }}
</details>

<details>
<summary>_Additional debugging details_</summary>
Path:<br>
<code>{{ item.node.path }}</code><br>
Selector:<br>
<code>{{ item.node.selector }}</code>
</details>

{% if not loop.last %}
---
{% endif %}
<br>

{% endfor %}

<br>
