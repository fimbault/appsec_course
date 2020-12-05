# Projet honeypot (assignment)

Ce projet vous permettra d'appliquer les notions présentées en cours.

## Livrable 

- projet sur github avec sa documentation (markdown)
- présentation/démo

## Organisation

Vous travaillerez en petit groupe et devrez indiquer comment vous vous répartissez le travail.
En pratique, vous travaillerez à plusieurs sur git, je vous conseille une méthodologie [trunk based](https://trunkbaseddevelopment.com/). 
En cas de souci, [ohshitgit](https://ohshitgit.com/) peut vous aider.  

## Qu'est-ce qu'un honeypot

C'est un leurre qui nous permettra d'observer des tentatives de connexion. 

Le honeypot peut concerner : 
- des systèmes ouverts sur l'extérieur. Par exemple: partie admin d'un site wordpress, ou pour des systèmes [industriels](http://conpot.org/)
- des systèmes internes, pour détecter au plus tôt des intrusions. Le [birding guide](http://canary-content.s3-website-us-east-1.amazonaws.com/documents/birding-guide.pdf) donne des exemples intéressants.

Ce qui existe: 
- [awesome honeypot](https://github.com/paralax/awesome-honeypots) vous donnera une liste complète de honeypots existants (mais l'objectif n'est pas de réutiliser ce qui existe). 
- des scanners (e.g. [shodan](https://www.shodan.io/)) permettent aussi de détecter des actifs (serveurs, IoT) ouverts sur internet

## Ce qui vous est demandé

Mettre en place un système pour l'observalibilité de services ssh et http.
Exemple : [honeypot ssh](https://systemoverlord.com/2020/09/04/lessons-learned-from-ssh-credential-honeypots.html)

Il vous est demandé d'avoir une réflexion sur ce qui vous faites et donc d'expliciter le niveau de sécurité de vos services : 
- quelles vulnérabilités exposez-vous volontairement? Par exemple, grâce aux outils de configuration as code, vous pouvez exposer des containers avec des settings de sécurité différents, et voir ce qui se passe
- et pouvoir killer vos services

Une partie de votre infrastructure (le backend de votre honeypot, pour analyser les logs) doit être sécurisée. Précisez comment. 

## Technologies conseillées

- le choix du/des cloud que vous utilisez est libre (prenez un abonnement gratuit)
- [golang](https://golang.org/) pour programmer vos honeypots et vos remontées d'alertes
- github (et github actions)
- containers (et éventuellement technologies de scan associées)
- déploiement CI/CD avec [terraform](https://www.terraform.io/)
- configuration avec [starlark](https://ascode.run/)
- gestion de vos secrets avec [vault](https://www.vaultproject.io/) et [SOPS](https://github.com/mozilla/sops)
- gestion des logs avec [fluentbit](https://fluentbit.io/) et [prometheus](https://prometheus.io/)
- visualisation avec [graphana](https://grafana.com/)

Ca sera donc aussi l'occasion d'apprendre à utiliser les technologies devsecops.
