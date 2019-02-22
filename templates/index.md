# {{ data.requestedUrl|replace('https://', '')|capitalize }} Assessment

__<{{ data.requestedUrl }}>__

__Screenshot:__

![Screenshot of this website](assets/screenshot.png)

<h2 id="toc-header">Contents of this report</h2>
<div id="toc">
<!--TOC-->
</div>

## Summary of WCAG Success Criteria violations
There were problems with the following success criteria for WCAG on this page:
<ul id="wcag-summary"></ul>

{% for cat_id, cat in data.categories.items() -%}
{% for audit in cat.sorted_audits %}
{%- if ( audit.scoreDisplayMode == "binary" and audit.score == 0) or
        (audit.scoreDisplayMode == "numeric" and audit.score != 100 ) or
        (audit.scoreDisplayMode == "manual") or
        (audit.scoreDisplayMode == "informative") or
        (audit.scoreDisplayMode == "error")
%}
## {{ audit.title }}

{%- include [audit.audit_template, "audit_result.md"] %}
{% if not loop.last %}
<hr>
{% endif %}
{%- endif %}
{% endfor %}
{%- endfor -%}

{% include 'includes/footer.md' %}
