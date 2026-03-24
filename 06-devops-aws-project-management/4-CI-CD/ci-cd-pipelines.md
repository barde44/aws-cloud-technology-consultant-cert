# 🚀 Pipelines CI/CD

## 📌 Qu’est-ce qu’un pipeline CI/CD ?

Un **pipeline CI/CD** (Intégration Continue / Déploiement Continu) est un processus automatisé qui permet de construire, tester et déployer une application rapidement et de manière fiable.

👉 Objectif :
- Automatiser le cycle de développement
- Réduire les erreurs humaines
- Accélérer la livraison des logiciels

---

## 🔄 Les deux concepts clés

### 🔹 1. Intégration Continue (CI)

La CI consiste à :
- Intégrer fréquemment le code dans un dépôt partagé
- Exécuter automatiquement des tests
- Détecter les erreurs rapidement

👉 Exemple :
Un développeur pousse son code → les tests s’exécutent automatiquement

---

### 🔹 2. Déploiement Continu (CD)

Le CD consiste à :
- Déployer automatiquement l’application après validation
- Rendre les nouvelles versions disponibles rapidement

👉 Types :
- **Continuous Delivery** : déploiement avec validation manuelle
- **Continuous Deployment** : déploiement automatique

---

## ⚙️ Étapes d’un pipeline CI/CD

Un pipeline typique comprend :

1. 📥 **Source**
   - Récupération du code (Git)

2. 🏗️ **Build**
   - Compilation du code
   - Gestion des dépendances

3. 🧪 **Test**
   - Tests unitaires
   - Tests d’intégration

4. 📦 **Package**
   - Création d’artefacts (.jar, .zip, Docker image)

5. 🚀 **Deploy**
   - Déploiement en staging ou production

---

## 🧰 Outils utilisés

### 🔹 CI/CD général
- Jenkins
- GitHub Actions
- GitLab CI/CD

### 🔹 AWS
- AWS CodePipeline
- AWS CodeBuild
- AWS CodeDeploy

---

## ✅ Avantages

- ⚡ Livraison rapide
- 🐞 Détection précoce des bugs
- 🤝 Meilleure collaboration
- 🔁 Processus automatisé
- 📈 Amélioration continue

---

## ❌ Inconvénients

- Configuration initiale complexe
- Nécessite une bonne discipline
- Dépendance aux outils

---

## 🎯 Bonnes pratiques

- Écrire des tests automatisés
- Automatiser chaque étape
- Déployer fréquemment
- Surveiller les performances
- Utiliser le versioning

---

## 📊 Exemple simple de pipeline

``` id="example-pipeline"
Code → Build → Test → Deploy