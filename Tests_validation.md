# TV_01: Valider un Build Order

###### Id: 01
###### Auteur: Ivan Delgado

#### Contexte: 
L'utilisateur *U_01* a un Build Order *BO_01* qu'il veut valider et dont il veut obtenir la durée idéale

##### Entrées:
* Build Order *BO_01*

#### Scénario:
1. L'utilisateur *U_01* clique sur "Valider un Build Order"
2. L'utilisateur rentre le Build Order *BO_01*
3. Le système indique la durée idéale de *BO_01*

#### Résultat attendu:
Le système affiche la validité du Build Order et sa durée

#### Moyens de vérification:
* Affichage de la part du système
* Réalisation du Build Order

---

# TV_02: Optimiser un objectif utilisateur

###### Id: 02
###### Auteur: Ivan Delgado

#### Contexte: 
L'utilisateur *U_01* a un Objectif *Ob_01* et une situation du jeu *J_01* à partir desquels il veut obtenir un BO optimisé

##### Entrées:
* Objectif *Ob_01*
* État du jeu *J_01*

#### Scénario:
1. L'utilisateur *U_01* clique sur "Optimiser un objectif"
2. L'utilisateur *U_01* rentre l'objectif *Ob_01*
3. L'utilisateur *U_01* rentre l'état du jeu *J_01*

#### Résultat attendu:
Le système affiche un écran de validation et le Build Order pour réaliser l'objectif

#### Moyens de vérification:
* Affichage de la part du système
* Réalisation du Build Order

---

# TV_03: Optimiser un objectif IA

###### Id: 03
###### Auteur: Ivan Delgado

#### Contexte: 
L'IA *IA_01* a un Objectif *Ob_01* et une situation du jeu *J_01* à optimiser par le système

##### Entrées:
* Objectif *Ob_01*
* État du jeu *J_01*

#### Scénario:
1. L'IA *IA_01* envoie l'état du jeu *J_01* cf: TV_04
2. L'IA *IA_01* envoie une requête au système contenant l'objectif *Ob_01*
3. Le système confirme la réception à l'IA

#### Résultat attendu:
Le système renvoie le Build Order à l'IA *IA_01* pour réaliser l'objectif

#### Moyens de vérification:
* Réponse du système

---

# TV_04: Envoyer un 2ème état du jeu

###### Id: 04
###### Auteur: Ivan Delgado

#### Contexte: 
L'IA *IA_01* a une nouvelle situation du jeu *J_02* dans le contexte de l'optimisation d'un objectif

##### Entrées:
* État du jeu *J_02*

#### Scénario:
1. L'IA *IA_01* envoie une requête pour changer l'état du jeu, contenant *J_02*, au système
2. Le système confirme le changement d'état à l'IA

#### Résultat attendu:
Le système renvoie une confirmation du changement d'état

#### Moyens de vérification:
* Réponse du système

---

# TV_05: Suite des tests TV_02 et TV_01

###### Id: 05
###### Auteur: Bastien Peruchena

#### Contexte: 
L'utilisateur *U_01* fournit correctment le contexte du test TV_02 et utiliser le résultat qu'il obtient pour TV_01

##### Entrées:
* Objectif *Ob_01*
* État du jeu *J_01*

#### Scénario:
1. L'utilisateur *U_01* réalise le test TV_02 avec *Ob_01* et *J_01*
2. L'utilisateur *U_01* réalise le test TV_01 avec le résultat qu'il obtient

#### Résultat attendu:
Le système confirme que l'utilisateur a bien rentré un BO valide et ne l'optimise pas davantage

#### Moyens de vérification:
* Affichage de la part du système
* Comparaison du BO donné par TV_02 et celui renvoyé par TV_01

---

# TV_06: Valider un BO avec seulement l'étape finale

###### Id: 06
###### Auteur: Bastien Peruchena

#### Contexte: 
L'utilisateur *U_01* ne fournit qu'une étape finale pour le BO

##### Entrées:
* Étape *E_01* de BO

#### Scénario:
1. L'utilisateur *U_01* envoie l'étape *E_01* comme BO pour le test TV_01
2. L'utilisateur *U_01* utilise l'étape *E_01* comme objectif pour le test TV_02

#### Résultat attendu:
Les Build Order sont identiques

#### Moyens de vérification:
* Affichage de la part du système
* Comparaison des Build Orders

---

# TV_07: Envoyer un état du jeu incohérent

###### Id: 07
###### Auteur: Nathan Gerday

#### Contexte: 
L'IA *IA_01* envoie un état du jeu *E_01* incohérent ou impossible suite à un bug du jeu ou de l'IA

##### Entrées:
* État du jeu *J_01*

#### Scénario:
1. L'IA *IA_01* envoie une requête pour changer l'état du jeu au système avec un état du jeu *J_01*

#### Résultat attendu:
Le système envoie une response d'erreur à l'IA

#### Moyens de vérification:
* L'IA reçoit une erreur à a place d'un BO
