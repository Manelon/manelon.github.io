---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# Hola, soy Manel

Llevo años programando, leyendo comics y jugando videojuegos. Tengo [un blog técnico llamado nocompila.com](https://www.nocompila.com)

Estoy jugando con github pages para ver como funciona el servicio y también un poco con Jekyll a ver qué se puede hacer con todo esto.
Por ahora este sitio está en obras, fase beta, alfa, WIP... o como se diga ahora.

Aunque tanbién estoy escribiendo un blog aqui

<ul>
    {% for post in site.posts %}
    <li>
        <h2><a href="{{ post.url}}">{{ post.title}}</a></h2> 
        <small>{{ post.date | date: "%-d %B %Y" }}</small>
        <p> {{ post.excerpt }}</p>
    </li>
    {% endfor %}
</ul>