# Planification du premier Sprint :

## -Les pré-/post-conditions- :

## 1. **Gestion des alimentations animaux :**

**Précondition** : Avoir suffisamment d'espace pour les enclos ∧ disposer d'une source d'eau suffisante ∧ avoir des fonds pour l'achat d'animaux, de nourriture et de fournitures pour leur entretien.

  ***Postcondition :*** Avoir des animaux en bonne santé et bien nourris ∧ des enclos propres et entretenus ∧ une production d'animaux vendables pour générer des revenus.
  

## **2. Gestion des cultures :**

***Précondition :*** Avoir suffisamment de terre pour planter les cultures ∧ disposer d'une source d'eau suffisante pour irriguer les cultures ∧ avoir des fonds pour l'achat de semences et d'outils de jardinage. 

***Postcondition :*** Avoir des cultures en bonne santé ∧ une production de produits agricoles vendables pour générer des revenus, et un stockage adéquat des produits récoltés

## **-Table de décision des tests de validation- :**



## 1. Gestion des alimentations animaux :


| Fonctionnalités | Test 1  | Test 2 | Test 3|Test4
|--|--|--|--|--|
| Avoir suffisamment d'espace pour le enclos | F |T|T|T
|Disposer d'une source d'eau suffisante | |F|T|T
|Avoir des fonds pour l'achat d'animaux, nourritures et fournitures pour l'entretien|||F|T
|Bonne gestion des alimentations des animaux|F|F|F|T
|Nombre de jeux de tests|2|2xn|1|1

## **2. Gestion des cultures :**

| Fonctionnalités | Test 1  | Test 2 | Test 3|Test4
|--|--|--|--|--|
|Avoir suffisamment de terre pour planter les cultures | F |T|T|T
|Disposer d'une source d'eau suffisante pour irriguer les culture| |F|T|T
|Avoir des fonds pour l'achat de semences et d'outils de jardinage.|||F|T
|Bonne gestion des culture|F|F|F|T
|Nombre de jeux de tests|2|2xn|1|1
-------------------------------------------------------------------------
-------------------------------------------------------------------------
-------------------------------------------------------------------------
## **Aspect Statique : Diagramme de Classes :**
|  Classe| Atrributs|Operations
|--|--|--|
| Joueur |id_joueur : l'identifiant unique du joueur nom_joueur : le nom du joueur. argent : l'argent du joueur. enclos : une liste des enclos appartenant au joueur entrepots : une liste des entrepôts appartenant au joueur. cultures : une liste des cultures appartenant au joueur. | acheter_produit(culture: Culture, quantite: float, prix: float): cette méthode permet à un joueur d'acheter un certain nombre de produits d'une culture donnée à un certain prix. vendre_produit(culture: Culture, quantite: float, prix: float): cette méthode permet à un joueur de vendre un certain nombre de produits d'une culture donnée à un certain prix acheter_animal(animal: Animal, enclos: Enclos): cette méthode permet à un joueur d'acheter un animal et de le placer dans un enclos. vendre_animal(animal: Animal): cette méthode permet à un joueur de vendre un animal. ajouter_culture(culture: Culture, surface: float): cette méthode permet à un joueur d'ajouter une culture avec une certaine surface. supprimer_culture(culture: Culture): cette méthode permet à un joueur de supprimer une culture.
|Animal	|id_animal : l'identifiant unique de l'animal nom_animal : le nom de l'animal. age : l'âge de l'animal. sexe : le sexe de l'animal. poids : le poids de l'animal. prix_achat : le prix d'achat de l'animal. prix_vente : le prix de vente de l'animal|nourrir(): cette méthode permet de nourrir l'animal en question. soigner(): cette méthode permet de soigner l'animal en question. vendre(): cette méthode permet de vendre l'animal en question. reproduire(): cette méthode permet à l'animal en question de se reproduire avec un autre animal de même espèce et de créer un nouvel animal de cette espèce
|Culture|id_culture : l'identifiant unique de la culture nom_culture : le nom de la culture. surface : la surface de la culture. date_plantation : la date de plantation de la culture. date_recolte : la date de récolte de la culture. prix_achat : le prix d'achat de la culture. prix_vente : le prix de vente de la culture.|arroser(): cette méthode permet d'arroser la culture en question. fertiliser(): cette méthode permet de fertiliser la culture en question. vendre(): cette méthode permet de vendre la culture en question. recolter(): cette méthode permet de récolter la culture en question.
Entrepôt|id_entrepot : l'identifiant unique de l'entrepôt nom_entrepot : le nom de l'entrepôt. capacite_max : la capacité maximale de stockage de l'entrepôt. produits : un dictionnaire qui contient les produits stockés et leur quantité |ajouter_produit(culture: Culture, quantite: float): cette méthode permet d'ajouter un certain nombre de produits d'une culture donnée à l'entrepôt. retirer_produit(culture: Culture, quantite: float): cette méthode permet de retirer un certain nombre de produits d'une culture donnée de l'entrepôt.
Enclos |id_enclos : l'identifiant unique de l'enclos dans la base de données. nom_enclos : le nom de l'enclos. surface : la surface de l'enclos. capacite_max : la capacité maximale d'animaux que peut contenir l'enclos. animaux : une liste d'animaux contenus dans l'enclos.|ajouter_animal(animal: Animal): cette méthode permet d'ajouter un animal dans l'enclos supprimer_animal(animal: Animal): cette méthode permet de supprimer un animal de l'enclos
Marché | id_marche : l'identifiant unique du marché dans la base de données. produits_disponibles : un dictionnaire qui contient les produits disponibles sur le marché et leur quantité. prix_vente : un dictionnaire qui contient les prix de vente des produits sur le marché. prix_achat : un dictionnaire qui contient les prix d'achat des produits sur le marché.|ajouter_produit(culture: Culture, quantite: float, prix_achat: float, prix_vente: float): cette méthode permet d'ajouter un certain nombre de produits d'une culture donnée sur le marché avec leur prix d'achat et de vente. retirer_produit(culture: Culture, quantite: float): cette méthode permet de retirer un certain nombre de produits d'une culture donnée du marché. mise_a_jour_prix(): cette méthode permet de mettre à jour les prix de vente des produits sur le marché
- Champs :une classe abstraite , classe mère des classes « Animal » et « Culture
- Ferme :la classe façade qui contient le nom de la ferme.
**

## Aspect Dynamique : Diagramme de Séquences :

1. ## **Gérer les alimentations des animaux :**
Description textuelle : 
-Le joueur commence par envoyer une demande pour acheter un animal au marché. Le marché reçoit cette demande et retire la quantité spécifiée de l'animal demandé. Ensuite, le marché envoie une mise à jour de la quantité d'animaux disponible au joueur. --Ensuite, le joueur souhaite ajouter l'animal acheté à son enclos. Il envoie une demande à l'enclos pour ajouter l'animal, et l'enclos envoie une confirmation d'ajout de l'animal au joueur. -Le joueur veut ensuite vérifier la santé de l'animal, donc il envoie une demande au système pour obtenir des informations sur le poids et l'âge de l'animal. Le système renvoie ces informations au joueur. -En fonction de l'âge et du poids de l'animal, deux scénarios sont possibles : -Si l'âge de l'animal est supérieur à 5 ans et son poids est inférieur à 50, le joueur doit prendre une décision entre soigner ou vendre l'animal. S'il décide de vendre, le système envoie une demande au marché pour ajouter l'animal à la vente, puis retire l'animal de l'enclos et envoie une confirmation au joueur. -Sinon, s'il décide de soigner, le système envoie une confirmation de soin au joueur. -Si l'âge de l'animal est inférieur ou égal à 5 ans ou son poids est supérieur ou égal à 50, le joueur doit décider entre nourrir ou reproduire l'animal. S'il décide de reproduire, le système envoie une confirmation de reproduction au joueur. -Sinon, s'il décide de nourrir, le système envoie une confirmation de nourrissage au joueur.
2.  **Gérer les cultures :**
Description textuelle : -Le joueur commence par envoyer une demande pour acheter une culture au marché. Le marché reçoit cette demande et l'active pour effectuer une mise à jour de la quantité disponible de la culture demandée. Une fois la mise à jour effectuée, le marché envoie une confirmation au joueur. -Ensuite, le joueur souhaite ajouter la culture achetée à l'entrepôt. Il envoie une demande à l'entrepôt pour ajouter la culture, qui est ensuite activée. L'entrepôt confirme l'ajout de la culture et désactive l'interaction. -Le joueur a également la possibilité de demander des informations sur la date de plantation et de récolte de la culture. Cette demande est envoyée à l'objet Culture, qui est activé pour répondre en renvoyant les dates de plantation et de récolte au joueur. -En fonction de la date de récolte par rapport à la date système, deux scénarios sont possibles : -Si la date de récolte est égale à la date système, le joueur envoie une demande pour récolter la culture au marché. Le marché retire la culture de l'entrepôt et envoie une confirmation de récolte au joueur. Si la date de récolte est différente de la date système, le joueur doit décider s'il souhaite arroser ou fertiliser la culture. Cette décision est envoyée au marché, qui envoie une confirmation de l'action choisie par le joueur. -Enfin, le joueur peut décider de vendre la culture au marché. Il envoie une demande de vente au marché, qui retire la culture de l'entrepôt et envoie une confirmation de vente au joueur



