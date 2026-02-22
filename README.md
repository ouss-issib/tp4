# TP 5 : Intégration Continue (CI) avec Jenkins et Docker

[cite_start]Ce dépôt contient les ressources pour la première partie du TP portant sur la mise en place d'un flux d'intégration continue[cite: 4, 5].

## 1. Fichiers du Projet
Le projet est composé d'une application web simple et de sa configuration de conteneurisation :
* [cite_start]**index.html** : Affiche le message "welcome bdcc"[cite: 49].
* [cite_start]**Dockerfile** : Utilise l'image `nginx`, expose le port 80 et copie le fichier `index.html` vers le répertoire `/usr/share/nginx/html`[cite: 31, 32, 33].

## 2. Configuration Jenkins (Partie CI)
### Configuration du Moteur Docker
[cite_start]Pour lier Jenkins au moteur Docker sur Windows, la propriété globale suivante a été définie[cite: 210, 212]:
* [cite_start]**Variable** : `DOCKER_HOST` [cite: 215]
* [cite_start]**Valeur** : `tcp://localhost:2375` [cite: 217]

### Authentification Docker Hub
[cite_start]Les identifiants de connexion ont été configurés dans Jenkins pour permettre la publication de l'image[cite: 196]:
* **Registry Credentials** : Identifiant `ousazwita` lié à un Access Token Docker Hub.
* **Dépôt distant** : `ousazwita/tp_jenkins` (Dépôt public).

## 3. Détails du Job Jenkins
Le job de type **Freestyle** nommé `job TP5 Jenkins` effectue les actions suivantes :
1.  [cite_start]**Récupération du code** : Clone le dépôt depuis GitHub (`https://github.com/ouss-issib/tp4`)[cite: 117].
2.  [cite_start]**Docker Build** : Génère l'image locale `ousazwita/tp_jenkins:latest`[cite: 173, 175, 176].
3.  [cite_start]**Docker Publish** : Pousse l'image vers le registre Docker Hub après un succès du build[cite: 82, 98].

---
