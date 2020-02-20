---
layout: post
title:  "Hola Jekyll!"
date:   2020-02-19 23:39:41 +0000
categories: jekyll
tags: [jekyll, github pages]
---
Este es mi primer post en este blog. Todavía no sé qué voy a hacer aquí.

Lo que sé es que quería empezar a probar Jekyll, así que el otro día instalé [Jekyll y completé tutorial oficial](https://jekyllrb.com/docs/step-by-step/01-setup/). 
Al dia siguiente estaba convencido que podría publicar la primera version de misitio web usando github pages y ¡¡¡¡Sorpresa!!!! no funciona.

La última version de Jekyll al escribir estas líneas es la 4.0.0, pero la version soportada por Github es la 3.8.5, asi que antes de empezar nada es mejor [comprobar las versiones soportadas por github](https://pages.github.com/versions/)

No soy un experto en ruby, así que corté por lo sano, lo primero desintalé la version 4.0.0 de jekyll y después instalé la versión 3.5.8
``` shell
gem uninstall jekyll
gem install jekyll -v 3.8.5
```

para asegurarme que si por error instalaba un paquete que no era el correcto también edite el Gemfile dejando todas las versiones fijas. Así quedó el fichero:
```ruby
source "https://rubygems.org"

# Hello! This is where you manage which Jekyll version is used to run.
# When you want to use a different version, change it below, save the
# file and run `bundle install`. Run Jekyll with `bundle exec`, like so:
#
#     bundle exec jekyll serve
#
# This will help ensure the proper Jekyll version is running.
# Happy Jekylling!
gem "jekyll", "~> 3.8.5"

# This is the default theme for new Jekyll sites. You may change this to anything you like.
gem "minima", "~> 2.0"

# If you want to use GitHub Pages, remove the "gem "jekyll"" above and
# uncomment the line below. To upgrade, run `bundle update github-pages`.
# gem "github-pages", group: :jekyll_plugins

# If you have any plugins, put them here!
group :jekyll_plugins do
  gem "jekyll-feed", "0.13.0"
  gem "github-pages", "204"
  gem "jekyll-sitemap", "1.4.0"
  gem "jekyll-seo-tag", "2.6.1"
end

# Windows does not include zoneinfo files, so bundle the tzinfo-data gem
gem "tzinfo-data", platforms: [:mingw, :mswin, :x64_mingw, :jruby]

# Performance-booster for watching directories on Windows
gem "wdm", "~> 0.1.0" if Gem.win_platform?
```

Una vez superado esto pude ejecutar los pasos del [tutorial de como usar Jekyll con github pages](https://help.github.com/en/github/working-with-github-pages/creating-a-github-pages-site-with-jekyll)
