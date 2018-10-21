# TV_01: Valider un Build Order

###### Id: 01
###### Auteur: Ivan Delgado

#### Contexte: 
L'utilisateur *U_01* a un Build Order *BO_01* valide qu'il veut valider et dont il veut obtenir la durée idéale

##### Entrées:
* Build Order *BO_01*

#### Scénario:
1. L'utilisateur rentre le Build Order *BO_01*
2. L'utilisateur *U_01* clique sur "Valider un Build Order"


#### Résultat attendu:
Le système affiche que le Build est valide et sa durée idéale

#### Moyens de vérification:
* Affichage de la part du système
* Test du Build Order dans le jeu

---

# TV_02: Optimiser un objectif utilisateur

###### Id: 02
###### Auteur: Ivan Delgado

#### Contexte: 
L'utilisateur *U_01* a un Objectif *Ob_01* valide à partir duquel il veut obtenir un BO optimisé

##### Entrées:
* Objectif *Ob_01*

#### Scénario:
1. L'utilisateur *U_01* introduit l'objectif *Ob_01*
2. L'utilisateur *U_01* clique sur "Optimiser objectif"

#### Résultat attendu:
Le système affiche un écran de validation et le Build Order pour réaliser l'objectif

#### Moyens de vérification:
* Affichage de la part du système du Build Order et d'un message de validation
* Test du Build Order dans le jeu

---

# TV_03: Optimiser un objectif utilisateur non valide

###### Id: 03

#### Contexte: 
L'utilisateur *U_01* a un Objectif *Ob_01* **non** valide à partir duquel il veut obtenir un BO optimisé

##### Entrées:
* Objectif *Ob_01*

#### Scénario:
1. L'utilisateur *U_01* introduit l'objectif *Ob_01*
2. L'utilisateur *U_01* clique sur "Optimiser objectif"

#### Résultat attendu:
Le système affiche un écran d'érreur qui indique le l'objectif introduit n'est pas valide

#### Moyens de vérification:
* Affichage de la part du système d'un message d'erreur

---

# TV_04: Optimiser un objectif IA

###### Id: 04
###### Auteur: Ivan Delgado

#### Contexte: 
L'IA *IA_01* a un Objectif *Ob_01* et une situation du jeu *J_01* à optimiser par le système

##### Entrées:
* Objectif *Ob_01*
* État du jeu *J_01*

#### Scénario:
1. L'IA *IA_01* envoie l'état du jeu *J_01* et l'objectif *Ob_01*

#### Résultat attendu:
Le système renvoie le Build Order à l'IA *IA_01* pour réaliser l'objectif en temps idéal

#### Moyens de vérification:
* Le système renvoie un Build Order
* Test du Build Order dans le jeu

---

# TV_05: Suite des tests TV_02 et TV_01

###### Id: 05
###### Auteur: Bastien Peruchena

#### Contexte: 
L'utilisateur *U_01* fournit correctment le contexte du test TV_02 et utilise le résultat qu'il obtient pour TV_01

##### Entrées:
* Objectif *Ob_01*

#### Scénario:
1. L'utilisateur *U_01* réalise le test TV_02 avec *Ob_01*
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
* Comparaison des Build qui devraient être identiques

---

# TV_07: Envoyer un état du jeu incohérent

###### Id: 07
###### Auteur: Nathan Gerday

#### Contexte: 
L'IA *IA_01* envoie un objectif avec un état du jeu *E_01* incohérent ou impossible suite à un bug du jeu ou de l'IA

##### Entrées:
* État du jeu *J_01*
* Objectif *Ob_01*

#### Scénario:
1. L'IA *IA_01* envoie l'état incohérent *J_01* et l'objectif *Ob_01*

#### Résultat attendu:
Le système envoie une response d'erreur à l'IA

#### Moyens de vérification:
* L'IA reçoit une erreur à a place d'un BO
