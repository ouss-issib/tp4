# TP 5 : Docker Engine, Jenkins et CI/CD

Ce projet documente la mise en place d'une chaîne d'intégration continue (CI) automatisée pour une application web conteneurisée.

## 1. Objectifs de la Partie 1
* [cite_start]Configuration de l'environnement Jenkins sur Windows[cite: 8].
* [cite_start]Automatisation du build d'une image Docker Nginx[cite: 18].
* [cite_start]Publication automatique vers le registre Docker Hub[cite: 11].

## 2. Configuration Technique
### Pipeline Jenkins (Job Freestyle)
[cite_start]Le job **job TP5 Jenkins** est lié au dépôt GitHub et configuré pour se déclencher à chaque commit[cite: 64, 147].
* **Source** : `https://github.com/ouss-issib/tp4`.
* **Credentials** : Utilisation d'un Token d'accès sécurisé pour le compte Docker Hub `ousazwita`.

### Docker Hub
Le dépôt distant est configuré en mode **Public** pour permettre le déploiement ultérieur.
* **Repository** : `ousazwita/tp_jenkins`.

## 3. Workflow de l'Application
1. **Modification du Code** : Changement effectué dans le fichier `index.html` (ex: "tp5 v2").
2. **Push Git** : Envoi des modifications vers la branche `main` via `git push`.
3. **Build Jenkins** : Déclenchement automatique du build (Build #17 réussi en 16s).
4. **Push Docker** : Publication de la nouvelle image sur Docker Hub.
5. **Résultat** : L'application est accessible localement sur le port `8081`.

## 4. Captures d'Écran
| Étape | État |
| :--- | :--- |
| **Push** | ![Pending](captures/push.png) |
| **Pending** | ![Pending](captures/pending.png) |
| **Commit & Push** | ![Git Push](captures/push.png) |
| **Succès Build** | ![Build Success](captures/success.png) |
| **Application Live** | ![App Running](captures/running-app.png) |

---
*Réalisé par Oussama Issib - 2025/2026*.
