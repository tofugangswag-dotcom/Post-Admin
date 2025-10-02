# README -- Exercice 1

## Exercice 1

### 1. Afficher le répertoire courant

``` bash
pwd
```

Affiche le chemin complet du répertoire où l'on se trouve.

------------------------------------------------------------------------

### 2. Créer un répertoire `files`

``` bash
mkdir Fichier
cd Fichier
```

Crée un dossier `Fichier` et on se place dedans.

------------------------------------------------------------------------

### 3. Créer 3 fichiers (dont 1 caché)

``` bash
touch Hello
touch Adieu
touch .Coucou
```

-   `Hello` et `Adieu` sont des fichiers normaux.\
-   `.Coucou` est un fichier **caché** (le point devant le nom le rend
    invisible avec `ls`, sauf si on fait `ls -a`).

------------------------------------------------------------------------

### 4. Copier un des fichiers dans le répertoire courant et le renommer

Depuis `~/fichier`, on copie le fichier caché `.Coucou` dans le répertoire
parent (le home dans ce cas) :

``` bash
cp .Coucou ..
```

Ensuite, dans le répertoire courant (home), on le renomme :

``` bash
mv .Coucou .Coucoucou
```

------------------------------------------------------------------------

Screenshot : ![(https://imgur.com/VVm7VjP)]
