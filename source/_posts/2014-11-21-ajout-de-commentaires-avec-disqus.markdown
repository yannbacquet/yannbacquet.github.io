---
layout: post
title: "Ajout de commentaires avec Disqus"
date: 2014-11-21 15:44:08 +0100
description: octopress tuto
comments: true
categories: [octopress]
---

## disqus
Afin de permettre l'ajout de commentaires par vos lecteurs; Vous pouvez utiliser un service externe : Disqus.   
Disqus s'intègre tres facilement avec octopress.
En effet on a besoin que d'une ligne de paramétrage ! même moi  j'y suis arrivé :-)

-Tout d'abord il vous faut créer un compte chez  [Disqus](https://disqus.com).
Notez bien le 'short name' de votre compte, vous en aurez besoin dans votre config octopress.

-modifiez votre `_config.yml` :    
cherchez  `disqus_short_name` et ajoutez y votre short name comme ceci:   
`disqus_short_name: myShortName`

Et pis c'est tout!