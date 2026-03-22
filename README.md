# AVUASU PORT ET SAT — Transcription P2P en temps réel

> **Statut du projet :** Prototype fonctionnel

AVUASU PORTABLE ET SATELLITE est une application web légère de transcription parole-vers-texte conçue pour la communication en face à face.

Le système repose sur deux appareils :
- un téléphone **PORT-PAROLE**, qui capte la voix et lance la transcription ;
- un téléphone **SATELLITE**, qui reçoit et affiche le texte en grand format.

Cette version vise un déploiement simple, rapide et sans infrastructure applicative lourde.

---

## Fonctionnalités

- Transmission du texte en temps réel entre deux appareils
- Appairage rapide via QR Code
- Affichage haute lisibilité sur appareil secondaire
- Effacement automatique du texte en cas de rupture de connexion
- Déploiement statique en HTML, CSS et JavaScript

---

## Architecture

Le projet s’appuie sur deux pages principales :

### `index.html`
Interface maître utilisée sur le téléphone PORT-PAROLE :
- accès au microphone,
- lancement de la reconnaissance vocale,
- génération du QR Code,
- émission du texte vers l’appareil secondaire.

### `satellite.html`
Interface d’affichage utilisée sur le téléphone SATELLITE :
- réception du texte,
- affichage plein écran,
- remise à zéro de l’écran en cas de déconnexion.

### Technologies utilisées

- **Web Speech API** pour la transcription vocale
- **PeerJS / WebRTC** pour la communication entre appareils
- **QRCode.js** pour l’appairage
- **Vanilla JavaScript / CSS** pour une base légère et rapide

---

## Déploiement

L’application doit être hébergée sur un site sécurisé afin de permettre l’accès au microphone dans un navigateur moderne.

### Hébergement recommandé

- GitHub Pages
- Netlify
- tout hébergement statique avec HTTPS

### Mise en ligne

1. Déposer les fichiers du projet à la racine du dépôt
2. Publier le site via GitHub Pages ou Netlify
3. Vérifier que l’URL est bien accessible en `https://`
4. Tester l’accès au microphone sur le téléphone maître

---

## Utilisation

### 1. Préparer les appareils

- Ouvrir `index.html` sur le téléphone PORT-PAROLE
- Scanner le QR Code avec le téléphone SATELLITE
- Ouvrir automatiquement la page d’affichage

### 2. Connecter les appareils

Pour un usage stable, il est conseillé de connecter les deux téléphones au même réseau local, par exemple via le partage de connexion du téléphone maître.

### 3. Démarrer la transcription

- Autoriser l’accès au microphone
- Appuyer sur le bouton de capture vocale
- Parler normalement
- Lire le texte affiché sur le téléphone SATELLITE

---

## Prérequis techniques

### Navigateur

La reconnaissance vocale dépend du navigateur et de son niveau de support. En pratique, il est recommandé de tester en priorité :
- **Google Chrome sur Android**
- **Safari sur iPhone / iPad**

### Connexion Internet

Même si l’affichage entre appareils repose sur une liaison directe, le téléphone maître peut nécessiter une connexion Internet active pour la transcription vocale selon le navigateur utilisé.

### Autorisations

Lors du premier lancement, le navigateur demandera l’autorisation d’accéder au microphone.

---

## Limites connues

- Le support de la reconnaissance vocale varie selon les navigateurs
- La qualité de transcription dépend du bruit ambiant, du microphone et de la langue utilisée
- La stabilité de l’affichage dépend de la qualité de la connexion entre les deux appareils
- Cette version privilégie la simplicité de déploiement plutôt qu’un fonctionnement hors ligne complet

---

## Dépannage

### Le microphone ne fonctionne pas
- Vérifier que le site est bien ouvert en HTTPS
- Vérifier que l’autorisation micro a été acceptée
- Tester avec Chrome sur Android ou Safari sur iOS

### Le QR Code fonctionne mais l’affichage reste vide
- Vérifier que les deux appareils sont bien connectés
- Recharger la page Satellite
- Recréer une session depuis le téléphone maître

### La transcription est imprécise
- Réduire le bruit ambiant
- Parler plus près du microphone
- Vérifier la langue utilisée dans le navigateur ou dans la configuration du projet

---

## Feuille de route

Améliorations possibles :
- sélection de langue,
- mode tablette,
- personnalisation de l’affichage,
- meilleure gestion des états de connexion,
- historique local temporaire,
- optimisation des usages terrain.

---

## Licence

À compléter selon votre choix :
- MIT
- Apache-2.0
- licence propriétaire
