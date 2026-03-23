Voici tout le contenu dans un seul bloc de code 👇

# 🚀 Labo AWS CodeBuild - Hello World (Étape par étape)

## 📌 Introduction

Ce labo permet de comprendre le cycle DevOps sur AWS en utilisant :
- AWS CodeCommit (gestion du code)
- AWS CodeBuild (build automatisé)
- Amazon S3 (stockage des artefacts)

👉 Objectif : Compiler, modifier et exécuter une application Java en utilisant AWS.

---

## 🎯 Objectifs du labo

À la fin de ce labo, vous serez capable de :

- Cloner un repository AWS CodeCommit
- Modifier et versionner du code avec Git
- Automatiser un build avec AWS CodeBuild
- Générer un fichier `.jar`
- Exécuter une application Java

---

## 🧩 Architecture du labo

1. Code Editor (IDE cloud)
2. AWS CodeCommit (repo Git)
3. AWS CodeBuild (build automatique)
4. Amazon S3 (stockage des artefacts)

---

## 🟢 Étape 1 : Connexion et clonage du repository

### 🔹 1.1 Accéder au Code Editor
- Ouvrir l’URL du labo
- Fermer les onglets inutiles
- Se familiariser avec l’interface

---

### 🔹 1.2 Cloner le repository

```bash
git clone codecommit://JavaApp

👉 Résultat attendu :

Un dossier JavaApp apparaît
Structure du projet :
JavaApp/
├── src/
│   └── sample/
│       └── Hello.java
├── buildspec.yml


🟢 Étape 2 : Compiler et exécuter le programme Java
🔹 2.1 Accéder au dossier
cd ~/environment/JavaApp/src
🔹 2.2 Compiler le code
javac sample/Hello.java

👉 Génère :

Hello.class
🔹 2.3 Exécuter le programme
java -cp . sample.Hello

👉 Résultat attendu :

Hello World!
🟢 Étape 3 : Modifier et pousser le code
🔹 3.1 Modifier le code

Dans Hello.java :

System.out.println("Build with AWS CodeBuild!");
🔹 3.2 Préparer les changements
cd ~/environment/JavaApp
git status
git add .
🔹 3.3 Commit
git commit -m "Update message"
🔹 3.4 Push vers CodeCommit
git push

👉 Le code est maintenant stocké sur AWS CodeCommit.

🟢 Étape 4 : Lancer un build avec AWS CodeBuild
🔹 4.1 Accéder à CodeBuild
Aller dans AWS Console
Rechercher CodeBuild
Ouvrir le projet JavaCMDBuild
🔹 4.2 Lancer le build
Cliquer sur Start build
🔹 4.3 Ce que fait CodeBuild

Grâce au fichier buildspec.yml, CodeBuild :

Compile le code
Exécute le programme
Crée un fichier .jar
javac src/sample/Hello.java
java -cp src sample.Hello
jar cf Hello.jar sample/Hello.class

👉 Résultat attendu :

Build with AWS CodeBuild!
🟢 Étape 5 : Récupérer et exécuter le fichier .jar
🔹 5.1 Récupérer le bucket S3
source_bucket=$(aws s3api list-buckets --query "Buckets[?contains(Name, 'artifactsbucket')].Name | [0]" --output text)
🔹 5.2 Télécharger le fichier .jar
aws s3 cp s3://$source_bucket/JavaCMDBuild/Hello.jar ./Hello.jar
🔹 5.3 Exécuter le fichier
java -cp Hello.jar sample.Hello

👉 Résultat attendu :

Build with AWS CodeBuild!
✅ Résultat final

À la fin du labo, vous avez :

Cloné un repo CodeCommit
Modifié et versionné du code
Automatisé un build avec CodeBuild
Généré un fichier .jar
Exécuté l’application
💡 Points clés à retenir
CodeCommit = gestion du code (Git)
CodeBuild = automatisation des builds
S3 = stockage des artefacts
buildspec.yml = cœur de l’automatisation
🏁 Conclusion

Ce labo montre un workflow DevOps complet :

👉 Code → Git → Build → Artefact → Exécution

C’est la base des pipelines CI/CD modernes sur AWS.