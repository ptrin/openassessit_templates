
<a href="https://www.w3.org/WAI/WCAG21/quickref/?versions=2.0#name-role-value">WCAG 4.1.2</a>

__I need a human!__ Manual Test: {{ audit.title|escape }}

{%- if audit.description %}

Description:<br>
{{ audit.description|trim|escape }}

<br>

{% endif -%}

<br>
