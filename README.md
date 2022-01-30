# UNO partie 3 / 4 voire 5

- Codiscovery
- Live (mercredi 19h-21h) proposé par vous
  - Start from scratch
- Physionomie des lives
  - Questions/Suggestions/Changements appréciées à tout moment (Twitch/Youtube/FB)
  - A partir 21h, réponse à vos questions (avec ou sans rapports avec le live. Ex : le métier, les formations, quel langage/framework apprendre ?)
  - Partie 1 : explication, partie 2 : code
- Si vous aimez :
  - refaire le code vous même + review
  - parlez-en autour de vous :)

## Colors

white: [255, 255, 255],
red: [215, 38, 0],
blue: [9, 86, 191],
green: [55, 151, 17],
yellow: [236, 212, 7],
black: [0, 0, 0],

## Etapes

### Card, Hand

- [x] Créer une carte
- [x] Créer le dos d'une carte
- [x] Créer la face d'une carte
  - [x] Créer les cartes avec chiffres
  - [x] Créer les cartes avec icônes
- [x] Afficher la main (les 7 cartes) d'un joueur

### Dealer, Pot, Deck

- [x] Créer le dealer (celui qui distribue les cartes et gère la partie)
- [x] Générer toutes les cartes du jeu
- [x] Mélanger les cartes
- [x] Mélanger les cartes
- [x] Distribuer les cartes à tout le monde (et à la pioche)
- [x] Définir valeur en points de la carte
- [x] Afficher les cartes distribuées
  - [x] Afficher joueur 1
  - [x] Afficher joueur 2, 3 et 4
- [x] Créer la pioche
- [x] Afficher la pioche
- [x] Créer la pile centrale
- [x] Afficher la pile centrale

### Mécanique de jeu

- [x] Faire le tour de chaque joueur pour qu'ils déposent une carte
- [x] Afficher et démarquer le joueur qui joue
- [x] Vérifier qu'un joueur puisse jouer
- [x] Faire jouer les ordis la première possibilité
- [x] Proposer au joueur 1 les cartes possibles
- [x] Piocher si impossible
- [x] Remplir la pioche lorsqu'elle est vide
- [x] Gérer les effets après avoir jouer une carte
  - [x] Gérer le changement de sens
  - [x] Gérer le +2
  - [x] Gérer le changement de couleur
  - [x] Gérer le +4
- [x] Arrêter la partie quand un 1er joueur a gagné
- [x] Faire un total des points des cartes restantes
- [x] Afficher le message de fin (ordre) - Faire un leaderboard
- [x] Redémarrer une partie
- [x] Selectionner la carte que j'ai cliqué (et pas la 1ère possibilité)

### Mécanique de jeu (x2)

- Cas spéciaux non gérés
  - [x] Empecher de jouer 2 plus 2 d'affilés

### Multijoueur - une room

- [x] Utiliser Fastify
- [x] Installer socket.io
- [x] Créer un utilisateur
- [x] Enregistrer et diffuser la liste de tous les utilisateurs
- [x] Effacer un utilisateur à la déconnexion
- [x] Donner les droits au 1er participant de démarrer la partie
- [x] Créer une waiting room
- [x] Créer le visuel de la waiting room dans P5.js
- [x] Ajouter le bouton "Start" pour l'admin dans P5.js

- [x] Démarrer la partie avec le nombre de joueur en waiting room
- [x] Traiter côté serveur l'état du
  - [x] Dealer
  - [x] Deck
  - [x] Pot
  - [x] Player
- [x] Envoyer la carte jouée au serveur
  - [x] Enlever la carte du deck du joueur (normalement devrait être géré dans le dealerState)
- [x] Renvoyer l'état du jeu après chaque carte jouée
- [x] Afficher l'état du jeu pour chaque joueur

  - [x] Afficher la pioche mise à jour après avoir pioché
  - [x] Afficher le nombre de carte du joueur qui vient de jouer

- [x] Afficher le joueur qui doit jouer

- [x] Gérer les effets

  - [x] Changement de sens
  - [x] Sauter le tour
  - [x] Gérer le +2
  - [x] Gérer le changement de couleur
  - [x] Gérer le +4

- [x] Piocher une carte si je ne peux pas jouer
  - [x] Si la carte piochée est jouable, alors je la joue
  - [x] Si la carte piochée n'est jouable alors, je passe mon tour
  - [ ] Ajouter des TCL console.log pour essayer de comprendre le problème
  - [ ] Fix it

- [x] Empêcher que la première carte dans la pile centrale, soit une carte spéciale
- [x] Afficher "P1", "P2", etc, au lieu de playerId

- [x] Fix click outside card (create a bug)

- [x] Who's playing

  - [x] Moi qui joue ?
  - [x] Pas moi qui joue ?

- [ ] History

  - [x] Le placer du côté droit de l'écran, en bas des autres joueurs
  - [x] Voir le numéro de joueur qui joue (P1 is choosing a card)
  - [x] Gérer l'historique pour afficher le "P1", "P2" plutôt que le player ID
  - [x] Afficher les n tours précédents
    - "Le joueur P1 a joué un changement sens"
  - [ ] Fix le bug qui coupe le texte trop long
  - [ ] Finir d'ajouter toutes les intéractions

- [x] Créer un timer (côté serveur) pour passer le tour en jouant automatiquement

- [x] Se reconnecter à sa partie

  - [x] Créer un ID unique (hors Socket IO) pour l'utilisateur
  - [x] Si un joueur s'est déconnecté

    - [x] Si le joueur est déco, on le met dans l'historique

    - [x] On affiche le joueur en grisé
    - [x] l'ordi prend le dessus et joue pour lui
      - [x] Lorsque c'est au joueur ghosté de jouer, l'ordi joue
      - [x] Si le player ghosté, ne peut pas jouer alors il pioche et joue sa carte pioché ou pas (le faire passer par la méthode Dealer.giveDeckCardByPlayerId)

  - [x] Trouver un player par son ID d'utilisateur
  - [x] Enregistrer cet ID dans le localstorage
  - [x] Faire une recherche de l'utilisateur par cet ID et le relinker à la partie


- [ ] Redémarrer une partie
  - [x] Le serveur détecte la fin de partie
  - [x] Envoyer à tous les joueurs, le leaderboard
  - [x] Afficher le leaderboard
  - [x] Reset les états serveurs
  - [x] (10s après le leaderboard) Forcer les navigateurs à rafraîchir
  - [ ] Fix : replace player ID by P1, P2, P3

- [ ] Lorsqu'un joueur a joué, on remet les cartes dans le trousseau

- Bug
  - [ ] Dealer#isCurPlayerCanPlay
/Users/jenaic/Desktop/lives/multiplayer_uno/src/game/Player.js:173
        card.color === firstPossibility.color &&
                                        ^

TypeError: Cannot read properties of undefined (reading 'color')
    at /Users/jenaic/Desktop/lives/multiplayer_uno/src/game/Player.js:173:41
    at Array.findIndex (<anonymous>)
    at Player.playAutomatically (/Users/jenaic/Desktop/lives/multiplayer_uno/src/game/Player.js:171:38)
    at Dealer.giveDeckCardByPlayerId (/Users/jenaic/Desktop/lives/multiplayer_uno/src/game/Dealer.js:198:36)

### Multijoueur - multi room

- [ ] Créer une page de login (username)
- [ ] Créer une session simple : id => username, mis en cache côté client (localStorage vs. cookie ?)
- [ ] Page pour lister les rooms et la choisir

### Améliorations

- [ ] Jouer la carte que j'ai cliqué (pas la 1ère du lot si duplicata)
- [ ] Changer la couleur du cercle bleu pour que le joueur reconnaisse son avatar
- [ ] (Jade - Ja2rbk) Ajouter des animations sur la carte jouée et piochée
- [ ] (Gozer) Organiser la main par couleurs
- [ ] (ACdhirR) Nommer le jeu UNlimitedO (à voir puisque le jeu ne sera peut-être plus en joueur illimité, parce que l'attente est longue)
- [ ] (ACdhirR) Utiliser TS
- [ ] Optimiser toutes les boucles
  - [ ] Créer un environnement de test pour m'assurer que ça va plus vite
  - [ ] forEach/map/find en for
- [ ] Problème de selection de cartes
  - [ ] Possibilité de sélectionner la carte sur sa face
  - [ ] Possibilité de sélectionner la carte sur son bord haut qui apparait
- [ ] Dans le Player.selectColor() scale up (avec animtion) la carte couleur lorsqu'on fait un hover dessus
- [ ] Optimiser toutes les boucles map en for
- [ ] Définir le nombre de cartes à ajouter par utilisateur extra (pour une partie illimitée)
- [ ] Update signature from Dealer.giveCurPlayerDeckCard() to Dealer.giveCurPlayerDeckCard(numCardsToGive) pour envoyer 2 ou 4 cartes via une instructions
- [ ] Possibilité de passer un tour

- IDEE DE LIVES
  - Tower defense
  - Discord bot (le pendu)
  - Framer motion (animation)
