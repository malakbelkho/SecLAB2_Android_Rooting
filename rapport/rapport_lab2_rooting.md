# LAB 2 — Rooting Android

## 1. Fiche périmètre

| Élément | Valeur |
|---|---|
| Application testée | À compléter |
| Version de l’application | À compléter |
| Support | AVD Android |
| Version Android / API | À compléter |
| Objectif | Comprendre le rooting et ses impacts |
| Données utilisées | Données fictives uniquement |
| Réseau | Environnement de test isolé |
| Auteur | Malak BELKHO |
| Date | À compléter |

## 2. Définition du rooting

Le rooting consiste à obtenir les privilèges super-utilisateur sur un système Android.  
Ces privilèges permettent d’accéder à des zones normalement protégées du système.  
Dans un laboratoire, cela permet d’observer l’impact du root sur les contrôles d’intégrité, le stockage et le comportement runtime d’une application.  
Cette pratique reste risquée et doit être limitée à un environnement isolé, traçable et réinitialisable.

## 3. Résumé Android Security

Android repose sur plusieurs couches de sécurité.  
Chaque application fonctionne dans une sandbox qui l’isole des autres applications.  
Le modèle de permissions contrôle l’accès aux ressources sensibles.  
Le système protège aussi l’intégrité globale de la plateforme.  
Le rooting peut modifier ce modèle de confiance.  
Il doit donc être étudié uniquement dans un environnement de test.

## 4. Verified Boot et AVB

Verified Boot sert à vérifier que le système démarré n’a pas été modifié de manière non autorisée.  
La chaîne de confiance signifie que chaque composant vérifie le suivant avant de lui transférer l’exécution.  
L’intégrité au démarrage est critique, car si le boot est compromis, les protections Android peuvent être contournées avant même le lancement du système.

### Schéma simplifié

```text
ROM → Bootloader → Vérification signature → Boot image → Système Android → Applications
```