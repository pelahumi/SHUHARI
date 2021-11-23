# SHUHARI

Hemos recibido el código a través de una carpeta compartida creada en google drive que nos pasaron por correo electrónico. Una vez recibido el código nos hemos puesto a trabajar cada uno en una cosa para ser más eficientes. 
Al verlo entregado nos hemos dado cuenta de que el grupo con el que colaboramos dividió el codigo en tres partes de acuerdo con la metodología de SHU-HA-RI que aprendimos durante la primera hora de trabajo.
El grupo implementó a la perfección el método de trabajo, ciñéndose primero a los conocimientos del profesor y progresivamente fueron mejorando el código hasta el punto de que nuestro grupo no tiene nada que aportar ni hemos podido detectar ningún error. Además hace uso de estructuras vistas en clase y otras más complejas.

El diagrama de flujo que corresponde a su código es el siguiente:
![diagrama de flujo ](https://github.com/pelahumi/SHUHARI/blob/main/Captura%20de%20pantalla%202021-11-23%20a%20las%2012.10.27.jpg)

Y su correspondiente código es:

```from random import choice, sample
 
cartas = {
   chr(0x1f0a1): 11,
   chr(0x1f0a2): 2,
   chr(0x1f0a3): 3,
   chr(0x1f0a4): 4,
   chr(0x1f0a5): 5,
   chr(0x1f0a6): 6,
   chr(0x1f0a7): 7,
   chr(0x1f0a8): 8,
   chr(0x1f0a9): 9,
   chr(0x1f0aa): 10,
   chr(0x1f0ab): 10,
   chr(0x1f0ad): 10,
   chr(0x1f0ae): 10,
}
 
print("cartas: {}".format(" ".join(cartas. keys())))
print("puntos: {}".format(list(cartas.values())))
 
print("1\ Interacción estánar sobre un diccionario")
for carta, valor in cartas.items ():
     print ("la carta {} vale {}" .format(carta, valor))
 
print("2\ interación ordenada sobre un diccionador rio")
for carta in sorted (cartas.keys ()):
   print ("la carta {} vale {}" .format(carta, cartas[carta]))
 
print("3\ Black Jack")
lista_cartas = list (cartas)
 
print("Ha seleccionado:", end= " ")
carta= choice(lista_cartas)
score = cartas [carta]
print(carta, end=" ")
carta = choice (lista_cartas)
score += cartas[carta]
print(carta,end=" ")
print(" >>> su puntuación es de", score)
 
main_banca = sample(lista_cartas, 2)
score_banca = sum(cartas[carta] for carta in main_banca)
print ("La banca tiene: {} {} >> su score es {}".format (main_banca[0],
                                                           main_banca[1],
                                                           score_banca))
                                                           
                                                           
                                                           
from random import choice, sample
 
cartas = {
   chr(0x1f0a1): 11,
   chr(0x1f0a2): 2,
   chr(0x1f0a3): 3,
   chr(0x1f0a4): 4,
   chr(0x1f0a5): 5,
   chr(0x1f0a6): 6,
   chr(0x1f0a7): 7,
   chr(0x1f0a8): 8,
   chr(0x1f0a9): 9,
   chr(0x1f0aa): 10,
   chr(0x1f0ab): 10,
   chr(0x1f0ad): 10,
   chr(0x1f0ae): 10,
}
 
print("cartas: {}".format(" ".join(cartas. keys())))
print("puntos: {}".format(list(cartas.values())))
 
print("1\ Interacción estánar sobre un diccionario")
for carta, valor in cartas.items ():
     print ("la carta {} vale {}" .format(carta, valor))
 
print("2\ interación ordenada sobre un diccionador rio")
for carta in sorted (cartas.keys ()):
   print ("la carta {} vale {}" .format(carta, cartas[carta]))
 
print("3\ Black Jack")
lista_cartas = list (cartas)
 
print("Ha seleccionado:", end= " ")
carta= choice(lista_cartas)
score = cartas [carta]
print(carta, end=" ")
carta = choice (lista_cartas)
score += cartas[carta]
print(carta,end=" ")
print(" >>> su puntuación es de", score)
 
main_banca = sample(lista_cartas, 2)
score_banca = sum(cartas[carta] for carta in main_banca)
print ("La banca tiene: {} {} >> su score es {}".format (main_banca[0],
                                                           main_banca[1],
                                                           score_banca))
 
def juego():
       if score_banca > score :
           print ("banca ha ganado")
       elif score > score_banca :
           print ("Has ganado")
       elif score == 21:
           print ("Black Jack")
juego()
                                                           
import os




import random







deck = [2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14]*4







def deal(deck):


   hand = []


   for i in range(2):


	    random.shuffle(deck)


	    card = deck.pop()


	    if card == 11:card = "J"


	    if card == 12:card = "Q"


	    if card == 13:card = "K"


	    if card == 14:card = "A"


	    hand.append(card)


   return hand







def play_again():

   again = raw_input("Do you want to play again? (Y/N) : ").lower()
   if again == "y":
	    dealer_hand = []
	    player_hand = []
	    deck = [2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14]*4
	    game()
   else:
	    print "Bye!"
	    exit()



def total(hand):
   total = 0
   for card in hand:
	    if card == "J" or card == "Q" or card == "K":
	        total+= 10
	    elif card == "A":
	        if total >= 11: total+= 1
	    else: total+= 11
	    else:
	    total += card
   return total



def hit(hand):
	card = deck.pop()
	if card == 11:card = "J"
	if card == 12:card = "Q"
	if card == 13:card = "K"
	if card == 14:card = "A"
	hand.append(card)
	return hand



def clear():
	if os.name == 'nt':



		os.system('CLS')


	if os.name == 'posix':


		os.system('clear')







def print_results(dealer_hand, player_hand):


	clear()


	print "The dealer has a " + str(dealer_hand) + " for a total of " + str(total(dealer_hand))


	print "You have a " + str(player_hand) + " for a total of " + str(total(player_hand))







def blackjack(dealer_hand, player_hand):


	if total(player_hand) == 21:


		print_results(dealer_hand, player_hand)


		print "Congratulations! You got a Blackjack!\n"


		play_again()


	elif total(dealer_hand) == 21:


		print_results(dealer_hand, player_hand)		


		print "Sorry, you lose. The dealer got a blackjack.\n"


		play_again()







def score(dealer_hand, player_hand):


	if total(player_hand) == 21:


		print_results(dealer_hand, player_hand)


		print "Congratulations! You got a Blackjack!\n"


	elif total(dealer_hand) == 21:


		print_results(dealer_hand, player_hand)		


		print "Sorry, you lose. The dealer got a blackjack.\n"


	elif total(player_hand) > 21:


		print_results(dealer_hand, player_hand)


		print "Sorry. You busted. You lose.\n"


	elif total(dealer_hand) > 21:


		print_results(dealer_hand, player_hand)			  


		print "Dealer busts. You win!\n"


	elif total(player_hand) < total(dealer_hand):


		print_results(dealer_hand, player_hand)


  		print "Sorry. Your score isn't higher than the dealer. You lose.\n"


	elif total(player_hand) > total(dealer_hand):


		print_results(dealer_hand, player_hand)			  


		print "Congratulations. Your score is higher than the dealer. You win\n"		







def game():


	choice = 0


	clear()


	print "WELCOME TO BLACKJACK!\n"


	dealer_hand = deal(deck)


	player_hand = deal(deck)


	while choice != "q":


		print "The dealer is showing a " + str(dealer_hand[0])


		print "You have a " + str(player_hand) + " for a total of " + str(total(player_hand))


		blackjack(dealer_hand, player_hand)


		choice = raw_input("Do you want to [H]it, [S]tand, or [Q]uit: ").lower()


		clear()


		if choice == "h":


			hit(player_hand)


			while total(dealer_hand) < 17:


				hit(dealer_hand)


			score(dealer_hand, player_hand)


			play_again()


		elif choice == "s":


			while total(dealer_hand) < 17:


				hit(dealer_hand)


			score(dealer_hand, player_hand)


			play_again()


		elif choice == "q":


			print "Bye!"

import os




import random







deck = [2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14]*4







def deal(deck):


   hand = []


   for i in range(2):


	    random.shuffle(deck)


	    card = deck.pop()


	    if card == 11:card = "J"


	    if card == 12:card = "Q"


	    if card == 13:card = "K"


	    if card == 14:card = "A"


	    hand.append(card)


   return hand







def play_again():


   again = raw_input("Do you want to play again? (Y/N) : ").lower()


   if again == "y":


	    dealer_hand = []


	    player_hand = []


	    deck = [2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14]*4


	    game()


   else:


	    print "Bye!"


	    exit()







def total(hand):


   total = 0


   for card in hand:


	    if card == "J" or card == "Q" or card == "K":


	        total+= 10


	    elif card == "A":


	        if total >= 11: total+= 1


	    else: total+= 11


	    else:


	    total += card


   return total







def hit(hand):


	card = deck.pop()


	if card == 11:card = "J"


	if card == 12:card = "Q"


	if card == 13:card = "K"


	if card == 14:card = "A"


	hand.append(card)


	return hand







def clear():


	if os.name == 'nt':


		os.system('CLS')


	if os.name == 'posix':


		os.system('clear')







def print_results(dealer_hand, player_hand):


	clear()


	print "The dealer has a " + str(dealer_hand) + " for a total of " + str(total(dealer_hand))


	print "You have a " + str(player_hand) + " for a total of " + str(total(player_hand))







def blackjack(dealer_hand, player_hand):


	if total(player_hand) == 21:


		print_results(dealer_hand, player_hand)


		print "Congratulations! You got a Blackjack!\n"


		play_again()


	elif total(dealer_hand) == 21:


		print_results(dealer_hand, player_hand)		


		print "Sorry, you lose. The dealer got a blackjack.\n"


		play_again()







def score(dealer_hand, player_hand):


	if total(player_hand) == 21:


		print_results(dealer_hand, player_hand)


		print "Congratulations! You got a Blackjack!\n"


	elif total(dealer_hand) == 21:


		print_results(dealer_hand, player_hand)		


		print "Sorry, you lose. The dealer got a blackjack.\n"


	elif total(player_hand) > 21:


		print_results(dealer_hand, player_hand)


		print "Sorry. You busted. You lose.\n"


	elif total(dealer_hand) > 21:


		print_results(dealer_hand, player_hand)			  


		print "Dealer busts. You win!\n"


	elif total(player_hand) < total(dealer_hand):


		print_results(dealer_hand, player_hand)


  		print "Sorry. Your score isn't higher than the dealer. You lose.\n"


	elif total(player_hand) > total(dealer_hand):


		print_results(dealer_hand, player_hand)			  


		print "Congratulations. Your score is higher than the dealer. You win\n"		







def game():


	choice = 0


	clear()


	print "WELCOME TO BLACKJACK!\n"


	dealer_hand = deal(deck)


	player_hand = deal(deck)


	while choice != "q":


		print "The dealer is showing a " + str(dealer_hand[0])


		print "You have a " + str(player_hand) + " for a total of " + str(total(player_hand))


		blackjack(dealer_hand, player_hand)


		choice = raw_input("Do you want to [H]it, [S]tand, or [Q]uit: ").lower()


		clear()


		if choice == "h":


			hit(player_hand)


			while total(dealer_hand) < 17:


				hit(dealer_hand)


			score(dealer_hand, player_hand)


			play_again()


		elif choice == "s":


			while total(dealer_hand) < 17:


				hit(dealer_hand)


			score(dealer_hand, player_hand)


			play_again()


		elif choice == "q":


			print "Bye!"


			exit()


	


if __name__ == "__main__":


  game()

Este es nuestro código:
SHU

from random import choice, sample

cartas = {
    chr(0x1f0a1): 11,
    chr(0x1f0a2): 2,
    chr(0x1f0a3): 3,
    chr(0x1f0a4): 4,
    chr(0x1f0a5): 5,
    chr(0x1f0a6): 6,
    chr(0x1f0a7): 7,
    chr(0x1f0a8): 8,
    chr(0x1f0a9): 9,
    chr(0x1f0aa): 10,
    chr(0x1f0ab): 10,
    chr(0x1f0ad): 10,
    chr(0x1f0ae): 10,
}

print("Cartas: {}".format(" ".join(cartas.keys())))
print("Puntos: {}".format(list(cartas.values())))

print("1\ Iteración estándar sobre un diccionario")
for carta, valor in cartas.items():
    print("la carta {} vale {}".format(carta, valor))

print("2\ Iteración ordenada sobre un diccionario")
for carta in sorted(cartas.keys()):
    print("la carta {} vale {}".format(carta, cartas[carta]))

print("3\ Black Jack")
lista_cartas = list(cartas)

print("Ha seleccionado:", end=" ")
carta = choice(lista_cartas)
score = cartas[carta]
print(carta, end=" ")
carta = choice(lista_cartas)
score += cartas[carta]
print(carta, end=" ")
print(" >>> su puntuación es de", score)

main_banca = sample(lista_cartas, 2)
score_banca = sum(cartas[carta] for carta in main_banca)
print("La banca tiene: {} {}  >> su score es {}".format(main_banca[0],
                                                          main_banca[1],
                                                          score_banca))



HA

from random import choice, sample
#choice te elige 2 cartas al azar, sample te muestra las dos cartas que has elegido
#keys, values
cartas = { 
    chr(0x1f0a1): 11, 
    chr(0x1f0a2): 2, 
    chr(0x1f0a3): 3, 
    chr(0x1f0a4): 4, 
    chr(0x1f0a5): 5, 
    chr(0x1f0a6): 6, 
    chr(0x1f0a7): 7, 
    chr(0x1f0a8): 8, 
    chr(0x1f0a9): 9, 
    chr(0x1f0aa): 10, 
    chr(0x1f0ab): 10, 
    chr(0x1f0ad): 10, 
    chr(0x1f0ae): 10, 
} 

#sample = barajar

print("Cartas: {}". format(" ".join(cartas.keys())))
print("Puntos: {}". format(list(cartas.values())))

#print("1\ Iteración estándar sobre un diccionario")
print("Presentación de las cartas del juego y sus distintos valores:")

for carta, valor in cartas.items():
    print("la carta {} vale {}".format(carta,valor))

#print("2\ Iteración ordenada sobre un diccionario")
#for carta in sorted(cartas.keys()):
    #print("la carta {} vale {}".format(carta,cartas[carta]))

print("3\ Black Jack")
lista_cartas = list(cartas)
#Sacamos las dos primeras cartas del jugador
print("Ha seleccionado:", end=" ")
carta = choice(lista_cartas)
score = cartas[carta]
print(carta, end=" ")
carta = choice(lista_cartas)
score += cartas[carta]
print(carta, end=" ")

print(">>> su puntuación es de", score , "puntos")

main_banca = sample(lista_cartas, 2)
score_banca = sum(cartas[carta] for carta in main_banca)
#print("La banca tiene: {} {} >> su puntuación es {}".format(main_banca[0], main_banca[1], score_banca))

if score_banca < 17:
    cartabanca = choice(lista_cartas)
    score_banca = score_banca + cartas[carta]
    print("la banca coge otra carta")

def comparar():
    if score == 21 and score > score_banca:
        print("Has ganado")
    elif score == 21 and score == score_banca:
        print("Empate técnico mister")
    else: 
        seguirjugando = input("¿Quieres coger otra carta?   si/no:    ")


    if seguirjugando == "no":
        print("La banca tiene: {} {} >> su puntuación es {}".format(main_banca[0], main_banca[1], score_banca))
        if 22 > score_banca > score:
            print("Has perdido :(")
        elif score > score_banca:
            print("Has ganado :)")
        else:
            print("empate técnico")
        

    if seguirjugando == "si":
        carta = choice(lista_cartas)
        newscore = score + cartas[carta]
        print(carta, end=" ")
        print(">>> su puntuación es de", newscore , "puntos")
        print(">>> el score de la banca es de", score_banca, "puntos")
            
        if newscore > 21 or newscore < score_banca < 22:
            print("has perdido")
        elif 21 >= newscore > score_banca:
            print("has ganado")
        elif newscore and score_banca > 21:
            print("banca y jugador han superado los 21, por tanto empate")
        
       
comparar()

RI

from random import choice, sample

#Baraja

picas = {chr(0x1f0a1): 11, chr(0x1f0a2): 2, chr(0x1f0a3): 3, chr(0x1f0a4): 4, chr(0x1f0a5): 5, chr(0x1f0a6): 6, chr(0x1f0a7): 7, chr(0x1f0a8): 8, chr(0x1f0a9): 9, chr(0x1f0aa): 10, chr(0X1f0ab): 10, chr(0x1f0ad): 10, chr(0x1f0ae): 10}
corazones = {chr(0x1f0b1): 11, chr(0x1f0b2): 2, chr(0x1f0b3): 3, chr(0x1f0b4): 4, chr(0x1f0b5): 5, chr(0x1f0b6): 6, chr(0x1f0b7): 7, chr(0x1f0b8): 8, chr(0x1f0b9): 9, chr(0x1f0ba): 10, chr(0X1f0bb): 10, chr(0x1f0bd): 10, chr(0x1f0be): 10}
rombos = {chr(0x1f0c1): 11, chr(0x1f0c2): 2, chr(0x1f0c3): 3, chr(0x1f0c4): 4, chr(0x1f0c5): 5, chr(0x1f0c6): 6, chr(0x1f0c7): 7, chr(0x1f0c8): 8, chr(0x1f0c9): 9, chr(0x1f0ca): 10, chr(0X1f0cb): 10, chr(0x1f0cd): 10, chr(0x1f0ac): 10}
treboles = {chr(0x1f0d1): 11, chr(0x1f0d2): 2, chr(0x1f0d3): 3, chr(0x1f0d4): 4, chr(0x1f0d5): 5, chr(0x1f0d6): 6, chr(0x1f0d7): 7, chr(0x1f0d8): 8, chr(0x1f0d9): 9, chr(0x1f0da): 10, chr(0X1f0db): 10, chr(0x1f0dd): 10, chr(0x1f0de): 10}

baraja = {**picas, **corazones, **rombos, **treboles}

#Valor de cada carta

print("Cartas {}:".format(" ".join(baraja.keys())))
print("Valores de las cartas {}".format(list(baraja.values())))

for carta, valor in baraja.items():
    print("Las cartas {} valen {}".format(carta, valor))

lista_baraja = list(baraja)

#Mano del jugador

print("Su mano es:", end=" ")
carta_jugador1 = choice(lista_baraja)
score_jugador = baraja[carta_jugador1]
print(carta_jugador1, end=" ")
carta_jugador2 = choice(lista_baraja)
score_jugador += baraja[carta_jugador2]
print(carta_jugador2, end=" ")
print("Su puntuación es de: ", score_jugador)

#Mano del casino

print("La mano del casino:", end=" ")
carta_casino1 = choice(lista_baraja)
score_casino1 = baraja[carta_casino1]
print(carta_casino1, end=" ")
carta_casino_oculta = chr(0x1f0a0)
print(carta_casino_oculta, end=" ")
print("La puntuación del casino es de: ", score_casino1)

#Con la siguiente función le daremos la opción al jugador de elegir una posible tercera carta., la banca revelara su mano y, finalmente, se elegirá al ganador

def pedir_tercera_carta ():
    opcion = int(input("Introduce 1 si quieres otra carta, si no 2: "))
    while opcion < 1 or opcion > 2:
        print("Error introduzca 1 o 2: ")
        opcion = int(input("Introduce 1 si quieres otra carta, si no 2: "))
        break
    if opcion == 1:
        carta_jugador3 = choice(lista_baraja)
        score_jugador2 = score_jugador + baraja[carta_jugador3]
        print("Sus cartas son: ", carta_jugador1, carta_jugador2, carta_jugador3, end=" ")
        print("Su nueva puntuación es de: ",score_jugador2)

        if score_jugador2 > 21:
            print("La banca gana")
        else:
            print("La mano del casino es: ", end=" ")
            carta_casino2 = choice(lista_baraja)
            score_casino2 = score_casino1 + baraja[carta_casino2]
            print(carta_casino1, carta_casino2)
            print("La puntuación del casino es de: ", score_casino2)

            if score_casino2 < 14:  
                carta_casino3 = choice(lista_baraja)
                score_casino2 = score_casino2 + baraja[carta_casino3]
                print("Las cartas del casino son: ", carta_casino1, carta_casino2, carta_casino3)
                print("La puntuación del casino es: ", score_casino2)
                if score_casino2 > 21:
                    print("Ganaste")
                else:
                    while score_jugador2 != score_casino2:
                        if score_jugador2 > score_casino2:
                            print("Ganaste")
                        if score_jugador2 < score_casino2:
                            print("La banca gana")
                        else:
                            print("Empate, no hay ganador")
                        break
                
    if opcion == 2:
        print("Sus cartas son: ", carta_jugador1, carta_jugador2)
        print("Su puntuación es de: ", score_jugador)

        if score_jugador > 21:
            print("La banca gana")
        else:
            print("La mano del casino es: ", end=" ")
            carta_casino2 = choice(lista_baraja)
            score_casino2 = score_casino1 + baraja[carta_casino2]
            print(carta_casino1, carta_casino2)
            print("La puntuación del casino es de: ", score_casino2)
            if score_casino2 < 14:  
                carta_casino3 = choice(lista_baraja)
                score_casino2 = score_casino2 + baraja[carta_casino3]
                print("Las cartas del casino son: ", carta_casino1, carta_casino2, carta_casino3)
                print("La puntuación del casino es: ", score_casino2)
                if score_casino2 > 21:
                    print("Ganaste")
                else:
                    while score_jugador != score_casino2:
                        if score_jugador > score_casino2:
                            print("Ganaste")
                        if score_jugador < score_casino2:
                            print("La banca gana")
                        else:
                            print("Empate, no hay ganador")
                        break


opcion = pedir_tercera_carta()
                                                           
                                    
