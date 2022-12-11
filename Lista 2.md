# Zadanie 1
```py
def minMax(tab):
    for i in range(0, 15, 1):
        if i == 0:
            min = tab[0]
            max = tab[0]

        if min > tab[i]:
            min = tab[i]
            pozMin = i + 1

        if max < tab[i]:
            max = tab[i]
            pozMax = i + 1

    return min, max, pozMin, pozMax

def srednia(tab):
    s = int(0)
    for i in range(0, 15, 1):
        s += num
    return s / 15

def pozycja(tab):
    poz = int(input())
    for i in range(0, 15, 1):
        if i == poz - 1:
            return tab[i]


tab = []

#Wpisywanie liczb
for i in range(0, 15, 1):
    num = int(input(f"podaj liczbę o pozycji {i + 1} "))
    tab.append(num)

#Wpisywanie pozycji do znalezienia
print("Podaj pozycję")
poz = pozycja(tab)

print(tab)
minmax = minMax(tab)
sr = srednia(tab)
print(f"Najmniejsza wartość wynosi: {minmax[0]}, znajduje się na pozycji {minmax[2]}")
print(f"Największa wartość wynosi: {minmax[1]}, znajduje się na pozycji {minmax[3]}")
print(f"Średnia wynosi {sr}")
print(f"Wartość na podanej pozycji to: {poz}")

```
