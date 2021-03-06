---
layout: usecases
title : Application de l’article 64
---
## Introduction

Dans le cadre de [la loi du 8 novembre 2019 relative à l'énergie et au climat](https://www.legifrance.gouv.fr/affichTexteArticle.do;jsessionid=A814DF82C4C2339D1BA972DAF0487BD9.tplgfr44s_2?idArticle=JORFARTI000039356027&cidTexte=JORFTEXT000039355955&dateTexte=29990101&categorieLien=id), certains fournisseurs d’énergie ont le droit d’accéder à une partie des données de l’API Entreprise concernant certains de leurs clients, pour vérifier leur éligibilité aux tarifs réglementés.

Les données concernées sont les effectifs (endpoint Entreprises et Etablissements de l’INSEE), les chiffres d’affaires (endpoint Exercices de l’Infogreffe) , les recettes et les totaux des bilans annuels (endpoint liasses fiscales de la DGFIP).

Cette autorisation d’accès est valide pour une période de huit mois suivant la promulgation de la loi, soit **jusqu’au 8 juillet 2020**.

Les fournisseurs mettent en œuvre un traitement automatisé des données issues de cette interface afin de n’avoir accès qu’aux données nécessaires pour déterminer l’éligibilité aux tarifs réglementés et conservent les données nécessaires pour déterminer l’éligibilité pendant une durée maximale de trois mois.

## Quelles sont les données autorisées pour le cas d'usage "Application de la loi énergie" ?

### Les données d'effectifs

Les données d'effectif sont disponibles en utilisant les endpoints ***entreprises et etablissements*** qui s'appuient sur l'API SIREN de l'INSEE.

Deux point d'attention sont à prendre en compte :
- il s'agit de tranches d'effectif "code_effectif_entreprise"  de la nomenclature  l'INSEE.
- Les données des entreprises qui lors de leur enregistrement ont déclaré ne pas souhaiter faire l'objet d'un démarchage commercial ne sont exposées que si l'on précise un paramettre dans la requete.

[documentation technique entreprise](https://doc.entreprise.api.gouv.fr/#entreprises)

### Les chiffres d’affaires

Les données de chiffres d'affaires (chiffre d'affaire comptable) sont accessibles en utilisant le endpoint ***Exercices issues*** 
Ces données sont issues de la liasse fiscale pour les entreprises soumises à l'impôt sur les sociétés qui ont déposés leurs comptes annuels aux greffes. 
L'API fourni les 3 derniers exercices.

[documentation technique exercices](https://doc.entreprise.api.gouv.fr/#exercices)

### Les données relatives aux recettes et au total de bilan annuels
Ces données sont accessibles en utilisant le endpoint ***liasses fiscales dgfip***

Pour les recettes, il s’agit dans le numéro d’imprimé 2033B (millésime 2018) de la valeur contenue pour le code_NREF 304456
Pour le chiffre d’affaire, il s’agit dans le numéro d’imprimé 2033B (millésime 2018) de la valeur contenue pour le code_NREF 304451

Pour cette donnée, il est demandé de limiter les appels à une requete par seconde.

[documentation technique liasse fiscale](https://doc.entreprise.api.gouv.fr/#liasses-fiscales-dgfip)

## Demander un accès aux données

Pour demander un accès, [veuillez consulter la page "Demander un accès"](https://entreprise.api.gouv.fr/demander_un_acces/), un déroulé des étapes à suivre vous sera décrit.

Comme expliqué dans l'introduction, les droits d'accès seront accordés jusqu'au 8 juillet 2020.  


