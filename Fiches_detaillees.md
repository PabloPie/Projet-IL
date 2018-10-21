# UC_01: Valider un Build Order

#### Description: 
L'utilisateur introduit un BO et le système:
* Indique la durée idéale s'il est réalisable
* Fournit une correction de ce BO (ajout d'actions) s'il n'est pas réalisable

#### Acteurs:
* Utilisateur

#### Pré-conditions:
* Les unités/bâtiments/ressources de l'objectif sont des objets existants du jeu

#### Scénario nominal:
1. L'utilisateur introduit un BO
2. Le système vérifie que le BO est réalisable
3. Le système indique la durée idéale du BO

#### Alternatives:
##### A1: Le BO n'est pas réalisable
L'enchaînement démarre aprés le point 2:

3. Le système corrige le BO en insérant des actions
4. Le système retourne le BO corrigé à l'utilisateur et indique sa durée idéale

#### Exceptions
Aucune

#### Post-conditions
Le Build Order est réalisable

---

# UC_02: Optimiser un objectif

#### Description: 
Le joueur ou l'IA définit un objectif et le système rend un Build Order optimisé

#### Acteurs:
* IA
* Utilisateur

#### Pré-conditions:
* Le système possède un état du jeu (qu'il soit initial ou courant)
* Les unités/bâtiments/ressources de l'objectif sont des objets existants du jeu

#### Scénario nominal:
1. Un acteur définit un objectif
2. Le système vérifie que l'objectif est atteignable
3. Le système compare l'état du jeu avec l'objectif
4. Le système calcule le Build Order
5. Le système renvoie le Build Order

#### Alternatives:
Aucune

#### Exceptions
##### E1: Objectif inatteignable
L'enchaînement démarre aprés le point 2:

3. Le système signale que l'objectif n'est pas atteignable

##### E2: L'objectif est déjà atteint (comprend le fait que l'état du jeu contienne plus d'unités/bâtiments/ressources que l'objectif)
L'enchaînement démarre aprés le point 3:

4. Le système signale que l'objectif est déjà accompli

#### Post-conditions
Le Build Order permet d'atteindre l'objectif en un temps idéal

---

# UC_03: Optimiser objectif à partir d'un état fournit

###### Date: 14/10/2018
###### Auteurs: P. Gomez, N. Gerday

#### Description: 
L'IA veut un BO optimisé en partant des données concernant l'état courant du jeu (unités, bâtiments, ressources) et d'un objectif.

#### Pré-conditions:
Aucune

#### Scénario nominal:
1. L'IA fournit l'état courant du jeu et un objectif au système
2. Le sytème vérifie la validité de l'état fournit
3. Appel du cas UC_02: "Optimiser un objectif"

#### Alternatives:
Aucune

#### Exceptions
##### E1: Incohérence des données
L'enchaînement démarre aprés le point 2:

3. Message d'erreur envoyé à l'IA

#### Post-conditions
Le Build Order permet d'atteindre l'objectif à partir de l'état  en un temps idéal
