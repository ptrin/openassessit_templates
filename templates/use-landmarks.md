
<a href="https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#info-and-relationships">WCAG 1.3.1</a> <a href="https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#bypass-blocks">WCAG 2.4.1</a>

__I need a human!__ Manual Test: {{ audit.title|escape }}

{%- if audit.description %}

Description:<br>
{{ audit.description|trim|escape }}

<br>

{% endif -%}

<br>
