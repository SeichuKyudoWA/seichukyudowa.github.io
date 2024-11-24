---
permalink: /
---
<!-- 
    The capture part and the source-split-last piping is a hack so that 
    the Front Matter from "pages/home.md" doesn't appear on the main page.

    This was done so that there is a single source of truth for the home
    content.

    Anything between two "---" (triple dash) anywhere in anything included
    will be omitted from displaying.
-->
{% capture source %}{% include_relative pages/home.md %}{% endcapture %}
{{ source | split: "---" | last }}
