#Zadanie 1
```py
import requests

while True:
    print("Podaj nazwę miasta")
    wyb = input()

    API = "5ec197339876353f5d366e9df3303a4d"
    CITY = wyb
    UNITS = "metric"
    LANG = "pl"

    print("1.Pogoda na dzisiaj")
    print("2.Pogoda na jutro")
    wyb = input()

    if wyb == '1':
        URL = "https://api.openweathermap.org/data/2.5/weather?"
        url = URL + "appid=" + API + "&q=" + CITY + "&units=" + UNITS + "&lang=" + LANG
        response = requests.get(url).json()
        try:
            print("Pogoda na dzisiaj")
            print(f"Nazwa: {response['name']}")
            print(f"Pogoda: {response['weather'][0]['description']}")
            print(f"Temperatura: {response['main']['temp']}C")
            print(f"Odczuwalna: {response['main']['feels_like']}C")
            print(f"Ciśnienie: {response['main']['pressure']}hPa")
            print(f"Wilgotność: {response['main']['humidity']}%")
            print(f"Prędkość wiatru: {response['wind']['speed']}km")
            break
        except:
            print("Podałeś nazwę, która nie istnieje!")

    elif wyb == '2':
        URLTOMORROW = "https://api.openweathermap.org/data/2.5/forecast?"
        urlTomorrow = URLTOMORROW + "appid=" + API + "&q=" + CITY + "&units=" + UNITS + "&lang=" + LANG
        responseTomorrow = requests.get(urlTomorrow).json()
        try:
            print("Pogoda na jutro")
            print(f"Nazwa: {responseTomorrow['city']['name']}")
            print(f"Pogoda: {responseTomorrow['list'][1]['weather'][0]['description']}")
            print(f"Temperatura: {responseTomorrow['list'][1]['main']['temp']}C")
            print(f"Odczuwalna: {responseTomorrow['list'][1]['main']['feels_like']}C")
            print(f"Ciśnienie: {responseTomorrow['list'][1]['main']['pressure']}hPa")
            print(f"Wilgotność: {responseTomorrow['list'][1]['main']['humidity']}%")
            print(f"Prędkość wiatru: {responseTomorrow['list'][1]['wind']['speed']}km")
            break
        except:
            print("Podałeś nazwę, która nie istnieje!")

    else:
        print("Nie ma takiej opcji!")
        pass
```

# Modyfikacja
```py
import requests
import os

while True:
    f = open("last.txt", "a")
    file = open("wybor.txt", "a")
    
    s = "last.txt"

    API = "5ec197339876353f5d366e9df3303a4d"
    UNITS = "metric"
    LANG = "pl"
    with open("last.txt", "r") as file:
        CITY = file.read().replace("\n", "")
    if os.stat(s).st_size == 0:
        print("pusty plik")
    else:
        with open("wybor.txt", "r") as file:
            wybor = file.read().replace("\n", "")
        print(f"WYBOR {wybor}")
        if wybor == "1":
            print(f"NAZWA MIASTA {CITY}")
            URL = "https://api.openweathermap.org/data/2.5/weather?"
            url = URL + "appid=" + API + "&q=" + CITY + "&units=" + UNITS + "&lang=" + LANG
            response = requests.get(url).json()
            print("Pogoda na dzisiaj")
            print(f"Nazwa: {response['name']}")
            print(f"Pogoda: {response['weather'][0]['description']}")
            print(f"Temperatura: {response['main']['temp']}C")
            print(f"Odczuwalna: {response['main']['feels_like']}C")
            print(f"Ciśnienie: {response['main']['pressure']}hPa")
            print(f"Wilgotność: {response['main']['humidity']}%")
            print(f"Prędkość wiatru: {response['wind']['speed']}km")
        if wybor == "2":
            URLTOMORROW = "https://api.openweathermap.org/data/2.5/forecast?"
            urlTomorrow = URLTOMORROW + "appid=" + API + "&q=" + CITY + "&units=" + UNITS + "&lang=" + LANG
            responseTomorrow = requests.get(urlTomorrow).json()
            print("Pogoda na jutro")
            print(f"Nazwa: {responseTomorrow['city']['name']}")
            print(f"Pogoda: {responseTomorrow['list'][1]['weather'][0]['description']}")
            print(f"Temperatura: {responseTomorrow['list'][1]['main']['temp']}C")
            print(f"Odczuwalna: {responseTomorrow['list'][1]['main']['feels_like']}C")
            print(f"Ciśnienie: {responseTomorrow['list'][1]['main']['pressure']}hPa")
            print(f"Wilgotność: {responseTomorrow['list'][1]['main']['humidity']}%")
            print(f"Prędkość wiatru: {responseTomorrow['list'][1]['wind']['speed']}km")

    print("Podaj nazwę miasta")
    wyb = input()
    f.write(wyb)
    f = open("last.txt", "w")

    CITY = wyb

    print("1.Pogoda na dzisiaj")
    print("2.Pogoda na jutro")
    wyb = input()
    file = open("wybor.txt", "w")
    file.write(wyb)

    if wyb == '1':
        URL = "https://api.openweathermap.org/data/2.5/weather?"
        url = URL + "appid=" + API + "&q=" + CITY + "&units=" + UNITS + "&lang=" + LANG
        response = requests.get(url).json()
        try:
            print("Pogoda na dzisiaj")
            print(f"Nazwa: {response['name']}")
            print(f"Pogoda: {response['weather'][0]['description']}")
            print(f"Temperatura: {response['main']['temp']}C")
            print(f"Odczuwalna: {response['main']['feels_like']}C")
            print(f"Ciśnienie: {response['main']['pressure']}hPa")
            print(f"Wilgotność: {response['main']['humidity']}%")
            print(f"Prędkość wiatru: {response['wind']['speed']}km")
            break
        except:
            print("Podałeś nazwę, która nie istnieje!")

    elif wyb == '2':
        URLTOMORROW = "https://api.openweathermap.org/data/2.5/forecast?"
        urlTomorrow = URLTOMORROW + "appid=" + API + "&q=" + CITY + "&units=" + UNITS + "&lang=" + LANG
        responseTomorrow = requests.get(urlTomorrow).json()
        try:
            print("Pogoda na jutro")
            print(f"Nazwa: {responseTomorrow['city']['name']}")
            print(f"Pogoda: {responseTomorrow['list'][1]['weather'][0]['description']}")
            print(f"Temperatura: {responseTomorrow['list'][1]['main']['temp']}C")
            print(f"Odczuwalna: {responseTomorrow['list'][1]['main']['feels_like']}C")
            print(f"Ciśnienie: {responseTomorrow['list'][1]['main']['pressure']}hPa")
            print(f"Wilgotność: {responseTomorrow['list'][1]['main']['humidity']}%")
            print(f"Prędkość wiatru: {responseTomorrow['list'][1]['wind']['speed']}km")
            break
        except:
            print("Podałeś nazwę, która nie istnieje!")

    else:
        print("Nie ma takiej opcji!")
        pass
```
