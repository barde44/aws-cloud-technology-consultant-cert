# 🛠️ Labo AWS - Commit a Bugfix (Étape par étape)

## 📌 Introduction

Ce labo permet de comprendre :
- Git (clone, commit, push)
- AWS CodeCommit
- AWS CodePipeline
- AWS CodeDeploy

👉 Objectif : Corriger un bug dans une application, puis déployer automatiquement la correction.

---

## 🎯 Objectifs

À la fin du labo, vous serez capable de :

- Identifier un bug dans une application
- Cloner un repo AWS CodeCommit
- Modifier le code
- Commit et push avec Git
- Observer un pipeline CI/CD
- Vérifier le déploiement

---

## 🧩 Architecture du labo

1. VS Code IDE (environnement de dev)
2. AWS CodeCommit (repo Git)
3. AWS CodePipeline (pipeline CI/CD)
4. AWS CodeDeploy (déploiement)
5. Amazon EC2 (hébergement de l’app)

---

## 🟢 Étape 1 : Vérifier l’application

- Ouvrir le lien **WebsiteURL**
- Observer l’application

👉 Problème :
- L’image (banner) ne s’affiche pas ❌

---

## 🟢 Étape 2 : Cloner le repository

### 🔹 2.1 Configurer Git

```bash
git config --global user.name "Student"
git config --global user.email "student@example.com"
🔹 2.2 Cloner le repo
git clone codecommit://PresidentsApp

👉 Résultat :

Dossier PresidentsApp créé
🟢 Étape 3 : Corriger le bug

👉 Fichier à modifier :

PresidentsApp/app/templates/main.html

👉 Problème :

Mauvais nom du fichier image (typo)

👉 Solution :

Corriger le nom de l’image (ex: banner.png)
🟢 Étape 4 : Préparer les changements (Git)
🔹 4.1 Aller dans le dossier
cd PresidentsApp
🔹 4.2 Vérifier les changements
git status
🔹 4.3 Ajouter le fichier
git add app/templates/main.html
🔹 4.4 Commit
git commit -m "Fix banner image typo"
🔹 4.5 Push vers CodeCommit
git push

👉 Cela déclenche automatiquement le pipeline CI/CD

🟢 Étape 5 : Observer le pipeline
🔹 Aller dans AWS Console
Ouvrir CodePipeline
Sélectionner : Presidents-Pipeline
🔹 Étapes du pipeline :
Source
Récupère le code depuis CodeCommit
Test
Exécute les tests unitaires
Deploy
Déploie sur EC2 via CodeDeploy
🔹 Vérifier :
Status = Succeeded
Commit ID visible
Message du commit affiché
🟢 Étape 6 : Vérifier le résultat
Retourner sur le site
Rafraîchir la page

👉 Résultat :

L’image banner s’affiche correctement ✅
✅ Résultat final

Vous avez :

Corrigé un bug
Utilisé Git (clone, add, commit, push)
Déclenché un pipeline CI/CD
Déployé automatiquement une application
💡 Points clés à retenir
Git permet de gérer les versions
CodeCommit stocke le code
CodePipeline automatise le workflow
CodeDeploy déploie l’application
Un push peut déclencher un déploiement
🏁 Conclusion

Ce labo montre un workflow DevOps complet :

👉 Code → Commit → Pipeline → Test → Deploy → Application

C’est un exemple concret de CI/CD en production sur AWS.