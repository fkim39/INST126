# INST126 PROJECT 1
IN THIS CODE I WAS ABLE TO CREATE A BASIC CALCULATOR USING VARIABLES, NUMERIC OPERATORS, AND CONDITIONAL STATEMENTS

print('Choose an operation: ')
print('1. Addition')
print('2. Subtraction')
print('3. Multiplication')
print('4. Division')

##In these first 5 lines of code, I utilize the print command to present to users what operators they may choose calculate


choose = input('Enter operation: ')

##Because users have to select an operation I utilize an if command and prompt them to select a certain operation

if choose == '1':
    num1 = int(input('Enter first value:'))
    num2 = int(input('Enter second value:'))
    print(num1 + num2)

##If users choose the number 1, then I prompt them to enter two integer values and print the sum of both

if choose == '2':
    num1 = int(input('Enter first value: '))
    num2 = int(input('Subtracted by second value: '))
    print(num1 - num2)
    
##If users choose the number 2, then I prompt them to enter a first integer value and a
##second integer value to subtract from the first and print the difference of both
    
if choose == '3':
    num1 = int(input('Enter first value: '))
    num2 = int(input('Enter second value: '))
    print(num1 * num2)
    
####If users choose the number 3, then I prompt them to enter two integer values and print the product of both

if choose == '4':
    num1 = int(input('Enter first value: '))
    num2 = int(input('Divided by second value: '))
    print(num1 / num2);

##If users choose the number 4, then I prompt them to enter a first integer value and a
##second integer value to divide from the first and print the quotient of both
    
