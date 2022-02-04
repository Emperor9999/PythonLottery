from random import randint


print( "WELCOME TO THE LOTTERY! WIN UP TO $100,000,000!" )
NUMBER_OF_PLAYERS = int(input( "Enter the number of players: " ))

total = []

for a in range (NUMBER_OF_PLAYERS):
  total.append(0)

names = []

for h in range (NUMBER_OF_PLAYERS):
  print("Enter name of player", (h + 1), ": " )
  names.append(str(input()))
  h += 1	

print("_____________________________________________________________________________________________________________________")

for p in range (NUMBER_OF_PLAYERS):
		
  print( "\nWelcome", names [p] )
  for j in range (10):
			
    lottery = randint(0,100)
	
    print("------------------------------------------------------------------------------------------------------")

    print( "\nEnter your lottery pick (two digits): " )
    guess = int(input())
		
    lotteryDigit1 = lottery / 10
    lotteryDigit2 = lottery % 10

    guessDigit1 = guess / 10
    guessDigit2 = guess % 10

    print( "The lottery number is", lottery )
    w = "\nWINNER WINNER WINNER WINNER WINNER WINNER WINNER WINNER WINNER WINNER WINNER WINNER WINNER WINNER WINNER"
    w2 = "winner winner winner!"

    print()

    if (guess == lottery):
				
      print( "Exact match: you win $100,000,000" , "\n" , w , w , w , w , w , w , w , w , w , w , w , w , w , w , w , w , w , w , w )
      total[p] += 100000000
				
    elif (guessDigit2 == lotteryDigit1 and guessDigit1 == lotteryDigit2):
				
      print( "Match all digits: you win $100,000", "\n", w2)
      total[p] += 100000
				
    elif (guessDigit1 == lotteryDigit1 or guessDigit1 == lotteryDigit2 or guessDigit2 == lotteryDigit1 or guessDigit2 == lotteryDigit2):
				
      print( "Match one digit: you win $100" + "\n" + "winner!")
      total[p] += 100
				
    else:
				
      print( "Sorry, your guess matches no digits" )
				

    print()

    if ((lottery - guess == 0 and lottery - guess >= 0 or guess - lottery == 0 and guess - lottery >= 0 )):
				
      print( w )
				
    elif ((lottery - guess < 2 and lottery - guess >= 0 or guess - lottery < 2 and guess - lottery >= 0 )):
				
      print( "You were less than 2 away! You win $10,000", "\n", w2 )
      total[p] += 10000
				
    elif ((lottery - guess < 5 and lottery - guess >= 0 or guess - lottery < 5 and guess - lottery >= 0 )):
				
      print( "You were less than 5 away! You win $1,000", "\n", w2 )
      total[p] += 1000
				
    elif ((lottery - guess < 10 and lottery - guess >= 0 or guess - lottery < 10 and guess - lottery >= 0 )):
				
      print( "You were less than ten away! You win $100", "\n", w2 )
      total[p] += 100
				
    else:
				
      print( "Sorry, your guess is very far off" )
				

    print( "\nYour total now is:", total[p] )
    j += 1
			
  print( "\n\n\n______________________________________________________________________________________________________" )
  print( "Your final 10-turn total is: $", total[p] )
		
  if (total[p] >= 100000000):
    print( "Wow, you're good at this!" )
  elif (total[p] >= 10000000):
    print( "Amazing job!" )
  elif (total[p] >= 1000000):
    print( "Great job!")
  elif (total[p] >= 100000):
    print( "Pretty good!" )
  elif (total[p] >= 10000):
    print( "Not bad at all" )
  elif (total[p] >= 1000):
    print( "Okay job" )
  elif (total[p] >= 100):
    print( "Could've been better" )
  else:
    print ( "Sorry, better luck next time" )
			
  if (p < (NUMBER_OF_PLAYERS - 1)):
    print( "Get ready", names[p + 1] )
  else:
    print( "ready to see the game results?" )

  print( "************************************************************************************************************" )
  print( "\n\n\n" )
		
  p += 1

print( "\n\n" )
print( "Game results:" )
print()
           
max = 0 
         
for x in range (len(total)):
  if (total[x] > max): 
    max = total[x]
  x += 1

		
for f in range (len(total)):
  if (max == total[f]):
    print(names[f], "WON! WITH A TOTAL OF $", total[f])
  f += 1

print( "\nScores: " )
print( "\n" )
		
for z in range (len(total)):
  print( names [z], ": $", total[z] )	
  z += 1
	
