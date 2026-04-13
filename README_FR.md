# 🛡️ KMAC Anti-Cheat | Advanced Cybersecurity Solution

![Version](https://img.shields.io/badge/Version-1.0.0--RELEASE-red)
![Minecraft](https://img.shields.io/badge/Minecraft-1.21.10-green)
![Architecture](https://img.shields.io/badge/Architecture-Multi--Threaded-orange)
![License](https://img.shields.io/badge/License-Private-blue)

**KMAC** est une infrastructure de cybersécurité haute performance conçue pour remplacer les méthodes de détection obsolètes. Il se concentre sur la certitude mathématique et la simulation physique côté serveur. En déchargeant 95 % des calculs sur des threads asynchrones, KMAC garantit une stabilité à 20,0 TPS, même lors de scénarios de combat intensifs.

---

## 🚀 1. VISION DU PROJET
KMAC n'est pas un simple plugin de kick, c'est un moteur d'analyse de données. Il utilise la simulation physique 1:1 et l'analyse statistique pour différencier un joueur talentueux d'un utilisateur de triche (client de triche).

---

## 🏗️ 2. ARCHITECTURE CORE
### A. Moteurs Haute Performance
* **Calcul Asynchrone** : Des pools de threads dédiés gèrent la logique statistique complexe, évitant tout pic sur le Thread principal (Main Thread).
* **Smart Object Pooling** : Réutilisation intensive des vecteurs et des snapshots pour réduire la pression sur le Garbage Collector (GC) et éviter les pics de RAM.
* **Simulation Physique** : Moteur personnalisé répliquant la physique exacte de Minecraft (Gravité, Friction, Inertie, Traînée).
* **Compensation de Lag Réseau** : Historisation des positions des entités permettant une validation précise des coups basée sur la latence réelle du joueur (RTT).

### B. Logique de Sanction Intelligente
* **Corrélation Multi-Module** : Mise à l'échelle exponentielle du niveau de violation (VL) lorsque plusieurs modules signalent un joueur simultanément.
* **Scaling Réseau Dynamique** : Ajustement automatique de la sensibilité en fonction des TPS du serveur et de la stabilité de la connexion (Jitter/Ping) du joueur.
* **Mode Ghost** : Surveillance passive permettant la collecte de données silencieuse sans déclencher de kick ou de ban immédiat.

---

## 🔍 3. SUITE DE DÉTECTION (65 MODULES)

### CATÉGORIE COMBAT (43 MODULES)
* **AutoClicker (A-E)** : Détection des limites de CPS, de la cohérence du timing (Écart-type) et des motifs de clics mécaniques.
* **Reach (A-C)** : Validation par Ray-tracing de la distance de frappe, incluant la détection d'expansion de bounding-box.
* **KillAura & AimAssist** : Analyse des mouvements brusques (snap-aim), de la fluidité (smooth-aim), des rotations et des motifs d'attaque multi-cibles.
* **Velocity (A-B)** : Surveillance stricte des modificateurs de recul vertical et horizontal.
* **Criticals** : Détection de paquets illégaux et d'états au sol falsifiés (spoofed ground-states).

### CATÉGORIE MOUVEMENT (22 MODULES)
* **Flight & Glide** : Validation des vecteurs de mouvement verticaux et de la durabilité du temps de vol.
* **Speed** : Validation des coordonnées horizontales XZ par rapport à la friction au sol et aux effets de statut.
* **Scaffold** : Analyse des angles de placement par rapport à la rotation et à la cohérence du mouvement.
* **Blink** : Identification en temps réel de la rétention de paquets (packet choking).
* **Bypass Detection** : Neutralisation du Jesus (marche sur l'eau), Spider (escalade) et NoWeb.

---

## 📂 4. SYSTÈME FORENSIQUE (SHIELD SUPPORT)
KMAC inclut un outil d'expertise "Boîte Noire" pour les administrateurs.

### Black-Box Logging
Chaque bannissement génère un rapport d'incident détaillé dans `/internal/forensics/` incluant :
* Le module exact et le modèle ayant déclenché l'alerte.
* État du serveur (TPS, nombre de joueurs).
* État du réseau (Ping, Jitter, perte de paquets).
* Données du joueur (Coordonnées, Vélocité, fichiers de config actifs).

### Commande de Support : `/kmac support`
Génère un **Token de Support** sécurisé contenant :
* IP du serveur encodée en Base64.
* ID de session unique à 6 caractères.
* État de la configuration chiffré.
**Note :** Cette commande transmet automatiquement les fichiers `.yml` (`config`, `settings`, `checks`) au développeur via un canal sécurisé et doublement obfusqué pour un diagnostic rapide.

---

## 📜 5. CONDITIONS D'UTILISATION & POLITIQUES
**IMPORTANT : À lire attentivement avant le déploiement.**

### 1. Annulation du Support
Le support technique pour les "Faux Positifs" est strictement annulé si :
* **Décompilation** : Toute tentative de décompiler ou d'inverser l'ingénierie du plugin est détectée.
* **Altération de Configuration** : Le support n'est fourni que si `standard_optimized_config` est sur `true`. Tout ban survenant alors que cette variable est sur `false` relève de la seule responsabilité de l'administrateur.

### 2. Capacités de Surveillance
Nous possédons des outils forensiques propriétaires pour vérifier l'état exact de votre configuration au moment d'un ban. Nos logs suivent :
* Statut détaillé des modules (Activé/Désactivé).
* Contenu des fichiers à la microseconde de la sanction.
* Métadonnées côté serveur.

---

## ⌨️ COMMANDES ADMINISTRATIVES
* `/kmac` : Ouvre l'interface graphique (GUI) de gestion principale.
* `/kmac reload` : Recharge toutes les configurations.
* `/kmac config` : Ouvre le menu de configuration rapide.
* `/kmac debug` : Affiche la charge des threads, la taille des pools et les métriques de cache.
* `/kmac support` : Génère le jeton de diagnostic et transmet les fichiers de config.

---
**KMAC Anti-Cheat** *Le Silence de la Performance, le Poids de la Justice.* **Propriété exclusive de KrazyMan_off** **Distribué via Krazy Studio**
