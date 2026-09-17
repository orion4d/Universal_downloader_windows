# 🌐 Universal Downloader

> **Application portable Windows de téléchargement vidéo/audio, extraction audio et capture de flux.**  
> **Created by Orion4D — 2026**

<!--
Ajoute ici ta capture principale GitHub, par exemple :

<img width="1600" alt="Universal Downloader" src="https://github.com/user-attachments/assets/TON-ID-IMAGE" />
-->

- **Lien direct :** [UniversalDownloader-v1.0.2-Portable-win-x64.zip](https://github.com/orion4d/Universal_downloader_windows/releases/download/v1.0.2/UniversalDownloader-v1.0.2-Portable-win-x64.zip)

## 🚀 Universal Downloader — Portable Windows x64

**Universal Downloader** est une application Electron portable basée sur **yt-dlp**, **FFmpeg**, **FFprobe** et **Deno**.

Elle permet d'analyser, télécharger, convertir et capturer des médias provenant de nombreuses plateformes, avec une interface graphique simple, une file d'attente, des profils de téléchargement, un historique local et des outils de diagnostic.

L'application est disponible en **français** et en **anglais**.

---

## ✨ Fonctionnalités

### 📥 Téléchargement intelligent

- **Vidéo + Audio**
- **Vidéo seule**
- **Audio MP3**
- **Fusion manuelle vidéo/audio**
- **Formats automatiques ou sélection manuelle**
- **Détection automatique de la plateforme**
- **Aperçu avant téléchargement**
  - miniature
  - titre
  - durée
  - plateforme
  - ID
- **Téléchargement de la miniature en PNG**
- **Normalisation automatique de certaines URL**
- **Support des URL directes audio/vidéo**

Universal Downloader utilise principalement les extracteurs de **yt-dlp**.  
La compatibilité réelle dépend donc des plateformes actuellement prises en charge par yt-dlp.

---

### 🎯 Profils de téléchargement

Des profils rapides sont disponibles pour éviter de devoir sélectionner manuellement les formats à chaque téléchargement :

- **Meilleure qualité — vidéo + audio**
- **MP4 — jusqu'à 1080p**
- **MP4 — jusqu'à 720p**
- **MP3 — 192 kb/s**
- **MP3 — 320 kb/s**

Les onglets détaillés restent disponibles pour choisir précisément un flux vidéo ou audio.

---

### 🎵 Extraction audio

Universal Downloader peut extraire ou convertir l'audio vers le format MP3.

Profils disponibles :

```text
MP3 192 kb/s
MP3 320 kb/s
```

L'application utilise **FFmpeg** pour la conversion.

Les flux audio directs peuvent également être traités, par exemple :

```text
.mp3
.aac
.m4a
.ogg
.opus
.wav
.flac
```

---

### 🖼️ Téléchargement des miniatures

Après analyse d'une vidéo, le bouton :

```text
Télécharger miniature PNG
```

permet d'enregistrer la miniature dans le dossier de téléchargement.

Les miniatures JPG ou WebP sont converties en **PNG** lorsque cela est nécessaire.

---

### 📡 Capture de flux

Universal Downloader possède un mode **Capture flux** pour les médias compatibles non protégés par DRM.

Cas d'utilisation :

- Live vidéo
- Web radio
- Flux audio direct
- HLS / M3U8
- DASH / MPD
- Capture d'une partie d'une VOD

Modes disponibles :

```text
Vidéo + Audio
Audio uniquement
```

Pour les vidéos à la demande, il est possible d'indiquer :

- un point de départ
- une durée

Exemples :

```text
01:12:30
12:30
90
```

Pour les lives, la capture peut commencer au moment où l'utilisateur clique sur le bouton d'enregistrement.

> Universal Downloader n'est pas conçu pour contourner les DRM ou les systèmes de chiffrement protégés.

---

### 🔗 Support des flux directs

Universal Downloader peut détecter et traiter directement certaines URL média sans passer par l'extracteur d'un site web.

Exemples :

```text
https://example.com/audio.mp3
https://example.com/live.m3u8
https://example.com/stream.mpd
```

Formats typiques reconnus :

```text
MP3
AAC
M4A
OGG
OPUS
WAV
FLAC
M3U8
MPD
```

**FFprobe** analyse le flux et **FFmpeg** assure l'enregistrement ou la conversion.

---

### 📋 File d'attente

La colonne de droite permet de gérer les téléchargements en cours et en attente.

Fonctions disponibles :

- ajout de plusieurs téléchargements
- traitement séquentiel
- progression en temps réel
- pause de la file
- reprise
- suppression des éléments en attente
- arrêt du téléchargement courant
- arrêt et vidage de la file
- journal d'activité détaillé

---

### 📊 Historique local

Universal Downloader peut mémoriser les téléchargements effectués.

Informations enregistrées :

- titre
- plateforme
- taille
- date
- URL source
- chemin du fichier

Actions disponibles depuis l'historique :

- **▶ Ouvrir le fichier**
- **📁 Afficher dans le dossier**
- **URL Copier l'URL source**
- **× Supprimer le fichier**

L'historique peut être désactivé dans l'interface.

---

### 🔄 Mise à jour intégrée de yt-dlp

Universal Downloader peut mettre à jour **yt-dlp directement depuis l'application**.

Deux canaux sont proposés :

```text
Stable
Nightly
```

#### Stable

Recommandé pour une utilisation normale.

#### Nightly

Reçoit plus rapidement les correctifs d'extracteurs lorsque YouTube, Vimeo ou d'autres plateformes modifient leur fonctionnement.

> Seul **yt-dlp** est mis à jour depuis l'application.  
> Universal Downloader lui-même est mis à jour manuellement via les Releases GitHub.

---

### 🧰 Diagnostic intégré

Le bouton **Diagnostic** vérifie la présence et la version des moteurs embarqués :

```text
yt-dlp
FFmpeg
FFprobe
Deno
```

Le diagnostic permet de repérer rapidement un problème lié aux outils internes.

---

## 🔒 Confidentialité YouTube

Universal Downloader possède un **Mode confidentialité YouTube**, activé par défaut.

Lorsqu'il est actif, l'application ignore pour YouTube :

- les cookies navigateur
- `cookies.txt`
- le User-Agent personnalisé
- l'impersonation Chrome

Le but est d'éviter d'associer inutilement un téléchargement à une session Google authentifiée.

> Ce mode ne rend pas la connexion anonyme.  
> L'adresse IP reste visible par les serveurs distants.

---

## 🔐 Options sites protégés / session

Certaines plateformes ou certains contenus peuvent nécessiter une session authentifiée.

Universal Downloader permet d'utiliser :

```text
Aucun
Firefox
Chrome
Edge
Brave
cookies.txt
```

### Cookies navigateur

Les cookies peuvent être utiles pour :

- contenu privé
- contenu réservé à un compte
- contenu soumis à une confirmation d'âge
- plateformes nécessitant une session valide

Pour les sites publics, Universal Downloader essaie d'éviter l'utilisation inutile des cookies.

Si la base de cookies Chrome / Edge / Firefox est verrouillée, l'application peut réessayer automatiquement **sans cookies** lorsqu'une extraction anonyme est possible.

---

### User-Agent

Le champ **User-Agent** permet de fournir manuellement une chaîne d'identification HTTP.

Exemple :

```text
Mozilla/5.0 (Windows NT 10.0; Win64; x64) ...
```

Dans la majorité des cas, il est recommandé de laisser ce champ vide.

---

### Impersonation Chrome

L'option **Impersonation Chrome** tente de reproduire davantage le comportement réseau d'un navigateur Chrome.

Elle peut aider avec certaines protections anti-bot ou certains CDN.

Pour un téléchargement normal :

```text
User-Agent : vide
Impersonation Chrome : désactivée
```

À utiliser uniquement si une plateforme bloque l'extraction standard.

---

## 🎞️ Vimeo

Vimeo peut nécessiter une session authentifiée pour certaines vidéos.

Si l'extraction anonyme échoue :

1. Se connecter à Vimeo dans Firefox, Chrome, Edge ou Brave.
2. Ouvrir **Options sites protégés / session**.
3. Sélectionner le navigateur utilisé.
4. Relancer l'analyse.

Si la base de cookies est verrouillée, fermer complètement le navigateur puis réessayer.

---

## 🌍 Plateformes

Universal Downloader est construit autour de **yt-dlp**.

Selon les extracteurs disponibles dans la version installée de yt-dlp, l'application peut fonctionner avec de nombreuses plateformes, notamment :

- YouTube
- Vimeo
- Dailymotion
- Facebook
- Instagram
- TikTok
- Twitter / X
- Twitch
- Reddit
- et de nombreux autres sites

> La compatibilité avec un site peut évoluer dans le temps.  
> Le bouton de mise à jour de yt-dlp permet de récupérer rapidement les correctifs d'extracteurs.

---

## 📦 Version portable

Universal Downloader est distribué sous forme d'une **archive ZIP portable Windows x64**.

### Aucun installateur

L'utilisateur télécharge l'archive, la décompresse et lance :

```text
UniversalDownloader.exe
```

Aucune installation système n'est nécessaire.

---

## ✅ Aucune dépendance à installer

La version portable contient tout ce qui est nécessaire.

L'utilisateur n'a pas besoin d'installer :

```text
Python
Node.js
npm
FFmpeg
FFprobe
Deno
yt-dlp
```

Les moteurs nécessaires sont inclus dans l'application.

---

## 📖 Guide d'utilisation

### 1. Télécharger et lancer l'application

1. Télécharger la dernière version portable depuis la page **Releases** de GitHub.
2. Décompresser complètement l'archive ZIP.
3. Ouvrir le dossier obtenu.
4. Lancer :

```text
UniversalDownloader.exe
```

> Il est recommandé de placer l'application dans un dossier où Windows autorise l'écriture.

---

### 2. Télécharger une vidéo

```text
1. Coller l'URL
2. Cliquer sur Analyser
3. Vérifier le titre et la miniature
4. Choisir un profil ou un format manuel
5. Cliquer sur Télécharger
```

Le téléchargement est ajouté à la file d'attente.

---

### 3. Télécharger uniquement l'audio

```text
1. Analyser l'URL
2. Choisir le profil MP3 192 ou MP3 320

ou

3. Ouvrir l'onglet Audio MP3
4. Choisir la piste
5. Télécharger
```

---

### 4. Télécharger la miniature

Après analyse :

```text
Télécharger miniature PNG
```

Le fichier est enregistré dans le dossier `UD_download`.

---

### 5. Capturer un live

```text
1. Coller l'URL du live
2. Analyser
3. Ouvrir Capture flux
4. Choisir Vidéo + Audio ou Audio uniquement
5. Démarrer la capture
6. Finaliser la capture lorsque nécessaire
```

---

## 📁 Dossiers portables

La structure finale ressemble à ceci :

```text
UniversalDownloader/
├── UniversalDownloader.exe
├── resources/
├── UD_download/
└── UD_data/
```

### `UD_download`

Dossier par défaut pour :

- vidéos
- audios
- captures de flux
- miniatures

Par défaut, il est créé **à côté de l'exécutable**.

Si l'application est déplacée sur un autre disque, le dossier par défaut suit automatiquement l'application.

L'utilisateur peut également sélectionner un autre dossier depuis l'interface.

---

### `UD_data`

Contient les données locales de l'application :

```text
settings.json
download_history.json
```

Ce dossier permet à Universal Downloader de rester réellement portable.

---

## 🖼️ Captures d'écran

Tu peux ajouter tes captures dans un dossier :

```text
docs/screenshots/
```

Puis utiliser par exemple :

```markdown
![Interface principale](docs/screenshots/main-interface.png)

![Profils de téléchargement](docs/screenshots/download-profiles.png)

![Capture de flux](docs/screenshots/stream-capture.png)

![Historique](docs/screenshots/history.png)
```

<!--
Exemple GitHub avec user-attachments :

<img width="1600" alt="Universal Downloader" src="https://github.com/user-attachments/assets/TON-ID" />
-->

---


## 🔐 Architecture de sécurité Electron

Universal Downloader sépare l'interface et le moteur Electron.

```text
Renderer HTML / CSS / JS
          ↓
      preload.js
          ↓
     IPC contrôlé
          ↓
      main.js
          ↓
yt-dlp / FFmpeg / FFprobe / Deno
```

Le renderer ne dispose pas d'un accès Node.js illimité.

Configuration Electron utilisée :

```text
nodeIntegration: false
contextIsolation: true
```

Les outils externes sont lancés avec des arguments contrôlés sans passer par un shell de commande libre.

---

### Cookies

Ne sélectionne un navigateur que si le site nécessite réellement une session.

Pour les contenus publics :

```text
Cookies : Aucun
```

est généralement le meilleur choix.

---

### Espace disque

Les téléchargements vidéo peuvent rapidement occuper beaucoup d'espace.

Le dossier par défaut est :

```text
UD_download
```

Tu peux déplacer les fichiers importants ailleurs après téléchargement.

---

## ⚠️ Limitations

Universal Downloader dépend du comportement des plateformes distantes.

Un site peut modifier à tout moment :

- son lecteur vidéo
- ses API
- ses protections anti-bot
- son authentification
- ses formats
- ses CDN

Une plateforme fonctionnant aujourd'hui peut donc nécessiter une mise à jour de yt-dlp demain.

Universal Downloader ne garantit pas la compatibilité permanente avec chaque site.

---

## ⚖️ Avertissement légal

Cet outil est fourni à des fins de convenance personnelle, d'archivage autorisé, de test et d'utilisation légitime.

Il est de la responsabilité de l'utilisateur de s'assurer qu'il possède le droit de télécharger ou d'enregistrer le contenu ciblé.

Veuillez respecter :

- les lois sur le droit d'auteur de votre pays
- les droits des créateurs
- les licences applicables
- les conditions d'utilisation des plateformes

Le développeur de cet outil ne peut être tenu responsable d'une utilisation illégale ou non autorisée.

Universal Downloader n'est pas destiné à contourner les DRM, les systèmes de chiffrement protégés ou les contrôles d'accès payants.

---

## 🔧 Composants utilisés

Universal Downloader s'appuie notamment sur :

- **Electron** — application desktop
- **yt-dlp** — extraction des informations et flux média
- **FFmpeg** — traitement, fusion et conversion audio/vidéo
- **FFprobe** — analyse des flux média
- **Deno** — runtime JavaScript utilisé pour certaines fonctions yt-dlp

Chaque composant tiers reste soumis à sa propre licence.

---

## 📝 Crédits

- **yt-dlp** — https://github.com/yt-dlp/yt-dlp
- **Electron** — https://www.electronjs.org/
- **FFmpeg** — https://ffmpeg.org/
- **Deno** — https://deno.com/

---

<div align="center">

### 🌟 Show Your Support

If this project helped you, please consider giving it a ⭐ on GitHub!

**by Orion4D**

<a href="https://ko-fi.com/orion4d">
<img src="https://ko-fi.com/img/githubbutton_sm.svg" alt="Buy Me A Coffee" height="41" width="174">
</a>

</div>
