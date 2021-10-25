<br><br><br>
<center><h1>Numérique et Sciences Informatiques</h1></center>
<center><h2>Recueil de corrections communautaire</h2></center>
<br><br><br><br><br><br><br>




# **Chapitre 2 :**[ **Programmation Orientée Objet**](https://cdn.discordapp.com/attachments/868964577071734814/873899194467876874/joke-women-class.png)

## *Exercice 2.1*
```py
class Plante :
    def __init__(self, espece, taille:float, age:int, age_maxi:int, nb_fleurs:int, nb_fruits:int) :
        self.espece = espece
        self.taille = taille
        self.age = max(age,0)
        self.age_maxi  = max(age_maxi, 0)
        self.nb_fleurs = max(nb_fleurs,0)
        self.nb_fruits = max(nb_fruits,0)
    
    def grandir(self,augmentation) :
        self.taille += augmentation
    
    def faner(self) :
        if (self.age>age_maxi*0.9) :
            self.nb_fleurs=0
            self.nb_fruits=0
```
Rappelez-vous, toujours [**self.**](https://www.youtube.com/watch?v=M5d7vygUPoQ) !

<br><br>


## *Exercice 2.2*
```py
from math import pi

class Cerlce :
    def __init__(self, rayon:float) :
        self.rayon = max(rayon,0)
    
    def get_rayon(self) :
        return self.rayon
    
    def set_rayon(self, new_rayon) :
        self.rayon = max(new_rayon,0)
    
    def get_perimetre(self) :
        return self.rayon*pi*2
    
    def get_aire(self) :
        return self.rayon*self.rayon*pi
```

<br><br>


## *Exercice 2.3*
1. ```py
   v = Voiture('Renault', 'Zoé', 0, 160)
   ```
2. ```py
   v.affiche()
   ```
3. ```py
   print(v.get_km())
   ```
4. ```py
   v.roule(50)
   ```

<br><br>


## *Exercice 2.4*
```py
class Personnage :
    """
    Classe implémentant un personnage caractérisé par :
    - ses points de vie (hp)
    - sa classe (classe)
    - sa puissance d'attaque (atk)
    - sa puissance de défense (dfs)
    """
    def __init__(self, hp, classe, atk, dfs) :
        """Constructeur"""
        self.hp     = hp
        self.classe = classe
        self.atk    = atk
        self.dfs    = dfs

    def get_hp(self) :
        """Accesseur des HP"""
        return self.hp

    def encaisse(self, points) :
        """
        Retire des points de HP au personnage
        Si à l'issue du calcul les HP sont négatifs ou nuls
        renvoie False, sinon renvoie True
        """
        self.hp -= points
        # Retourne le résultat de l'opération conditionnel, True ou False. Petite astuce sympa ;)
        return self.hp <= 0
    
    def soigne(self, points) :
    """
    Ajoute des points de HP au personnage
    Ne renvoie rien
    """
    self.hp += points
```

<br><br>


## *Exercice 2.5*
```py
from random import shuffle

class Doggo :
    def __init__(self, nom:str, pv:int, aboiement:str) :
        self.nom = nom
        self.pv  = pv
        self.aboiement = aboiement
    
    def mordre(self, autre_chien) :
        autre_chien.pv -= 1
    
    def manger(self) :
        self.pv += 1  # yummy yummy in my belly
    
    def grogner(self) :
        return 'Grrr...'+self.aboiement
    
    def machouiller(self, chaine:str) :
        c = list(chaine)
        shuffle(c)
        return ''.join(c)
```

<br><br>


## *Exercice 2.6*
1. Un *constructeur*
2. une *méthode*
3. Ses attributs sont *couleur* et *valeur*
4. ```py
    c = Carte('Carreau', 2)
   ```
5. ```py
    paquet = Paquet()
    for couleur in ["Trèfle", "Pique", "Cœur", "Carreau"] :
        for valeur un range(1, 14) :
            carte = Carte(couleur, valeur)
            paquet.ajouter_carte(carte)
   ```
6. ```py
    def affiche(self) :
    têtes = {1 : "As", 11 : "Valet", 12 : "Dame", 13 : "Roi"}
    if self.valeur not in têtes :
        print(self.valeur, "de", self.couleur)
    else :
        print(têtes[self.valeur], "de", self.couleur)
   ```
7.  ```py
    class Paquet :
        def __init__(self) :
            self.paquet = []
            for couleur in ["Trèfle", "Pique", "Cœur", "Carreau"] :
                for valeur in range(1, 14) :
                    carte = Carte(couleur, valeur)
                    self.paquet.append(carte)
        
        def affiche(self) :
            for carte in self.paquet :
                carte.affiche()
    ```
8.  ```py
    from random import shuffle
    
    def melange(self) :
        shuffle(self.paquet)
    ```

<br><br><br><br><br><br><br>




# **Chapitre 3 : Types abstraits de données**
<br>

---
<center><h2><i><strong>Listes chaînées</strong></i></h2></center>
---
---
<br><br>

### *Exercice 3.1*
---
Chaîne : ``Début -> 2 -> 1 -> 3 -> 4 -> None``

1. La valeur de la tête de *lst* est **1**
2. La longueur de *lst* est de **4**
3. (Voir chaîne si dessus)

<br><br>


### *Exercice 3.2*
---
Chaîne :
```
--> 2 -> 1 -> 3 -> 4 -> 2 --v
|___________________________|
```
- La chaîne est circulaire ⭕

<br><br>


### *Exercice 3.3*
---
```py
Fonction coupe(lst, n) :
    lst2 est une liste chaînée dont la tête est "la tête de lst"

    elt est la tête de "lst"

    # Lecture des chaînons jusqu'à trouver celui de valeur n
    Tant que elt est non vide et que la valeur de elt est différente de "n" :
        elt est égal au successeur de "elt"
    
    Si elt est vide :
        Renvoyer ("lst, lst2") # Pour expliquer rapidement, lst sera vide et lst2 contiendra tout
        # Sinon "lst2, None" est une possibilité
    Sinon :
        La tête de lst2 est égale au "successeur de elt"
        Le successeur de elt est "None"
        Renvoyer (lst, lst2)
```

<br><br>


### *Exercice 3.4*
---
1. *m* prend son successeur tout les 2 éléments parcourus puis à la fin son successeur si la liste est de longueur pair (on ne compte pas le premier élément). *m* devient donc **3** (au départ) puis **2** et pour finir **7**.
2. Même logique, *m* devient **3**, **2** et pour finir **7**.
3. Le rôle de ce code est de retourner le maillon au milieu de la chaîne.

<br><br>


<br><br><br><br><br><br>

---
<center><h2><i><strong>Piles</strong></i></h2></center>
---
---
<br><br>

### *Exercice 3.8*
---
1. Le contenu de la pile est, de haut en bas : ``8 -> 6 -> 5``
2. La hauteur de la pile est de **3**
3. ```py
   while not pile.est_vide() :
       pile.depiler()
   ```
4. La dernière valeur dépilée sera le **5**

<br><br>


### *Exercice 3.12*
---
```
p1 est une Pile
tmp est une Pile vide
p2 est une Pile vide

Tant que p1 est non vide :
	v est le résultat de Dépile(p1)
	empiler v dans tmp

Tant que tmp est non vide :
	v est le résultat de Dépiler(tmp)
	empiler v dans p1
	empiler v dans p2
```

<br><br>


### *Exercice 3.14*
---
1.  ```js
        Déjà parcouront la première partie, les valeurs au fur-et-à-mesure sont :
        n : 23 -> 11 -> 5 -> 2 -> 1 -> 0
        p : 1  +  1  +  1 +  0 +  1
    
    Affichage :
        1
        0
        1
        1
        1
    ```
2. Cet algorithme permet de convertir un nombre décimal en binaire !<br>
``01101001 01101110 01100011 01110010 01101111 01111001 01100001 01100010 01101100 01100101 00100001``

<br><br>


### *Exercice 3.18*
---
```
Fonction insertion ( p : pile de nombres triées,	n : nombre ) -> Pile :
	tmp est une Pile vide
	v = Infini

	Tant que v > n ET p est non-vide :
		v est le résultat de dépiler p
		Si v > n :
			Empiler v dans tmp
	Si v <= n :
		Empiler v dans p
	Empiler n dans p

	Tant que tmp est non vide :
		Empiler dans p le résultat de dépiler tmp

	Renvoyer p
```

<br><br>


<br><br><br><br><br><br>


---
<center><h2><i><strong>Files</strong></i></h2></center>
---
---
<br><br>

### *Exercice 3.20*
---
1. 6-7-8
2. 3
3.  ```
    Tant que la file est non vide :
        Défiler un élément
    ```
4. 8

<br><br>


<br><br><br><br><br><br><br>




# **Chapitre 4 : Récursivité**
<br>


## *Exercice 4.1*
```py
def factoriel(n:int)->int :
    return n*factoriel(n-1)
```

<br><br>


## *Exercice 4.2*
1. 42 -> 85 -> 426 -> 853 -> 1707
   <br>Il y a au total 5 appels
2. 43 -> 87 -> 175 -> 876 -> 1753
   <br>Il y a au total 5 appels

<br><br>


## *Exercice 4.6*
1. **m=1** et **n=2**,<br>**m>0 et n>0**<br>donc on a *A(m-1, A(m,n-1))*<br>
    soit **A(0, A(1, 1))**<br>
    On répète l'opération ... et obtient **6 appels récursifs**
    <br><br>
2. A(2,1) -> **14 appels**
3. ```py
    # Voir aussi : https://pythontutor.com/visualize.html#mode=display
    def A(m, n, s="%s"):
        global na
        print(s % ("A(%d,%d)" % (m, n)))
        if m == 0:
            return n + 1
        if n == 0:
            na+=1
            return A(m - 1, 1, s)
        n2 = A(m, n - 1, s % ("A(%d,%%s)" % (m - 1)))
        na+=2
        return A(m - 1, n2, s)

    na=1
    print(f"Résultat : {A(3,4)} avec {na} appels")
    ```
    Résultat : 125 avec 10307 appels
4.  ```py
    '''def A(m,n):
    if m>0 :
        if n>0:
            return A(m-1, A(m,n-1))
        return A(m-1,1)
    return n+1'''
    A=lambda m,n:n+(m==0 or A(m-1,n==0 or A(m,n-1))-n)
    print(A(3,4))
    ```

<br><br>


## *Exercice 4.19*
```py
def partition(T, premier, dernier) :
	j=premier
	for i in range(premier, dernier):
		if T[i] <= T[dernier] :
			T[i], T[j] = T[j], T[i]
			j+=1
	T[dernier], T[j] = T[j], T[dernier]
	return j

def tri_rapide(T, premier, dernier) :
	if premier<dernier:
		pivot = partition(T, premier, dernier)
		tri_rapide(T, premier, pivot-1)
		tri_rapide(T, pivot+1, dernier)

l=[0,5,6,8,4,2,3,1,7,9]
tri_rapide(l, 0, len(l)-1)
print(l)
```

<br><br><br><br><br><br><br>




# **Chapitre 5 :**[ **Diviser pour régner**](https://media.discordapp.net/attachments/868964577071734814/897203031836352542/x1a1thbc8us71.png?width=484&height=514)
<br>

## *Exercice 5.3*
1.  ```py
    def dicho_iter(lst, valeur,gauche=0,droite=len(lst)-1,milieu=0) :
        """
        Recherche valeur dans lst (version itérative)
        Renvoie l'indice de valeur dans lst s'il existe, -1 sinon
        """
        if gauche<=droite:
            milieu=(gauche+droite)>>1
            if lst[milieu]==valeur :
                return milieu
            elif lst[milieu]>x:
                return dicho_iter(lst,valeur,gauche,milieu-1,milieu)
            else :
                return dicho_iter(lst,valeur,milieu+1,droite,milieu)
        return -1
    ```
2. **9** car 500 < 2<sup>9</sup>

<br><br>


## *Exercice 5.6*
   1. a) <br>43x58<br>=344+2150<br>=2494
      b) **4**
      c) **O(n)**
   2. **"3"** mais plutôt **11**
   3. **5**
   4. 3 et 4. On obtient le nombre de puissance de 10 nécessaire à écrire le nombre
   5. a) **25** et **68**
    b)
   ```py
    def coupe_10n(n, b):
        return (n//10**b, n%10**b)
   ```
    6.
```py
    def karatsuba(m,n) :
        t=max(m,n)
        if t<2 :
            return m*n
        a,b=coupe_10n(m,2)
        c,d=coupe_10n(n,2)
        ac=karatsuba(a,c)
        bd=karatsuba(b,d)
        ab_cd=karatsuba(ac,bd)
        return ac*10**t+(ac+bd-ab_cd)*10**(t/2)+bd
```


<br><br>



<br><br><br><br><br><br><br><br><br>
# Aides à l'écriture de ce document :

Editeur de textes :
- VScode - Extension <u>Markdown All in One</u> de *Yu Zhang*
- StackEdit [(web)](https://stackedit.io/app#)
- Github (web) depuis le repo

Cheatsheet : https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

N'oubliez pas que le Markdown est une **version simplifé d'écrire de l'HTML**.<br>
Vous pouvez écrire comme vous le souhaitez !

Et le Markdown moderne est rempli de plug-ins. Pour interpréter du LateX par exemple ;)