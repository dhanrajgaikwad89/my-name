# my-name
# Hangman game 
# import
import random
# constants
HANGMAN = (
""""
    ----
    
    |   |
    |
    |
    |
    |
    |
    |
    |
    
----------

""",

"""
    ----
    
    |   |
    |   0
    |
    |
    |
    |
    |
    |

----------

""",

"""
    ----
    
    |   |
    |   0
    |  -+-
    |
    |
    |
    |
    |
----------

""",

"""
    ----
    
    |   |
    |   0
    | /-+-
    | 
    |
    |
    |
    |
----------

""",
 
"""
    ----
    
    |   |
    |   0
    | /-+-/
    | 
    | 
    |
    |
    |
----------

""",

"""
    ----
    |   |
    |   0
    | /-+-/
    |   |
    |   
    |
    |
    |
----------
    
""",

"""
    ----
    |   |
    |   0
    | /-+-/
    |   |
    |   |
    | |
    | |
    |
----------

""",

"""
    ----
    |   |
    |   0
    | /-+-/
    |   |
    |   |
    | |   |
    | |   |
    |
----------

 """)
MAX_WRONG = len (HANGMAN)
WORDS = ("CLAM","PUCK","PYTHON","PHONE","FACEBOOK","GOOGLE","WHATSAPP")
# initialize variables
word = random.choice(WORDS) #the word to be guessed
so_far = "-" * len(word) #one dash for each letter in word to be guessed
wrong = 0 #numer of wrong guesses player has made
used = [] # letters already guessed
print (" Welcome to Hangman. Good luck!")
while wrong < MAX_WRONG and so_far != word:
    print (HANGMAN [wrong])
    print ("\n You've used the following letters: \n",used)
    print ("\n So far, the word is : \n", so_far)
guess = input ("\n\nEnter your guess: ")
guess = guess.upper( )
while guess in used:
    print ("you've already guessed the letter:", guess)
    guess = input("Enter your guess: ")
    guess = guess.upper()
    used.append(guess)
if guess in word:
    print ("\nYes !", guess, "is in the word!")
    #create the new so_far to include guess 
    new = " "
    for i in range(len(word)):
        if guess == word[i]:
            new += guess 
        else:
            new += so_far[i]
    so_far = new 
else:
        print ("\n Sorry,", guess, " isn't in the word.")
        wrong += 1
            
        if wrong == MAX_WRONG:
            print ("HANGMAN[wrong]")
            print ("\n You've been hanged!")
        else:
            print ("\n You guessed it!")
        print ("\n The word was", word)
        input ("\n\n Press the enter key to exit.") 
            
        

   
