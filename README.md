# My-Lisp — Interpréteur en mode REPL

Interpréteur en ligne de commande pour le langage **My-Lisp** (inspiré de la syntaxe préfixée de Lisp), développé en **C** avec **Flex** et **Bison**.

*Projet réalisé par Martin Claude — L3 Informatique (Université Jean Monnet)*

---

## Fonctionnalités

* **Opérations arithmétiques :** `+`, `-`, `*`, `/`, `^` (avec `+` et `*` à arité variable, et `-` unaire)
* **Opérateurs logiques :** `and`, `or` (arité variable) et `not`
* **Opérateurs de comparaison :** `=`, `!=`, `<`, `>`, `<=`, `>=`
* **Fonctions mathématiques :** `sqrt`, `log`, `exp`, `cos`, `sin`
* **Types gérés :** `int`, `double`, `bool` et listes 1D homogènes (`list`)
* **Manipulation des listes :** création `(list ...)`, longueur `(len ...)`, somme `(sum ...)` et concaténation `(+ ...)`
* **Variables et portée :** typage inféré ou explicite, constantes (`const`) et variables à type fixe (`typeconst`)
* **Commandes du REPL :** `symbols`, `delete <var>`, `quit`
* **Gestion des erreurs :** messages explicites classés par catégorie (`[Lexicale]`, `[Syntaxique]`, `[Sémantique]`) sans interruption de session

---

## Structure du projet

```text
.
├── README.md               # Présentation, compilation et utilisation
├── Makefile                # Automatisation de la compilation
├── src/
│   ├── lexer.l             # Analyse lexicale (Flex)
│   ├── parser.y            # Analyse syntaxique et grammaire (Bison)
│   ├── types.h / types.c   # Représentation des valeurs, des types et des listes
│   ├── sym_table.h / .c    # Table des symboles (variables, const, typeconst)
│   ├── operations.h / .c   # Opérations arithmétiques, logiques, comparaisons et maths
│   └── affichage.h / .c    # Affichage des résultats et messages d'erreurs
└── exemples/               # Jeux de tests pour l'interpréteur
    ├── ex1.txt
    ├── ex2.txt
    └── ex3.txt
