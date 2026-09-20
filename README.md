# Jeu de dames — Java

## Contexte
Projet réalisé dans le cadre du module de Modélisation et Programmation Orientée
Objet, visant à traduire les règles du jeu de dames en une architecture logicielle
claire, modulaire et évolutive.

## Règles implémentées
- Plateau 8x8, 12 pièces par joueur
- Déplacement diagonal des pions vers l'avant
- Capture obligatoire, avec prises multiples
- Promotion en dame à la dernière rangée, avec déplacement longue distance dans toutes les directions
- Fin de partie : victoire, blocage ou match nul

## Fonctionnalités additionnelles
- Mise en surbrillance des déplacements possibles
- Bordure rouge sur les pions devant obligatoirement capturer
- Effets sonores (déplacements, victoire)
- Annonce du joueur gagnant

## Architecture (MVC)
- **Modèle** : `Plateau` (état du damier 8x8 et logique du jeu), `Piece` (classe abstraite) avec `Pion` et `Dame` (héritage/polymorphisme), `Position` (coordonnées immuables), énumérations `Couleur` et `TypePiece`
- **Vue** : `PlateauDeJeu` (hérite de `JPanel`), affiche le plateau, les pièces, les sélections et les messages
- **Contrôleur** : `JeuDeDamesGUI` (JFrame principal), gère les événements utilisateur et orchestre modèle/vue, utilise `SoundManager` (méthodes statiques) pour les effets sonores

> Remarque : ces classes sont organisées conceptuellement selon le patron MVC, mais actuellement regroupées dans un seul fichier `JeuDeDamesGUI.java` (une classe publique + classes non publiques dans le même fichier).

## Stack technique
- **Langage** : Java (POO)
- **Interface graphique** : java.awt (Color, Graphics, Graphics2D, Dimension, Font, BorderLayout), javax.swing (JFrame, JPanel, JLabel, SwingUtilities)
- **Interactions souris** : java.awt.event (MouseEvent, MouseAdapter)
- **Son** : javax.sound.sampled (AudioInputStream, AudioSystem, Clip)
- **Structures de données** : java.util (ArrayList, List)

## Installation et lancement
\`\`\`bash
git clone https://github.com/<ton-user>/jeu-de-dames-java.git
cd jeu-de-dames-java
javac JeuDeDamesGUI.java
java JeuDeDamesGUI
\`\`\`

## Structure du projet
\`\`\`
jeu-de-dames-java/
├── JeuDeDamesGUI.java   # Modèle + Vue + Contrôleur + SoundManager (voir section Architecture)
├── sounds/              # fichiers audio (.wav) pour les effets sonores
└── README.md
\`\`\`

## Pistes d'amélioration
- Séparer les classes en fichiers distincts (un fichier par classe) pour une meilleure lisibilité et testabilité
- Ajouter un mode contre l'ordinateur (IA)
- Passer d'une version console à une interface graphique enrichie *(si applicable selon ta version finale)*

## Captures d'écran
_(à ajouter : plateau de jeu, mise en surbrillance des coups, fin de partie)_

## Auteur
Wiam — Étudiante en géoinformatique, FST Tanger (projet réalisé en équipe)