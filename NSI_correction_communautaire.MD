<br><br><br>
<center><h1>Numérique et Sciences Informatiques</h1></center>
<center><h2>Recueil de corrections communautaire</h2></center>
<br><br><br><br><br><br><br>



# **Chapitre 2 : Programmation Orientée Objet**

## *Exercice 2.1*
---
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
---
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
---
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
---
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
---
```py

```

<br><br>


## *Exercice 2.6*
---
```py

```

<br><br>






<br><br><br><br><br>
# Aides à l'écriture de ce document :

Editeur de textes :
- VScode - Extension <u>Markdown All in One</u> de *Yu Zhang*
- StackEdit [(web)](https://stackedit.io/app#)

Cheatsheet : https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

N'oubliez pas que le Markdown est une **version simplifé d'écrire de l'HTML**.<br>
Vous pouvez écrire comme vous le souhaitez !

Et le Markdown moderne est rempli de plug-ins. Pour interpréter du LateX par exemple ;)