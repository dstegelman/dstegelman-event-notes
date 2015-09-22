===============
Django Snippets
===============


Pagination
----------

Inside the views::



Templates::

    {% if is_paginated %}
    <div class="pagination">
        <ul>
            {% if page_obj.has_previous %}
            <li><a href="?page={{ page_obj.previous_page_number }}">Prev</a></li>
            <li><a href="?page={{ page_obj.previous_page_number }}">{{ page_obj.previous_page_number }}</a></li>
            {% endif %}
            <li class="active">
                <a href="?page={{ page_obj.number }}">{{ page_obj.number }}</a>
            </li>


            {% if page_obj.has_next %}
            <li><a href="?page={{ page_obj.next_page_number }}">{{ page_obj.next_page_number }}</a></li>
            <li><a href="?page={{ page_obj.next_page_number }}">Next</a></li>
            {% endif %}
        </ul>
    </div>
    {% endif %}
