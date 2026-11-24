================================================================================
PROJET MY-LISP - CLAUDE Martin étudiant en L3 informatique
================================================================================

1. PRESENTATION

Ce projet consiste à créer un interpréteur en ligne de commande pour un
langage type My-Lisp, un peu inspiré par le langage Lisp.

Fonctionnalités :
- Opérations arithmétiques : +, -, *, /, ^
- Opérateurs logiques : and, or et not
- Operateurs de comparaison : =, !=, <, >, <=, >=
- Fonctions mathématiques : sqrt, log, exp, cos, sin
- Types gérés : int, double, boolean et listes homogènes
- Manipulation des listes : création (list ...), longueur <len>, somme <sum>
  et concaténation <+>
- Variables et types: typage donné ou explicite, constantes const et
  variables à type fixe typeconst
- Commandes possibles : symbols, delete <var>, quit
- Gestion des erreurs classées par catégorie : [Lexicale], [Syntaxique], [Sémantique]


2. STRUCTURE DU PROJET

.
├── Contribution_IA.pdf	    # PDF sur l'utilisation de l'IA dans le projet
├── README.txt              # Présentation, compilation et utilisation
├── Makefile                # Automatisation de la compilation
└── src/
    ├── lexer.l             # Analyse lexicale (Flex)
    ├── parser.y            # Analyse syntaxique et grammaire (Bison)
    ├── types.h / types.c   # Représentation des valeurs, de leur type et des listes
    ├── sym_table.h / .c    # Table des symboles (variables)
    ├── operations.h / .c   # Opérations arithmétiques, logiques, comparaisons et maths
    └── affichage.h / .c    # Affichage et messages d'erreurs
└── src_make/		    # Dossier généré par Makefile contenant les fichiers compilé
└── exemples/		    # Dossier contenant des exemples de fichier test pour l'interpreteur
    ├── ex1.txt
    ├── ex2.txt
    └── ex3.txt
    
3. COMPILATION

Le projet nécessite gcc, flex et bison.

Depuis la racine du projet :
- Compiler l'exécutable :
    make
  (Les fichiers générés par make sont placés dans le dossier src_make/
   et l'exécutable est créé dans le fichier courant)

- Nettoyer les fichiers générés :
    make clean

- Recompiler entièrement :
    make re


4. EXECUTION ET EXEMPLES

L'interpréteur propose deux modes d'exécution :

- Mode coercitif (conversions int -> double autorisées) :
    ./my-lisp

- Mode non coercitif (erreur sémantique si on mélange int / double) :
    ./my-lisp --non-coerce

Exemples d'utilisation dans le REPL :
    >> x = 10
    x = 10
    >> (+ x 2.5)
    12.5
    >> const int MAX = 100
    MAX = 100
    >> L = (list 1 2 3)
    L = [1, 2, 3]
    >> (sum L)
    6
    >> symbols
    >> quit
    
Vous pouvez également exécuter directement avec un fichier de teste :
    ./my-lisp < exemples/ex1.txt
    ./my-lisp < exemples/ex2.txt
    ./my-lisp < exemples/ex3.txt
