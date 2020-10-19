INST126 PROJECT 2: CREATING A HANGMAN GAME
IN THIS CODE, I WAS ABLE TO CREATE A SIMPLE HANGMANGAME BY UTILIZING IF STATEMENTS, USING THE DECRYPT FUNCTION, DEFINING FUNCTIONS, ETC.
THE GAME PROMPTS USERS TO ENTER LETTER GUESSES AS WELL AS PRESENTS DASHES INDICATING HOW MANY LETTERS ARE IN THE RANDOMLY CHOSEN ENCRYPTED WORD.
USERS CAN THEN ENTER LETTER GUESSES, IF THE LETTER GUESS IS INCORRECT; THE USER LOSES A LIFE (INITIALLY STARTING AT 10 LIVES). IF USERS ARE ABLE TO GUESS 
ALL LETTERS TO THE RANDOMLY CHOSEN WORD, THEY ARE PRESENTED WITH A WINNING STATEMENT AS WELL AS A DECRYPTION OF THE RANDOM ENCRYPTED WORD

CODE HAS BEEN PLUGGED BELOW:
import random
words = ["WHDSPQZ","XHO","TTDBFRT","QQJYF","ENQD","DNPK","CNTR","EHWHOD","TSVMOHOF","XNOCFQGTM"]
import string

def correct_word(words):
    word = random.choice(words) # randomly chooses something from the words list
    return word

def decrypt(ciphertext):
    plaintext = ""
    i=0
    for i in range (0,len(ciphertext)):
        if i % 2 == 0:
            plain_ascii = ciphertext[i]
            cipher_ascii = ord(plain_ascii) - 1
            plaintext = plaintext + str(chr(cipher_ascii))
        if i % 2 == 1:
            plain_ascii = ciphertext[i]
            cipher_ascii = ord(plain_ascii) + 1
            plaintext = plaintext + str(chr(cipher_ascii))
    
    return plaintext
    


def hangman():
    word = correct_word(words)
    word_letters = set(word)  # letters in the word
    alphabet = set(string.ascii_uppercase)
    used_letters = set() # the letters the user has guessed
    
    lives = 10
    
    #gaining user input
    while len(word_letters) > 0 and lives > 0:
        print('You have', lives, 'lives left and you have used these letters: ', ' '.join(used_letters))
         
        # what current word is (ie W - R D)
        word_list = [letter if letter in used_letters else '-' for letter in word]
        print('Current word: ',' '.join(word_list))

        user_letter = input('Guess a letter: ').upper()
        if user_letter in alphabet - used_letters:
            used_letters.add(user_letter)
            if user_letter in word_letters:
                word_letters.remove(user_letter)
            
            else:
                lives = lives - 1  # takes away a life if wrong
                print('That letter is not in the word')
    
        elif user_letter in used_letters:
            print('You already used that letter... Try again.')
        
        else:
            print('Invalid Character... Try again.')
            
    
    # Results here when len(word_letters) == 0 OR when lives == 0        
    if lives == 0:
        print('You died, the word was', word)
    else:            
        print('You guessed the word', word, 'The decoded message is', decrypt(word), '!')

        
            

hangman()
    
