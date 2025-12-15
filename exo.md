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

# Etoiles : 2 <-> 2: Exercice machin
## Consignes

~~~py
def store_two_classics(val1: int, val2: int) -> tuple[qiskit.QuantumCircuit, str, str]:
    """
    Generates a Quantum Circuit which stores two classical integers
    Returns the circuit and binary representation of the integers
    """
    x, y = bin(val1)[2:], bin(val2)[2:]  # Remove leading '0b'

    # Ensure that both strings are of the same length
    if len(x) > len(y):
        y = y.zfill(len(x))
    else:
        x = x.zfill(len(y))

    # We need (3 * number of bits in the larger number)+1 qBits
    # The second parameter is the number of classical registers, to measure the result
    circuit = qiskit.QuantumCircuit((len(x) * 3) + 1, len(x) + 1)

    # We are essentially "not-ing" the bits that are 1
    # Reversed because it's easier to perform ops on more significant bits
    for i in range(len(x)):
        if x[::-1][i] == "1":
            circuit.x(i)
    for j in range(len(y)):
        if y[::-1][j] == "1":
            circuit.x(len(x) + j)

    return circuit, x, y
~~~

De quelle forme est le p-uplet renvoyé?

## Réponse

`(<class 'qiskit.QuantumCircuit'>, <class 'str'>, <class 'str'>)`

# Etoiles : 2 <-> 3: Rotation de p-uplet

## Consignes

Créez une fonction qui renvoie un p-uplet retourné.

```python
a = fonction((1, 2, 3)) # renvoie (3, 2, 1)
```

## Réponse
~~~py
def retourner(puplet: tuple) -> tuple:
    out = ()
    for i in range(len(puplet)):
        out = (out, len(puplet) - i);
    return out;
~~~


# Etoiles : 1 <-> 2: Alpha et Beta

## Consignes

Donnez une fonction qui renvoie alpha et beta partant de a, b, c, et la fonction

## Réponse

~~~py
def racines(a, b, c, fn):
    return ((-b)/(2*a), fn((-b)/(2*a)));
~~~

# Etoiles : 3 <-> 2: Les shadocks
## Consignes
Renvoyer le nombre d'entrée N en shadock
GA = 0
BU = 1
ZO = 2
MEU = 3

base 4

## Réponse
~~~py
def shadock(N):
    mots = ['GA', 'BU', 'ZO', 'MEU']  # correspondance base 4
    if N == 0:
        return mots[0]
    
    resultat = []
    while N > 0:
        N, reste = divmod(N, 4)
        resultat.append(mots[reste])
    
    return ''.join(reversed(resultat))
~~~

# Etoiles : 1 <-> 3: Deviner
## Consignes
Devinez la valeur de e
~~~py
import math

def decimale_de_pi(n: int):
    n = int(n)
    if n <= 204:
        return print(format(math.pi, f".{n}f"))
    else:
        print("PI AVEC 204 DECIMALES CAR MAX")
        return print(format(math.pi, ".204f"))
~~~
## Réponse
