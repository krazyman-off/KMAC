# 🚀 KM-PL | KrazyMan Performance & Lag-isolation

![Version](https://img.shields.io/badge/Version-1.0.0--RELEASE-blue)
![Minecraft](https://img.shields.io/badge/Minecraft-1.21.10-green)
![Architecture](https://img.shields.io/badge/Architecture-Multi--Threaded-orange)
![License](https://img.shields.io/badge/License-Private-red)

**KM-PL** est une suite logicielle de monitoring et d'optimisation de haute précision pour serveurs Minecraft. Contrairement aux outils classiques, KM-PL n'est pas un simple "limiteur" : c'est un **chirurgien du lag** capable d'isoler, de tracker et de brider les sources de charge en temps réel sans impacter la fluidité globale.

---

## 🛠️ Caractéristiques Principales

* **Pulse Tracking™** : Mesure du temps d'exécution des événements en nanosecondes.
* **Architecture GC-Free** : Conçu pour minimiser les allocations d'objets et éviter les pics de Garbage Collection.
* **Isolation Sélective** : Bride les chunks ou les entités problématiques de manière isolée.
* **Diagnostic Avancé** : Plus de 40 commandes de monitoring (TPS, RAM, GC, Threads, Network, Hoppers, Redstone).
* **Export de Données** : Compatible Prometheus et export JSON pour une visualisation externe.
* **Smart Support** : Système de diagnostic à distance avec envoi de rapports automatisés sur Discord.

---

## 📂 Structure du Core

Le plugin est articulé autour de **46 modules** spécialisés, chargés dynamiquement pour optimiser l'empreinte RAM :

| Catégorie | Description |
| :--- | :--- |
| **Monitoring** | Surveillance TPS, RAM, GC, Threads et Paquets réseau. |
| **Analyse** | Détection de fuites de mémoire (Leak Detector) et analyseur de Hotspots. |
| **Optimisation** | Gestion intelligente de l'IA, des Hoppers et des circuits Redstone. |
| **Diagnostic** | Benchmark de performance intégré et tableau de bord de santé. |

---

## ⌨️ Commandes Principales

Le plugin utilise une commande racine unique : `/kmpl`.

* `/kmpl top` : Affiche les événements les plus lourds (Profiler).
* `/kmpl chunks` : Identifie les zones de lag géographique.
* `/kmpl dashboard` : Ouvre l'interface de santé globale.
* `/kmpl health` : Diagnostic rapide du serveur.
* `/kmpl support` : Génère un token et envoie un rapport complet (Webhooks Discord).
* `/kmpl reload` : Recharge la configuration à chaud.

---

## ⚙️ Installation

1. Glissez le fichier `KM-PL.jar` dans votre dossier `plugins/`.
2. Redémarrez votre serveur.
3. Configurez les seuils d'alerte dans `plugins/KM-PL/config.yml`.
4. (Optionnel) Configurez le Webhook Discord dans `settings.yml` pour le support.

---

## 🧠 Philosophie de Développement

KM-PL est optimisé **"à la mort"**. Chaque module est géré via une `Map` de services et un système de **Lazy Loading** pour garantir que le plugin n'impacte jamais les performances qu'il est censé protéger.
* **Priorité Monitor** sur les listeners pour une observation non-intrusive.
* **Traitement Asynchrone** des statistiques et des rapports de support.
* **Utilisation de types primitifs** pour éviter le boxing/unboxing coûteux.

---

## 📞 Support & Contact

Ce plugin fait partie de la suite **KrazyStudio**. Pour toute demande de support technique ou rapport de bug :
* Utilisez la commande `/kmpl support` pour générer un dump technique.
* Le rapport inclura automatiquement votre configuration et l'état actuel de votre JVM.

---
> *Propulsé par KrazyMan Performance & Lag-isolation - 2026*
