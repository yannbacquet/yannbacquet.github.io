---
layout: post
title: "Installation d'octopress"
date: 2014-06-27 10:07:51 +0200
description: octopress tuto
comments: true
categories: [octopress]
---

## github
Pour héberger un blog sur GitHub:   
il faut commencer par se créer un repo dédié avec comme nom , ben ton nom en fait ;)
c'est expliqué [la](https://pages.github.com/)  
Si tu penses utiliser octopress, crée juste le repository (tache 1 uniquement)    
Si tu n'es pas un expert github tu peux réviser un peu [ici](http://fr.openclassrooms.com/informatique/cours/gerez-vos-codes-source-avec-git). (tu n'auras besoin que des commandes de base)


## octopress
le mieux est de suivre  [le setup offciel](http://octopress.org/docs/setup/) et en parallèle les explications ci-dessous:

<!--more-->
- installer Git    
- installer Ruby + le dev Kit (si vous êtes sous windows le plus simple est d'aller directement sur le site de [ruby](http://rubyinstaller.org/downloads/) et d'y installer:    
`Ruby 1.9.3-p545`  (la version 1.9.3 était alors recommandée)  
puis le devkit associé: `DevKit-tdm-32-4.5.2-20111229-1559-sfx.exe`   
   
rajouter ensuite a votre Path les variables d'environnements  `...\Rubyxx\bin` , `...\RubyDevKit\bin` et  `...\RubyDevKit\mingw\bin`   
 (pour ces 2 dernières vous pouvez utiliser `RubyDevKit/devkitvars.bat`)   

- installer un blog octopress vide : [(cf octopress)](http://octopress.org/docs/deploying/github/)   
Créez vous un repertoire local qui accueillera votre blog,
et dans ce repertoire lancez :
>rake setup\_github\_pages

cette commande va vous checkouter un blog octopress vide et le faire mapper sur votre repo github
> rake generate    
rake deploy   

vous permet de générer votre site; puis de le déployer sur github pour enfin obtenir ceci :   
![blog Vide](\images\blogVide.png) 



