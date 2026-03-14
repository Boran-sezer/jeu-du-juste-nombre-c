# 🎯 Jeu du Juste Nombre (C)

Petit jeu en **langage C** où le joueur doit deviner un **nombre aléatoire** généré par l’ordinateur.

Le programme donne des indices pour aider le joueur :

* **"C'est plus !"** → le nombre mystère est plus grand
* **"C'est moins !"** → le nombre mystère est plus petit

Le jeu continue jusqu’à ce que le bon nombre soit trouvé. Une fois la partie terminée, le joueur peut choisir de **rejouer**.

---

# 🧠 Principe du jeu

1. L’ordinateur génère un nombre aléatoire entre **1 et 100**
2. Le joueur propose un nombre
3. Le programme indique si le nombre mystère est plus grand ou plus petit
4. Le joueur recommence jusqu’à trouver la bonne réponse
5. Une fois trouvé, le joueur peut lancer une nouvelle partie

---

# 📂 Fichiers du projet

```text
projet/
│
├── jeux_du_juste_nombre.c
├── run.bat
└── README.md
```

### `jeux.c`

Ce fichier contient **le code source du jeu**.

Le programme utilise plusieurs éléments du langage C :

* génération d’un nombre aléatoire
* boucle de jeu
* interaction avec l’utilisateur dans le terminal
* possibilité de recommencer une partie

---

### `run.bat`

Script Windows permettant de **compiler et exécuter automatiquement le programme**.

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
3. lance le programme si la compilation réussit

---

# ⚙️ Prérequis

Installer un compilateur C sur Windows.

Par exemple **GCC avec MinGW ou MinGW-w64**.

Pour vérifier que l’installation fonctionne :

```bash
gcc --version
```

Si une version apparaît dans le terminal, le compilateur est correctement installé.

---

# ▶️ Lancer le jeu

Ouvrir un **terminal** dans le dossier du projet.

Puis exécuter :

```bash
run jeux_du_juste_nombre
```

Le script va automatiquement :

1. compiler `jeux_du_juste_nombre.c`
2. créer `jeux_du_juste_nombre.exe`
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

Le programme initialise le générateur de nombres aléatoires avec :

```c
srand(time(NULL));
```

Puis il génère un nombre entre **1 et 100** :

```c
nombreMystere = (rand() % (MAX - MIN + 1)) + MIN;
```

Une boucle `do...while` gère les tentatives du joueur jusqu’à ce que le bon nombre soit trouvé.

Une seconde boucle permet de **rejouer une nouvelle partie** si le joueur choisit de continuer.

---

# 💡 Améliorations possibles

Quelques idées pour améliorer ce projet :

* ajouter un **compteur de tentatives**
* ajouter un **mode difficile (1 à 1000)**
* limiter le **nombre d’essais**
* ajouter des **couleurs dans le terminal**
* créer une **interface graphique**

---

# 📜 Licence

Projet libre pour l’apprentissage du langage **C**.
