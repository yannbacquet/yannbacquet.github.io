---
layout: post
title: "Octopress customisation"
date: 2014-07-02 12:52:27 +0200
comments: true
categories: [octopress]
keywords: octopress,tutorial,tuto,blog
description: octopress customisation tuto 

---

## Thèmes
Vous pouvez récupérer des [thèmes](http://octopressthemes.com) déja tout fait pour remplacer celui par defaut    
Il faudra alors copier le répertoire dans octopress\\.themes

## _config.yml
`octopress\config.yml` est le point d'entré pour customiser votre blog:   
Vous pouvez commencer par changer `title:`  `subtitle:`  `author:` 
et eventuellement le format de date avec `date_format:` 
<!--more-->  
Pour franciser la "Category", changez  `category_title_prefix:`.   
Passez `titlecase:` a false Si vous ne voulez pas de majuscule à chaque mots (pour vos titres).

Pour une présentation avec résumés (affichage partiel de chaque post)
il faudra ajouter dans vos posts `<!--more-->`   
et pour fanciser, modifier `excerpt_link:`

Pour customiser la partie droite de votre blog, modifiez
`default_asides:`   
Par exemple vous pouvez vous rajouter une fenêtre "About" avec   
{% codeblock %}
default_asides: [ custom/asides/about.html, ...
{% endcodeblock %}
le about.html à customiser se trouvant sous    `octopress\source\_includes\custom\asides\about.html`

## page de présentation
je me créé une page about (ca pourrait être toto)   
`rake new_page[about]` =>  `source\about\index.markdown`   
Si vous voulez ensuite un onglet pointant dessus :   
allez dans `source\_includes\custom\navigation.htm`   
et ajouter :
{% codeblock %}
<li><a href="{{ root_url }}/about">A Propos</a></li>
{% endcodeblock %}

## SEO (search engine optimisation)
voici d'abord un lien [wikipedia SEO](http://fr.wikipedia.org/wiki/Optimisation_pour_les_moteurs_de_recherche)  
Même si les moteurs de recherche semblent s'apppuyer de moins en moins sur les 'meta tags'; ca ne mange pas de paim de les rajouter.

Pour la *Home page*: rajouter dans _config.yml les mots clés `keywords` et `description`   
{% codeblock %}
description: #site description
keywords:    #key1,key2,key3
{% endcodeblock %}

Puis pour sa bonne prise en compte : Dans `source/_includes/head.html` 
apres la ligne `<meta name="author" ...` changer le code pour description/Keywords
avec:

{% codeblock %}
{% raw %}
{% capture description %}{% if page.url == "/index.html" %} {{ site.description }}{% elsif page.description %}{{ page.description }}{% else %}{{ content | raw_content }}{% endif %}{% endcapture %}
  <meta name="description" content="{{ description | strip_html | condense_spaces | truncate:150 }}">
  {% if page.url == "/index.html" %}<meta name="keywords" content="{{ site.keywords }}">
  {% elsif page.keywords %}<meta name="keywords" content="{{ page.keywords }}">{% endif %}
{% endraw %}
{% endcodeblock %}
