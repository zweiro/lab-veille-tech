---
title: "Expérimentation : Écrire des messages de commit efficaces"
date: 2022-01-09T11:30:03+00:00
# weight: 1
# aliases: ["/first"]
tags: ["Configuration", "Git", "Travail d'équipe"]
categories: ["Expérimentation"]
author: "Robin Z."
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
description: "Les logiciels de versioning ont révolutionné la manière de travailler en équipe. Chacun peut désormais travailler facilement sur sa machine et partager son travail sans risque de détruire le travail des autres développeurs. En cas d’erreur, il est possible de remonter dans l’historique des versions pour en identifier l’origine. Cet article résume les tests de configuration de l’éditeur et les choix de rédaction pour un bon message de commit."
canonicalURL: "https://canonical.url/to/page"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
cover:
    image: "https://cdn.pixabay.com/photo/2018/01/11/21/27/laptop-3076957_960_720.jpg" # image path/url
    # alt: "Image test" # alt text
    # caption: "Image test" # display caption under cover
    relative: true # when using page bundles set this to true
    hidden: false # only hide on current single page
---

## Pourquoi écrire un bon message de commit ?
Écrire de bons messages de commit est nécessaire pour un travail de qualité en équipe. Cela demande un minimum de temps, mais permet potentiellement d’en gagner énormément dans le futur. Parmi les avantages d’écrire un bon message, on a :
* Retrouver l’origine de futures erreurs
* Permettre aux autres développeurs de comprendre ce que l’on a fait
* Pouvoir revenir à tout moment à une version précise du produit
## Règles importantes dans la rédaction de messages de commit (Tirées de l’article cité dans les sources)
* Un message de commit est composé d’un en-tête, d’un corps et d’un pied de page
* Le sujet est limité à 50 caractères
o	Le sujet est une ligne qui résume au mieux tous les changements présents dans le commit
* Mettre une majuscule à la première lettre du sujet de l’en-tête
* Éviter le point « . » en fin de la ligne d’en-tête
* Ajouter une ligne blanche entre l’en-tête, le corps de texte et le pied de page
* Limiter la largeur du corps de texte à 72 caractères
* Écrire le corps de texte sous forme de liste à puce
* Utiliser l’impératif
* Décrire quoi et pourquoi mais pas comment
* Le pied de page peut faire référence à un éventuel N° de ticket du support
## Il est possible de configurer son éditeur VSCode pour respecter au mieux ces règles. C’est parti pour l’expérimentation.
On commence définir VSCode comme éditeur git par défaut :
git config –global core.editor « code –wait »
Ensuite nous allons ajouter deux lignes qui vont visuellement délimiter les 50 et 72 caractères dont on a parlé précédemment. Pour cela il faut appuyer sur CTRL + Shift + P et taper « Open user setting JSON ». On peut maintenant ajouter les quelques lignes suivantes :
 
![VSCode config for rulers](https://github.com/zweiro/lab-veille-tech/blob/main/resources/_gen/images/config.png?raw=true)

Il est maintenant temps de tester en faisant « git commit »

![GitHub commits stats graph](https://github.com/zweiro/lab-veille-tech/blob/main/resources/_gen/images/empty-commit.png?raw=true)
 
Magnifique, j’obtiens 2 lignes visuelles qui indiquent les fameux 50 (en vert) et 72 (en orange) caractères !
On peut maintenant remplir pour enfin faire un commit « digne de ce nom » :

![GitHub commits stats graph](https://github.com/zweiro/lab-veille-tech/blob/main/resources/_gen/images/better-commit.png?raw=true)
 
Cela démontre déjà beaucoup plus ce qui a été fait, mais un aspect visuel peut encore venir améliorer la compréhension. Il s’agit du projet Gitmoji construit principalement par Carlos Cuesta et qui propose d’ajouter un emoji aux lignes du commit. Cela est malin, car les images marquent toujours plus les esprits que les mots. Voici donc ce que donne notre commit modifié :

![GitHub commits stats graph](https://github.com/zweiro/lab-veille-tech/blob/main/resources/_gen/images/emoji-commit.png?raw=true)
 
Voici donc à quoi cela ressemble une fois sur GitHub :

![GitHub commits stats graph](https://github.com/zweiro/lab-veille-tech/blob/main/resources/_gen/images/github-commit.png?raw=true)
 
Beaucoup plus parlant que ce dont on a l’habitude n’est-ce pas ? 😊
Ce que j’en ressors pour mon futur professionnel
La collaboration est un élément essentiel dans les équipes de développement et les outils de versioning sont des éléments clés de celle-ci. Prendre le temps de faire de la documentation de qualité représente un gain de temps énorme pour le futur et je suis réellement heureux d’avoir appris les règles citées dans cet article. Je me réjouis beaucoup d’appliquer tout cela à l’avenir.
## Source
https://medium.com/@hritik.jaiswal/how-to-write-a-good-commit-message-9d2d533b9052
Dans cet article Medium, HRITIK JAISWAL propose une compilation de ses connaissances dans le domaine de la rédaction de commit en alliant humour et simplicité.
