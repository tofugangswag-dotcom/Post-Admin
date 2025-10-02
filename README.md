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
cp .Coucou .. ou cp .Coucou /home/pepitodelanoche
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


## Exercice 3

### 1) Se placer dans le bon dossier
```bash
cd /home/pepitodelanoche/Fichier
```
- **cd** = *change directory* : se déplacer dans un répertoire.
- Chemin **absolu** (il commence par `/`), donc ça marche depuis n'importe où.
- Équivalent plus court : `cd ~/Fichier` (car `~` = ton *home*).

---

### 2) Créer le fichier et écrire un message
```bash
echo "mon message secret" > secret.txt
```
- **echo** affiche du texte.
- **`>`** redirige la sortie **vers un fichier** :
  - s'il **n'existe pas**, il est **créé** ;
  - s'il **existe**, il est **écrasé** (remplacé).
- Variante pour **ajouter** sans écraser : `>>`

Vérification possible :
```bash
cat secret.txt
```

---

### 3) Restreindre les permissions au propriétaire
```bash
chmod 600 secret.txt
```
- **chmod** : change les droits (permissions) du fichier.
- **600** = `rw-------`
  - **r** (read = lire), **w** (write = écrire), **x** (execute = exécuter)
  - **Propriétaire** : `rw` (lecture + écriture)
  - **Groupe** : `---` (aucun droit)
  - **Autres** : `---` (aucun droit)
- Équivalent en notation symbolique : `chmod u=rw,go= secret.txt`

---

### 4) Vérifier les droits du fichier
```bash
ls -l secret.txt
```
- **ls -l** : liste détaillée (droits, propriétaire, groupe, taille, date).
- Sortie attendue similaire à :
  ```
  -rw------- 1 pepitodelanoche pepitodelanoche 18 Oct  2 11:17 secret.txt
  ```
  - Le premier caractère `-` = fichier (vs `d` pour **d**ossier).
  - `rw-------` = droits correspondant à **600**.
  - Les deux champs suivants sont le **propriétaire** et le **groupe**.

------------------------------------------------------------------------

Screenshot : ![test3](https://i.imgur.com/0qwUoe0.png)


------------------------------------------------------------------------
