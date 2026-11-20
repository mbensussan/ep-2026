# 🐍 Épreuve Pratique NSI 2026 — Guide de prise en main

Bienvenue dans votre espace de travail en ligne pour la préparation à l'Épreuve pratique de Terminale NSI. Cet environnement est préconfiguré pour fonctionner directement dans votre navigateur, sans aucune installation requise sur votre ordinateur.

---

## 🛠️ 1. Initialisation de l'environnement (à faire au premier démarrage)

Lors de la toute première ouverture de votre espace de travail (Codespace), vous devez créer un environnement virtuel dédié et y installer les bibliothèques Python nécessaires aux sujets (comme `pillow` pour les images ou `matplotlib` pour les graphiques).

Si le **Terminal** n'est pas déjà ouvert en bas de l'écran, ouvrez le via le menu `Terminal > Nouveau terminal` et exécutez successivement les trois commandes ci-après. *Remarque.* Lors d'un copier-coller, une fenêtre de dialogue peut s’ouvrir : veuillez cliquer à chaque fois sur **Autoriser** pour fermer la fenêtre.

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

> **Remarque.** Une fenêtre de dialogue s'ouvre affichant « Vous avez peut-être installé des paquets Python dans votre environnement global, ce qui peut entraîner des conflits entre les versions des paquets. Voulez-vous créer un environnement virtuel avec ces packages pour isoler vos dépendances ? ».
> Cliquer sur le bouton **Ne plus afficher** pour fermer la fenêtre.

Pourquoi cette étape ?

La première commande crée un espace isolé (.venv), la deuxième l'active dans le terminal, et la troisième (pip) installe toutes les bibliothèques listées dans requirements.txt. Vous n'aurez besoin d'effectuer cette manipulation qu'une seule fois lors de la création de votre espace.


---

## 📂 2. Naviguer vers le dossier d'un sujet

Les 23 sujets sont rangés dans des dossiers distincts. Avant d'exécuter un script Python, il est indispensable de **se placer dans le bon dossier** afin que Python trouve correctement les fichiers annexes (images, fichiers `.csv`, fichiers `.txt`, etc.) utilisés par le sujet.

Utilisez la commande `cd` (*Change Directory* — changer de répertoire), par exemple pour le sujet 1 :

```bash
cd 26-01_codage_rle
```

> 💡 **Astuce de productivité : l'autocomplétion**  
> Vous n'avez pas besoin de taper le nom complet du dossier ! Tapez simplement `cd 26-01` puis appuyez sur la touche **`Tab`** (Tabulation) de votre clavier : le terminal complétera automatiquement le reste du nom.

*(Pour revenir au dossier principal si vous changez de sujet, tapez `cd ..`)*

---

## ▶️ 3. Exécuter votre code et lancer les tests

Une fois placé dans le répertoire de votre sujet, vous pouvez tester votre travail de deux manières complémentaires :

### A. Exécution simple du programme

Pour lancer votre script et observer l'affichage dans le terminal (les `print`, les erreurs éventuelles, etc.) :

```bash
python rle.py
```

*(Adaptez bien sûr le nom du fichier `.py` en fonction du sujet traité).*

### B. Validation avec les tests unitaires (`pytest`)

Comme nous le pratiquons en classe, utilisez `pytest` pour vérifier automatiquement que vos fonctions respectent bien le cahier des charges et passent tous les jeux de tests :

```bash
pytest -vv rle.py
```

> **Pourquoi l'option `-vv` ?**  
> Le drapeau `-vv` (*very verbose* — très verbeux) demande à `pytest` d'afficher un rapport d'exécution complet et détaillé. En cas d'échec d'un test, vous verrez précisément quelles valeurs étaient attendues et ce que votre fonction a réellement renvoyé.

---

## 📖 4. Consulter l'énoncé du sujet côte à côte

Vous pouvez ouvrir directement le fichier `.pdf` de l'énoncé dans l'éditeur en cliquant dessus dans l'explorateur de fichiers à gauche. Pour éviter de faire des allers-retours incessants entre l'énoncé et votre code, divisez l'écran en **deux panneaux côte à côte** :

1. Ouvrez d'abord votre fichier `.py` et votre fichier `.pdf` (ils apparaissent sous forme d'onglets en haut de la zone d'édition).
2. Cliquez sur l'onglet du fichier `.pdf`, maintenez le bouton de la souris enfoncé et **faites-le glisser** vers le bord droit (ou gauche) de l'éditeur jusqu'à voir apparaître une zone grisée sur la moitié de l'écran, puis relâchez.
3. *(Alternative rapide)* : Faites un **clic droit** sur l'onglet du fichier `.pdf` et choisissez **Fractionner à droite** (*Split Right*).

> 💡 **Astuce pour les écrans de Chromebook :**  
> Une fois vos deux panneaux ouverts, cliquez sur l'icône de l'explorateur de fichiers tout en haut à gauche (les deux feuilles superposées) ou appuyez sur `Ctrl + B` pour masquer le menu latéral et gagner un maximum de largeur de lecture.

---

## 💾 5. Sauvegarder son travail sur GitHub

Dans Codespaces, l'enregistrement automatique sauvegarde vos fichiers dans votre espace de travail temporaire, **mais ne les envoie pas encore sur votre compte GitHub**. À la fin de chaque séance (ou dès qu'un exercice est terminé), pensez à sauvegarder votre travail :

1. Cliquez sur l'icône **Contrôle de code source** (*Source Control*, l'icône avec des branches et un chiffre bleu) dans la barre latérale tout à gauche.
2. Dans la zone de texte **Message** située en haut, écrivez obligatoirement une courte étiquette décrivant votre travail (par exemple : `Sujet 01 RLE terminé` ou `Avancement séance 1`).
3. Cliquez sur le bouton bleu **Valider** (*Commit*). Si une fenêtre vous propose de « Voulez-vous indexer tous vos changements et les valider directement ? », cliquez sur **Toujours**.
4. Le bouton bleu devient **Synchroniser les modifications** (*Sync Changes*) : cliquez dessus pour envoyer définitivement votre code sur GitHub. Si une fenêtre vous s'affiche avec le message « Cette action permet d’extraire et d’envoyer (push) les validations à partir de et vers « origin/main ». », cliquer sur le bouton **OK, ne plus afficher**.

> **Vérification :** Le chiffre bleu sur l'icône Contrôle de code source disparaît. Votre travail est en sécurité sur votre dépôt GitHub, même si vous fermez votre Chromebook !

Bon travail et bonnes révisions ! 🚀

---

> *Transparence : la configuration de cet espace Codespaces et la rédaction de ce guide ont été élaborées en collaboration avec l'IA (Gemini), puis testées et validées par votre enseignant.*