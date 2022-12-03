# Zadanie 1
```py
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
