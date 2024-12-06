## Upcoming Events
{% for eventYear in site.data.upcomingEventList %}
    {% for eventMonth in eventYear.months %}
<dl><dt> {{ eventMonth.month }} {{ eventYear.year }} </dt></dl>
<ul>
        {% for event in eventMonth.events %}
<li>
{{ event.title }}
    <ul>
        <li> Dates: {{ event.dates }} </li>
        <li> Location: {{ event.location }} </li>
        {% if event.cost %}
        <li> Cost: {{ event.cost }} </li>
        {% endif %}
            {% for information in event.other_information %}
                {% if information.link %}
        <li> <a href="{{information.link}}"> {{information.text}} </a></li>
                {% elsif information.document %}
        <li> <a href="{{site.url}}/{{information.document}}"> {{information.text}} </a></li>
                {% else %}
        <li> {{ information.text }} </li>
                {% endif %}
            {% endfor %}
    </ul>
</li>
        {% endfor %}
</ul>
    {% endfor %}
{% endfor %}
