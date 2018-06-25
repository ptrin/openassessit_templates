{%- if audit.description %}

{{ audit.description|trim }}

{% endif -%}

{% for item in audit.details['items'] %}

### The {{ item.node.snippet|striptags }}element should not have an `accesskey`.

__Visual location:__
{# TODO: Grabbing screen shots of specific elements can probably be automated #}
![{{ item.node.snippet|striptags }} element with an access key](https://via.placeholder.com/150x50)

__HTML location:__

```html
{{ item.node.snippet }}
```

#### Suggested solution:
Unless this website is an app, remove all `accesskeys` attributes.

<details>
<summary>_Additional debugging details_</summary>
Selector:<br>
<code>{{ item.node.path }}</code>

Path:<br>
<code>{{ item.node.selector }}</code>

More detailed explanation:<br>
{{ item.node.explanation|escape|replace('  ', '<br>') }}
</details>

<hr>

<br>
{% endfor %}