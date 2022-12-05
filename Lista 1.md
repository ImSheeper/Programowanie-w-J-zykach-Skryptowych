# Zadanie 1
```python
print("Wybierz bryłę:")
print("1.Kula")
print("2.Prostopadłościan")
print("3.Stożek")

wyb = input()

if wyb == '1':
    print("Wybrales kulę")
    print("Podaj promien")

    r = input()
    r = int(r)
    ob = (4/3) * 3.14 * (r*r*r)
    pp = 4 * 3.14 * (r*r)

    print(f"Objetosc kuli {ob}")
    print(f"Pole powierzchni kuli {pp}")

elif wyb == '2':
    print("Wybrales Prostopadłościan")
    print("Podaj a")
    a = input()
    a = int(a)
    print("Podaj b")
    b = input()
    b = int(b)
    print("Podaj c")
    c = input()
    c = int(c)

    ob = a * b * c
    pp = (2 * a) * b + (2 * b) * c + (2 * a) * c

    print(f"Objetosc prostopadłościanu {ob}")
    print(f"Pole powierzchni prostopadłościanu {pp}")

elif wyb == '3':
    print("Wybrales Stożek")
    print("Podaj r")
    r = input()
    r = int(r)
    print("Podaj h")
    h = input()
    h = int(h)
    print("Podaj l")
    l = input()
    l = int(l)

    ob = (3.14 * (r * r) * h) / 3
    pp = 3.14 * r * (r + l)

    print(f"Objetosc stożka {ob}")
    print(f"Pole powierzchni stożka {pp}")
```
# Zadanie 2
```python
sumaMatma = 0
sumaAlgo = 0
sumaProg = 0
przedmioty = 0
matma = 0
algo = 0
prog = 0

print("Podaj oceny z matematyki")
print("Wpisz 0, aby przestać wpisywać oceny")
while True:
    print("Podaj ocenę")
    a = input()
    a = int(a)

    if a == 0:
        break

    if a >= 2 and a <= 5:
        sumaMatma += a
        przedmioty += 1
        matma += 1
    else:
        print("Podałeś złą liczbę!")

print("Podaj oceny z algorytmów")
print("Wpisz 0, aby przestać wpisywać oceny")
while True:
    print("Podaj ocenę")
    a = input()
    a = int(a)

    if a == 0:
        break

    if a >= 2 and a <= 5:
        sumaAlgo += a
        przedmioty += 1
        algo += 1
    else:
        print("Podałeś złą liczbę!")

print("Podaj oceny z programowania")
print("Wpisz 0, aby przestać wpisywać oceny")
while True:
    print("Podaj ocenę")
    a = input()
    a = int(a)

    if a == 0:
        break

    if a >= 2 and a <= 5:
        sumaProg += a
        przedmioty += 1
        prog += 1
    else:
        print("Podałeś złą liczbę!")

print("Z czego policzyć średnią?")
print("1.Wszystkich przemiotów")
print("2.Matmy")
print("3.Algorytmów")
print("4.Programowania")

wyb = input()

if wyb == '1':
    print("Twoja średnia ocen z wszystkich przedmiotów ", (sumaMatma + sumaAlgo + sumaProg) / przedmioty)
elif wyb == '2':
    print("Twoja srednia ocen z matmy ", sumaMatma / matma)
elif wyb == '3':
    print("Twoja srednia ocen z algorytmów ", sumaAlgo / algo)
elif wyb == '4':
    print("Twoja srednia ocen z programowania ", sumaProg / prog)
```
# Zadanie 3
```python
#print("Podaj ilosc gwiazdek w podstawie")
#a = input()
#a = int(a)
print("Podaj nieparzysty tekst")
tekst = input()
a = len(tekst)
while a % 2 == 0:
    print("Podałeś parzysty tekst! Podaj ponownie")
    tekst = input()
    a = len(tekst)

for i in range(a * 2):

    for j in range (a * 2 - 1):
        if i + j == a - 1 or j - i == a - 1 or i == a - 1:
            print("*", end="")
        elif i == a - 2 and j == a - 1:
            print(tekst, end="");
        elif i == a - 2 and j > 1 and j < a + 2:
            print("", end="")
        else:
            print(" ", end="")

        #print(i, j, end="`")

    print(" ")
```
# Zadanie 4
```python
print("Podaj ciąg znaków")
tekst = input()
print("Podaj znak do pominięcia")
znak = input()

bezSpacji = 0
bezSpacji = int(bezSpacji)

pominiecie = 0
pominiecie = int(pominiecie)

dlugosc = len(tekst)

for i in range(dlugosc):
    if tekst[i] != " ":
        bezSpacji += 1
    if tekst[i] != znak:
        pominiecie += 1

print("ilość liter: ", dlugosc)
print("ilość z liter pominięciem spacji: ", bezSpacji)
print("ilość liter z pominięciem znaku: ", pominiecie)
print("")

print("Całe zdanie: ", tekst)
print("")

print("Zdanie z pominięciem spacji: ")
for i in range(dlugosc):
    if tekst[i] != " ":
        print(tekst[i], end="")
    else:
        print("")
print("")
print("")

print("Zdanie z pominięciem znaku: ")
for i in range(dlugosc):
    if tekst[i] != znak:
        print(tekst[i], end="")
    else:
        print(tekst[i])
```
