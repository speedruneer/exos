# Etoiles : 1 <-> 1: La liste de noel
## Consignes
Créez un tuple des noms de familles des personnes invitées pour noël, la liste doit contenir:
- noël-collin
- grinch
- payne

## Réponse
~~~py
liste = ("noël-collin", "grinch", "payne")
~~~

# Etoiles : 3 <-> 1: Exercice 1.44224957031

## Consignes

Quentin crée une fonction qui renvoie un p-uplet en python et veut tester leurs valeurs.

Voici le code qu'il a utilisé

~~~py

def tup(st):
    a = ('',)
    for lettre in st:
        a = a + (lettre,)
    return a

t1 = tup("J'utilise arch linux")
~~~

Documentez et spécifiez la fonction.

## Réponse
~~~py
def tup(st: str) -> tuple:
    """
    Convertit une chaîne de caractères en un tuple contenant chaque caractère.

    Chaque caractère de la chaîne d'entrée est placé dans un tuple, dans le même ordre 
    que dans la chaîne. Le tuple retourné contient également un élément initial vide 
    (tuple vide au début).

    Arguments:
        st (str): La chaîne de caractères à convertir. Doit contenir au moins un caractère.

    Renvoie:
        tuple: Un tuple contenant tous les caractères de la chaîne, précédés d'un élément vide.
    """
    assert len(st) >= 1, "Le str devrait avoir une longueur supérieure ou égale à 1"
    a = ('',)
    for lettre in st:
        a = a + (lettre,)
    return a

t1 = tup("J'utilise arch linux")
~~~

# Etoiles : 2 <-> 1: La pizza c'est trop bon
## Consignes

Créez une fonction qui renvoie l'aire, le périmètre, de chaque part d'une pizza découpée en N parts de rayon C.

## Réponse

~~~py
import math

def parts(N, C):
    return ((math.pi * C * C)/N, (2 * math.pi * C)/N)

~~~
