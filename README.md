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
**# 🎯 Jeu du Nombre Mystère (C)

Petit jeu en **langage C** dans lequel le joueur doit deviner un **nombre aléatoire** généré par l’ordinateur.

Le programme donne des indices :

* **"C'est plus !"** → le nombre mystère est plus grand
* **"C'est moins !"** → le nombre mystère est plus petit

Le jeu continue jusqu’à ce que le joueur trouve le bon nombre.

---

# 🧠 Principe du jeu

1. L’ordinateur génère un nombre aléatoire entre **1 et 100**.
2. Le joueur propose un nombre.
3. Le programme indique si le nombre mystère est :

   * plus grand
   * plus petit
4. Le joueur recommence jusqu’à trouver la bonne réponse.
5. Une fois trouvé, le joueur peut **rejouer une nouvelle partie**.

---

# 📂 Fichiers du projet

```
projet/
│
├── jeux.c
├── run.bat
└── README.md
```

### `jeux.c`

Contient **le code du jeu**.

Fonctionnalités principales :

* génération d’un nombre aléatoire (`rand`)
* boucle de jeu
* système pour **rejouer une partie**
* interaction avec l’utilisateur via le terminal

---

### `run.bat`

Script Windows permettant de **compiler et exécuter le jeu automatiquement**.

Contenu du script :

```bat
gcc %1.c -o %1
if %errorlevel%==0 (
    %1.exe
)
```

Ce script :

1. compile le fichier `.c`
2. crée le fichier `.exe`
3. lance le programme si la compilation fonctionne

---

# ⚙️ Prérequis

Installer un compilateur C :

* **GCC avec MinGW ou MinGW-w64**

Tester dans le terminal :

```
gcc --version
```

Si une version apparaît, le compilateur est correctement installé.

---

# ▶️ Lancer le jeu

Ouvrir un **terminal** dans le dossier du projet.

Puis exécuter :

```
run jeux
```

Le script va automatiquement :

1. compiler `jeux.c`
2. créer `jeux.exe`
3. lancer le jeu

---

# 🎮 Exemple de partie

```
--- NOUVELLE PARTIE ---
Quel est le nombre ? 50
C'est plus !

Quel est le nombre ? 75
C'est moins !

Quel est le nombre ? 63
Bravo, tu as trouve !

Voulez-vous rejouer ? (1 pour OUI, 0 pour NON) :
```

---

# 🔧 Fonctionnement du code

Le programme utilise plusieurs concepts fondamentaux du C :

### Génération aléatoire

```
srand(time(NULL));
```

Initialise le générateur de nombres aléatoires.

Puis :

```
nombreMystere = (rand() % (MAX - MIN + 1)) + MIN;
```

Génère un nombre entre **1 et 100**.

---

### Boucle de jeu

Une boucle `do...while` permet :

* de demander un nombre au joueur
* de vérifier s’il est correct
* de donner un indice

---

### Rejouer une partie

Une seconde boucle `do...while` permet de **relancer une nouvelle partie** si le joueur entre `1`.

---

# 💡 Améliorations possibles

Quelques idées pour améliorer le jeu :

* ajouter un **compteur de tentatives**
* ajouter un **mode difficile (1-1000)**
* limiter le **nombre d’essais**
* ajouter des **couleurs dans le terminal**
* créer une **interface graphique**

---

# 📜 Licence

Projet libre pour l’apprentissage du langage **C**.
