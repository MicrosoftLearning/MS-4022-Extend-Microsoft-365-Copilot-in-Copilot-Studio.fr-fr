---
title: Instructions de l’exercice
permalink: index.html
layout: home
---

# Exercices

Cette page répertorie les exercices associés au cours de compétence Microsoft **MS-4022 : étendre Microsoft 365 Copilot avec Copilot Studio**.

Parcours d’apprentissage connexe : [Étendre Microsoft 365 Copilot avec Copilot Studio](https://learn.microsoft.com/training/paths/extend-microsoft-365-copilot-studio/).

**Remarque** : pour effectuer ces exercices, vous aurez besoin des éléments suivants.

- Un compte professionnel ou scolaire ayant [accès à Copilot Studio](https://learn.microsoft.com/microsoft-copilot-studio/requirements-licensing-subscriptions). Si vous n’avez pas encore accès à Copilot Studio, selon la configuration de votre organisation Microsoft 365, vous pouvez peut-être [créer un compte d’essai](https://learn.microsoft.com/microsoft-copilot-studio/sign-up-individual).
- Une licence Microsoft 365 Copilot
- Des informations d’identification pour se connecter aux sources de contenu souhaitées (connecteurs, API, etc.)

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %} {% assign labs = labs | sort: "lab.title" %} {% for activity in labs  %}
- [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) {% endfor %}

