# Zadanie 1
```py
#Napisz program, który wczyta 15 liczb różnych liczb całkowitych do listy, a następnie
#• znajduje największą i najmniejszą z nich, a także ich pozycje w zbiorze
#• wyznaczy średnią wartość w tablicy
#• zwróci pozycję wartości podanej przez użytkownika
#Oczywiście powyższe funkcjonalności realizowane powinny być przez odpowiednie funkcje do
#których należy przekazać listę wczytanych liczb. Funkcje zwracają wyniki – nie wyświetlają ich. Wyniki
#wyświetla „część główna” skryptu. Funkcje te powinny trafić do dedykowanego modułu.

tab = []
pozMin = int(0)
pozMax = int(0)
s = int(0)

for i in range(0, 15, 1):
    num = int(input(f"podaj liczbę o pozycji {i + 1} "))
    s += num

    tab.append(num)
    if i == 0:
        min = num
        max = num

    if min > tab[i]:
        min = tab[i]
        pozMin = i

    if max < tab[i]:
        max = tab[i]
        pozMax = i


print("Podaj pozycję")
poz = int(input())
for i in range(0, 15, 1):
    if i == poz - 1:
        print(f"Wartość na podanej pozycji to: {tab[i]}")
        break

print(tab)
print(f"Najmniejsza wartość wynosi: {min}, znajduje się na pozycji {pozMin + 1}")
print(f"Największa wartość wynosi: {max}, znajduje się na pozycji {pozMax + 1}")
print(f"Średnia wynosi {s / 15}")
```
