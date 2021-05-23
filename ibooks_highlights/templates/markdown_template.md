    -Release year: 
    -Topic:
    -Recommended by: 
    -Goodread links:
    -Summary  ↓
-## iBooks hightlights/notes
{% set vars={'last': none} %}
{% for h in highlights %}
{# found a new chapter, print its title #}
{% if h.selected_text %}
{% if h.chapter is not none and vars.last != h.chapter %}
{# stupid hacky nonsense to get around assignment not holding in outer scope #}
{% if vars.update({'last': h.chapter}) %}{% endif %}

    -### {{ h.chapter }}
    {% endif %}

    {# print the quote #}
    -“{{ h.selected_text }}” {% if h.note is not none and h.note|length > 0 %}

            -^^NOTE:^^ {{ h.note }}_{% endif %}

{% endif %}
{% endfor %}
 