## TP 4 - Gestion des paquets

### Exercice 1. Commandes de base

#### 1. Commencez par mettre à jour votre système avec les commandes vues dans le cours.

Pour mettre à jour le système à jour, on utilise la commande : sudo apt-get update && apt-get upgrade

#### 2. Créez un alias “maj” de la ou des commande(s) de la question précédente. Où faut-il enregistrer cet alias pour qu’il ne soit pas perdu au prochain redémarrage ?

Pour créer un alias on utilise la commande : alias maj='sudo apt-get update && apt-get upgrade'

Pour que cette alias soit enregistrer, il faut ecrire l'alias dans le fichier .bashrc.

![image](https://user-images.githubusercontent.com/80454458/192150423-a6a3d0c9-a2fb-4706-bb44-7b9714fce81d.png)


![image](https://user-images.githubusercontent.com/80454458/192150513-a3564989-d121-4c4b-9ed5-c69af721b93e.png)

#### 3. Utilisez le fichier /var/log/dpkg.log pour obtenir les 5 derniers paquets installés sur votre machine.

Pour obtenir les 5 derniers paquets installés sur votre machine on utilise la commande grep "installed" /var/log/dpkg.log | tail -n5

![image](https://user-images.githubusercontent.com/80454458/192150768-235abe51-fcbf-4dda-9781-6a6c08e3b200.png)

#### 4. Listez les derniers paquets qui ont été installés explicitement avec la commande apt install

Pour retrouver les derniers paquets installés avec la commande apt install on utilise la commande grep "apt install" /var/log/apt/history.log

![image](https://user-images.githubusercontent.com/80454458/192151073-8d9a45f5-07ab-48c1-92e5-1a854c5ba943.png)

#### 5. Utilisez les commandes dpkg et apt pour compter de deux manières différentes le nombre de total de paquets installés sur la machine (ne pas hésiter à consulter le manuel !). Comment explique-t-on la (petite) différence de comptage ? Pourquoi ne peut-on pas utiliser directement le fichier dpkg.log ?

Avec la commande dpkg:

![image](https://user-images.githubusercontent.com/80454458/191689730-21de2e77-0ebd-4761-8caf-fa3393291c4a.png)

Avec la commade apt:

![image](https://user-images.githubusercontent.com/80454458/191690033-0483dfc3-2a9d-47de-98b2-f7f9aaafbb93.png)

La différence de comptage viens de 

#### 6. Combien de paquets sont disponibles en téléchargement sur les dépôts Ubuntu ?

![image](https://user-images.githubusercontent.com/80454458/191690313-abbd88e5-6099-4ab4-b62a-563ab610f8b0.png)

#### 7. A quoi servent les paquets glances, tldr et hollywood ? Installez-les et testez-les.

glances:
Est un utilitaire qui permet d'afficher un maximum d'information dans un minimum de place ainsi que des informations supplémentaire.

tldr:
Est un utilitaire qui permet d'avoir des pages de manuel simplifiées et gérées par la communauté.

hollywood:
Permet de simuler une fenêtre de hacking comme au cinéma.

#### 8. Quels paquets proposent de jouer au sudoku ? 
N’installez pas le paquet gnome-sudoku ou ksudoku sous peine de devoir probablement réinstaller
votre VM

C'est la paquets ksudoku qui nous propose de jouer au sudoku

### Exercice 2.
#### A partir de quel paquet est installée la commande ls ? Comment obtenir cette information en une seule commande, pour n’importe quel programme ? Utilisez la réponse à cette question pour écrire un script appelé origine-commande (sans l’extension .sh) prenant en argument le nom d’une commande, etindiquant quel paquet l’a installée.

![image](https://user-images.githubusercontent.com/80454458/191694724-9206b3f5-845b-47cb-b4e6-5452aa0c35e3.png)

### Exercice 3.
#### Ecrire une commande qui affiche “INSTALLÉ” ou “NON INSTALLÉ” selon le nom et le statut du package spécifié dans cette commande.

![image](https://user-images.githubusercontent.com/80454458/192203036-91baf652-85c4-4b04-aa3b-16a3de9fb6d1.png)

### Exercice 4.
#### Lister les programmes livrés avec coreutils. En particulier, on remarque que l’un deux se nomme [. De

### Exercice 5. aptitude
#### Installez les paquets emacs et lynx à l’aide de la version graphique d’aptitude (et prenez deux minutes pour vous renseigner et tester ces paquets).

Le paquets emacs est un éditeurs de texte, mais également regarder des images ou lire des mails.

Le paquets lynx est un navigateur web en mode texte.

### Exercice 6. Installation d’un paquet par PPA
#### Certains logiciels ne figurent pas dans les dépôts officiels. C’est le cas par exemple de la version ”officielle” de Java depuis qu’elle est développée par Oracle. Dans ces cas, on peut parfois se tourner vers un ”dépôt personnel” ou PPA.

1. Installer la version Oracle de Java (avec l’ajout des PPA)
sudo add-apt-repository ppa:linuxuprising/java
sudo apt update
sudo apt install oracle-java15-installer

2. Vérifiez qu’un nouveau fichier a été créé dans /etc/apt/sources.list.d. Que contient-il ?

![image](https://user-images.githubusercontent.com/80454458/191698363-11b91d8b-4d57-4f96-99ec-7af456ee356d.png)

### Exercice 7. Installation d’un logiciel à partir du code source
#### Lorsqu’un logiciel n’est disponible ni dans les dépôts officiels, ni dans un PPA, ou encore parce qu’on souhaite n’installer qu’une partie de ses fonctionnalités, on peut se tourner vers la compilation du code source. C’est ce que nous allons faire ici, avec le programme cbonsai (https://gitlab.com/jallbrit/cbonsai)

1. Commencez par cloner le dépôt git suivant :
git clone https://gitlab.com/jallbrit/cbonsai
Ceci permet de récupérer en local le code source du logiciel cbonsai.

2. Rendez vous dans le dossier cbonsai. Un fichier README.md) est livré avec les sources, et vous explique
comment compiler le programme (vous pouvez installer un lecteur de Markdown pour Bash, comme
mdless pour vous faciliter la lecture de ce type de fichiers).
Un fichier Makefile est également présent. Un Makefile est un fichier utilisé par l’outil make, et
contient toutes les directives de compilation d’un logiciel. Un Makefile définit un certain nombre de
règles permettant de construire des cibles. Les cibles les plus communes étant install (pour la compilation et l’installation du logiciel) et clean (pour sa suppression).
En suivant les consignes du fichier README.md, et en installant les éventuels paquets manquants, compilez ce programme et installez le en local.
3. Malheureusement, cette installation “à la main” fait qu’on ne dispose pas des bénéfices de la gestion
de paquets apportés par dpkg ou apt. Heureusement, il est possible de transformer un logiciel installé
“à la main” en un paquet, et de le gérer ensuite avec apt ; c’est ce que permet par exemple l’outil
checkinstall.
4. Recommencez la compilation à l’aide de checkinstall :
sudo checkinstall
Un paquet a été créé (fichier xxx.deb), et le logiciel est à présent installé (tapez cbonsai depuis n’importe
quel dossier pour vous en assurer) ; on peut vérifier par exemple avec aptitude qu’il provient bien du paquet
qu’on a créé avec checkinstall.
Vous pouvez à présent profiter d’un instant de zenitude avant de passer au dernier exercice.
