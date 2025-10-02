# README

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

Screenshot : ![test](https://i.imgur.com/VVm7VjP.png)


------------------------------------------------------------------------


## Exercice 2

### 1) Lister `/etc` dans `log.txt`
```bash
ls /etc > log.txt
```
- `>` redirige la sortie de la commande vers le fichier `log.txt` (il sera créé s’il n’existe pas).

### 2) Ajouter les 10 dernières lignes du syslog
```bash
tail -n 10 /var/log/syslog >> log.txt
```
- `tail -n 10` prend les 10 dernières lignes.
- `>>` **ajoute** à la fin de `log.txt` (n'écrase pas).

### 3) Afficher uniquement les lignes contenant "error"
```bash
grep -i "error" log.txt
```
- `-i` ignore la casse (`error`, `Error`, `ERROR`).


------------------------------------------------------------------------

Screenshot : ![test2](https://i.imgur.com/YOE50Zk.png)


------------------------------------------------------------------------

