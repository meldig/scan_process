# Documentation de filtre_BinSup_SmallFiles.py

Le script intervient à la fin du stage 2 de la chaîne de nettoyage des nuages de points. Il est chargé de trier les fichiers et de ne conserver que ceux qui sont intéressants.

## Constantes en entrée

- FILE_SIZE : Le taille limite des fichiers (en Ko). En dessous de cette limite, le fichier sera supprimé.
- DIR_PATH : Le chemin du dossier que l'on veut trier.

Ces constantes sont initialisées suite à l'appel de filtre_BinSup_SmallFiles.py en ligne de commande, l'appel ressemblera donc à ceci : 

``` bash
python filtre_BinSup_SmallFiles.py *FILE_SIZE* *DIR_PATH*
```

## Fonction SupBinAndLazFiles

Cette fonction permet de ne conserver que les fichiers avec l'extension .las, et donc de supprimer tous les autres.

On récupère tous les fichiers du dossier grâce à la fonction os.listdir, on itère ensuite sur ces fichiers et pour chacun on vérifie son extension.

## Fonction SupSmallFiles

Cette fonction permet de supprimer les fichiers dont la taille est inférieure à la limite fixée dans FILE_SIZE.

On itère cette fois ci sur tous les fichiers '.las' et pour chacun on vérifie sa taille.

On récupère la taille du fichier (en byte) grâce à la fonction os.path.getsize et on la divise deux fois par 1024 pour l'obtenir en Mo.