# Zadanie 1
```py
import requests

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
    print("Pogoda na dzisiaj")
    try:
        print(f"Nazwa: {response['name']}")
        print(f"Pogoda: {response['weather'][0]['description']}")
        print(f"Temperatura: {response['main']['temp']}C")
        print(f"Odczuwalna: {response['main']['feels_like']}C")
        print(f"Ciśnienie: {response['main']['pressure']}hPa")
        print(f"Wilgotność: {response['main']['humidity']}%")
        print(f"Prędkość wiatru: {response['wind']['speed']}km")
    except:
        print("Podałeś nazwę, która nie istnieje!")

else:
    URLTOMORROW = "https://api.openweathermap.org/data/2.5/forecast?"
    urlTomorrow = URLTOMORROW + "appid=" + API + "&q=" + CITY + "&units=" + UNITS + "&lang=" + LANG
    responseTomorrow = requests.get(urlTomorrow).json()
    print("Pogoda na jutro")
    try:
        print(f"Nazwa: {responseTomorrow['city']['name']}")
        print(f"Pogoda: {responseTomorrow['list'][1]['weather'][0]['description']}")
        print(f"Temperatura: {responseTomorrow['list'][1]['main']['temp']}C")
        print(f"Odczuwalna: {responseTomorrow['list'][1]['main']['feels_like']}C")
        print(f"Ciśnienie: {responseTomorrow['list'][1]['main']['pressure']}hPa")
        print(f"Wilgotność: {responseTomorrow['list'][1]['main']['humidity']}%")
        print(f"Prędkość wiatru: {responseTomorrow['list'][1]['wind']['speed']}km")
    except:
        print("Podałeś nazwę, która nie istnieje!")
```
