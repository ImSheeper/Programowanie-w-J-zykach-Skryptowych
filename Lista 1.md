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
    ```
