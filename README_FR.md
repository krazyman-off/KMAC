# 🚀 KM-PL | KrazyMan Performance & Lag-isolation

![Version](https://img.shields.io/badge/Version-1.1.0--STABLE-blue)
![Minecraft](https://img.shields.io/badge/Minecraft-1.21.10-green)
![Architecture](https://img.shields.io/badge/Architecture-Multi--Threaded-orange)
![GC-Status](https://img.shields.io/badge/GC--Intelligence-Active-brightgreen)

**KM-PL** est une suite logicielle de monitoring et d'optimisation de haute précision pour serveurs Minecraft. Contrairement aux outils classiques, KM-PL n'est pas un simple "limiteur" : c'est un **chirurgien du lag** capable d'isoler, de tracker et de brider les sources de charge en temps réel sans impacter la fluidité globale.

---

## 🛠️ Caractéristiques Principales

* **Pulse Tracking™** : Mesure ultra-précise du temps d'exécution des événements en nanosecondes.
* **Architecture GC-Free** : Code optimisé pour minimiser les allocations d'objets et éliminer les pics de Garbage Collection internes.
* **Cleaning Intelligence Engine** : Nouveau moteur de diagnostic capable de distinguer une charge normale d'une fuite de mémoire (Leak).
* **Isolation Sélective** : Permet de brider des chunks ou des entités spécifiques sans affecter le reste du monde.
* **Diagnostic Avancé** : Plus de 40 modules de monitoring (TPS réels, RAM Velocity, Efficacité GC, Threads, Paquets réseau).
* **Smart Support** : Système de rapports automatisés avec envoi de dumps techniques via Webhooks Discord.

---

## 🧠 Intelligence de Nettoyage (Nouveau v1.1)

Le module de gestion mémoire a été entièrement refondu pour passer d'une surveillance réactive à une **analyse prédictive** :

* **Memory Velocity (↑↓)** : Analyse en temps réel de la vitesse de remplissage de la RAM (ex: +33 MB/s). Permet d'anticiper un crash 2 minutes avant qu'il ne survienne.
* **GC Efficiency Tracking** : Calcule le "Delta" de RAM libérée à chaque passage du nettoyeur. Si l'efficacité est négative ou trop basse, KM-PL identifie une fuite mémoire.
* **Détection du GC Thrashing** : Alerte immédiate si le serveur passe plus de 15% de son temps processeur à essayer de libérer de la mémoire sans succès.
* **Seuils Dynamiques (%)** : Migration complète vers un système de seuils en pourcentage, rendant le plugin compatible avec n'importe quelle allocation RAM (de 2 Go à 128 Go+).

---

## 📂 Structure du Core

KM-PL s'appuie sur **46 modules** spécialisés, chargés dynamiquement pour garantir une empreinte mémoire minimale :

| Catégorie | Description |
| :--- | :--- |
| **Monitoring** | Surveillance TPS, RAM (Velocity), GC (Efficiency), Threads et Réseau. |
| **Analyse** | Détecteur de fuites de mémoire et analyseur de Hotspots (points chauds). |
| **Optimisation** | Gestion intelligente de l'IA, limitation des Hoppers et Redstone. |
| **Diagnostic** | Benchmark intégré et tableau de bord de santé prédictif. |

---

## ⌨️ Commandes Principales

Le plugin utilise une commande racine unique : `/kmpl`.

* `/kmpl top` : Affiche les événements les plus lourds (Profiler en temps réel).
* `/kmpl memory` : Affiche l'usage détaillé, la **Velocity** et le statut de santé.
* `/kmpl gc` : Rapport sur l'overhead et l'**Efficacité** du Garbage Collector.
* `/kmpl dashboard` : Interface visuelle de santé globale du serveur.
* `/kmpl support` : Génère un token et envoie un rapport complet vers votre Discord.

---

## ⚙️ Configuration

Les seuils sont désormais gérés en **pourcentages** pour une flexibilité totale :

```yaml
alert-system:
  # Seuil d'alerte critique (Déclenche le Watchdog et les mesures d'urgence)
  memory-critical-threshold-percent: 90.0
  # Seuil d'avertissement (Notification console et administrateurs)
  memory-warning-threshold-percent: 80.0
```
---

## 🧠 Philosophie de Développement

KM-PL est optimisé pour ne jamais devenir lui-même une source de lag :

* **Traitement Asynchrone** : 95% des calculs de statistiques sont déportés hors du thread principal pour garantir un impact nul sur les TPS.
* **Types Primitifs** : Utilisation intensive de types primitifs (int, long, double) pour éviter le coût de mémoire du boxing/unboxing Java.
* **Lazy Loading** : Les modules ne sont activés et chargés en mémoire que si nécessaire.
* **Zero-Allocation Path** : Les boucles critiques de monitoring sont conçues pour ne créer aucun objet temporaire, limitant ainsi la pression sur le Garbage Collector.

---

## 📞 Support & Contact

Ce plugin est un produit de la suite **KrazyStudio**. 

* Utilisez la commande `/kmpl support` pour toute demande technique.
* Le rapport généré inclut automatiquement l'état de la JVM, la liste des plugins actifs, ainsi que les tendances de performance récentes pour un diagnostic ultra-rapide.

---
> *Propulsé par KrazyMan Performance & Lag-isolation - 2026*
