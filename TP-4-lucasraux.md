## TP 4 - Gestion des paquets

### Exercice 1. Commandes de base

#### 1. Commencez par mettre à jour votre système avec les commandes vues dans le cours.

Pour mettre à jour le sustème on utilise la commande : sudo apt-get update && apt-get upgrade

#### 2. Créez un alias “maj” de la ou des commande(s) de la question précédente. Où faut-il enregistrer cet alias pour qu’il ne soit pas perdu au prochain redémarrage ?

Pour creer un alias on utilise la commande : alias maj='sudo apt-get update && apt-get upgrade'

Pour que cette alias soit enregistrer, il faut ecrire l'alias dans le fichier .bashrc

#### 3. Utilisez le fichier /var/log/dpkg.log pour obtenir les 5 derniers paquets installés sur votre machine.



#### 4. Listez les derniers paquets qui ont été installés explicitement avec la commande apt install

#### 5. Utilisez les commandes dpkg et apt pour compter de deux manières différentes le nombre de total de paquets installés sur la machine (ne pas hésiter à consulter le manuel !). Comment explique-t-on la (petite) différence de comptage ? Pourquoi ne peut-on pas utiliser directement le fichier dpkg.log ?

Avec la commande dpkg:

![image](https://user-images.githubusercontent.com/80454458/191689730-21de2e77-0ebd-4761-8caf-fa3393291c4a.png)

Avec la commade apt:
![image](https://user-images.githubusercontent.com/80454458/191690033-0483dfc3-2a9d-47de-98b2-f7f9aaafbb93.png)

#### 6. Combien de paquets sont disponibles en téléchargement sur les dépôts Ubuntu ?

![image](https://user-images.githubusercontent.com/80454458/191690313-abbd88e5-6099-4ab4-b62a-563ab610f8b0.png)

#### 7. A quoi servent les paquets glances, tldr et hollywood ? Installez-les et testez-les.

#### 8. Quels paquets proposent de jouer au sudoku ? 
N’installez pas le paquet gnome-sudoku ou ksudoku sous peine de devoir probablement réinstaller
votre VM

C'est la paquets ksudoku qui nous propose de jouer au sudoku
