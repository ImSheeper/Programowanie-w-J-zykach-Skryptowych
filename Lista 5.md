# Zadanie 3
```py
from tkinter import *

main = Tk()

main.title("Kółko i krzyżyk")

globalna_wartosc = 'o'

def wpisz_symbol(symbol, button):
    global globalna_wartosc
    if globalna_wartosc == 'x':
        globalna_wartosc = 'o'
        button['text'] = globalna_wartosc
        label['text'] = 'Kolej gracza 1 (x)'
    else:
        globalna_wartosc = 'x'
        button['text'] = globalna_wartosc
        label['text'] = 'Kolej gracza 2 (o)'
    if(button['state'] == NORMAL):
        button['state'] = DISABLED

tab = [[0,1,2], [3,4,5], [6,7,8]]

def game(wartosc, button):

    if button == button_1:
        tab[0][0] = wartosc
    if button == button_2:
        tab[0][1] = wartosc
    if button == button_3:
        tab[0][2] = wartosc

    if button == button_4:
        tab[1][0] = wartosc
    if button == button_5:
        tab[1][1] = wartosc
    if button == button_6:
        tab[1][2] = wartosc

    if button == button_7:
        tab[2][0] = wartosc
    if button == button_8:
        tab[2][1] = wartosc
    if button == button_9:
        tab[2][2] = wartosc

    check(tab)

def check(tab):
    #sprawdzanie horyzontalne
    for i in range(3):
        if(tab[i][0] == tab[i][1] and tab[i][1] == tab[i][2]):
            game_end(globalna_wartosc)
    #sprawdzanie wertykalne
    for i in range(3):
        if (tab[0][i] == tab[1][i] and tab[1][i] == tab[2][i]):
            game_end(globalna_wartosc)
    #sprawdzanie glowna przekatna
    if(tab[0][0] == tab[1][1] and tab[1][1] == tab[2][2]):
        game_end(globalna_wartosc)
    #sprawdzanie przekatnej
    if (tab[0][2] == tab[1][1] and tab[1][1] == tab[2][0]):
        game_end(globalna_wartosc)

    print(tab[0])
    print(tab[1])
    print(tab[2])

def game_end(gracz):
    if gracz == 'x':
        gracz = 1
    else:
        gracz = 2

    newWindow = Toplevel(main)
    newWindow.geometry("400x100")
    main.withdraw()

    newlabel = Label(newWindow, text=f"Wygrał gracz {gracz} ({globalna_wartosc})", font=('Arial 18 bold'))
    newbutton = Button(newWindow, text="Zagraj ponownie", pady=10, command=lambda: play_again(newWindow))

    newlabel.pack()
    newbutton.pack()

def play_again(newWindow):
    k = 0
    for i in range(3):
        for j in range(3):
            tab[i][j] = k
            k += 1

    button_1['text'] = ""
    button_2['text'] = ""
    button_3['text'] = ""
    button_4['text'] = ""
    button_5['text'] = ""
    button_6['text'] = ""
    button_7['text'] = ""
    button_8['text'] = ""
    button_9['text'] = ""

    button_1['state'] = NORMAL
    button_2['state'] = NORMAL
    button_3['state'] = NORMAL
    button_4['state'] = NORMAL
    button_5['state'] = NORMAL
    button_6['state'] = NORMAL
    button_7['state'] = NORMAL
    button_8['state'] = NORMAL
    button_9['state'] = NORMAL

    main.deiconify()
    newWindow.withdraw()

label = Label(main, text="Kolej gracza 1 (x)", font=('Arial 28 bold'))
label.grid(column=0, row=0, columnspan=3, padx=10, pady=10)

button_1 = Button(main, text="", font=('Arial 20 bold'), width=10, height=4, command=lambda: [wpisz_symbol(globalna_wartosc, button_1), game(globalna_wartosc, button_1)])
button_2 = Button(main, text="", font=('Arial 20 bold'), width=10, height=4, command=lambda: [wpisz_symbol(globalna_wartosc, button_2), game(globalna_wartosc, button_2)])
button_3 = Button(main, text="", font=('Arial 20 bold'), width=10, height=4, command=lambda: [wpisz_symbol(globalna_wartosc, button_3), game(globalna_wartosc, button_3)])
button_4 = Button(main, text="", font=('Arial 20 bold'), width=10, height=4, command=lambda: [wpisz_symbol(globalna_wartosc, button_4), game(globalna_wartosc, button_4)])
button_5 = Button(main, text="", font=('Arial 20 bold'), width=10, height=4, command=lambda: [wpisz_symbol(globalna_wartosc, button_5), game(globalna_wartosc, button_5)])
button_6 = Button(main, text="", font=('Arial 20 bold'), width=10, height=4, command=lambda: [wpisz_symbol(globalna_wartosc, button_6), game(globalna_wartosc, button_6)])
button_7 = Button(main, text="", font=('Arial 20 bold'), width=10, height=4, command=lambda: [wpisz_symbol(globalna_wartosc, button_7), game(globalna_wartosc, button_7)])
button_8 = Button(main, text="", font=('Arial 20 bold'), width=10, height=4, command=lambda: [wpisz_symbol(globalna_wartosc, button_8), game(globalna_wartosc, button_8)])
button_9 = Button(main, text="", font=('Arial 20 bold'), width=10, height=4, command=lambda: [wpisz_symbol(globalna_wartosc, button_9), game(globalna_wartosc, button_9)])

button_1.grid(column=0, row=1)
button_2.grid(column=1, row=1)
button_3.grid(column=2, row=1)
button_4.grid(column=0, row=2)
button_5.grid(column=1, row=2)
button_6.grid(column=2, row=2)
button_7.grid(column=0, row=3)
button_8.grid(column=1, row=3)
button_9.grid(column=2, row=3)

main.mainloop()
```
