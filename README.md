# Jeu Du Juste Nombre – Compilation et exécution rapide

Ce projet contient un programme écrit en **langage C** ainsi qu’un script permettant de le compiler et de l’exécuter automatiquement sous **Windows**.

---

# Fichiers du projet

## `jeux.c`

C’est le fichier principal du programme.
Il contient le code source du jeu écrit en C.

Exemple minimal :

```c
#include <stdio.h>

int main() {
    printf("Bienvenue dans le jeu !\n");
    return 0;
}
```

Ce fichier doit être compilé pour créer un programme exécutable.

---

## `run.bat`

C’est un **script Windows** qui automatise deux actions :

1. Compiler le fichier `.c`
2. Exécuter le programme généré

Contenu du script :

```bat
gcc %1.c -o %1
if %errorlevel%==0 (
    %1.exe
)
```

---

# Prérequis

Avant d’utiliser ce projet, vous devez installer un compilateur C.

Par exemple **GCC avec MinGW ou MinGW-w64**.

Vérifiez que le compilateur est installé avec :

```bash
gcc --version
```

Si une version apparaît dans le terminal, tout est prêt.

---

# Utilisation

1. Ouvrir un **terminal (cmd ou PowerShell)**
2. Aller dans le dossier du projet

```bash
cd chemin\vers\le\dossier
```

3. Lancer la commande suivante :

```bash
run jeux
```

Le script va automatiquement :

* compiler `jeux.c`
* créer `jeux.exe`
* lancer le programme

---

# Fonctionnement

Le script utilise un paramètre (`%1`).

Exemple :

```
run jeux
```

Le script comprend :

* `jeux.c` → fichier à compiler
* `jeux.exe` → programme généré

Si une erreur de compilation apparaît, **le programme ne sera pas exécuté**.

---

# Structure du projet

```
projet/
│
├── jeux.c
├── run.bat
└── README.md
```

---

# Pourquoi utiliser ce système ?

Sans script :

```bash
gcc jeux.c -o jeux
jeux.exe
```

Avec le script :

```bash
run jeux
```

Moins de commandes, moins de friction, plus de temps pour coder.
