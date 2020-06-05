# list_examples
#practicing with lists in various forms
#python list, tuples and string exercises
#small 1 sum the number
'''
small_numbers = (8,4,5,7,2,5,1)
sum_numbers = sum(small_numbers)
print(sum_numbers)
'''
#2 small, largest numbers, print largest number
'''
small_numbers = [8,4,5,7,2,5,1]
small_numbers.sort()
print("largest numbers: %s" % small_numbers[-3:-1])
'''
#3 small, smallest number
'''
small_numbers = [8,4,5,7,2,5,1]
small_numbers.sort()
print("smallest number: %s" % small_numbers[0])
'''
#4 small even numbers
'''
list1 = [2, 7, 5, 64, 14]
for num in list1: 
    if num % 2 == 0: 
       print(num)
'''
#5 small positive numbers
'''
list2 = [-20, -1, 4, 5, -43, 52]
for i in list2:
    if i > 0:
        print(i)
'''
#6 small positive numbers 2 
'''
nums = [34, 1, 0, -23]
print("Original list: ",nums)
new_nums = list(filter(lambda x: x >0, nums))
print("Positive numbers list: ",new_nums)
'''
#7 small multiply a list
'''
my_list = [1, 2, 3, 4, 5]
my_new_list = [i * 5 for i in my_list]

print(my_new_list)
[5, 10, 15, 20, 25]
'''
#8 reverse a string
'''
txt = "Hello World"[::-1]
print(txt)
'''
#1 medium multipy vectors
'''
list1 = [2,4,5]
list2 = [2,3,6]
products = [a * b for a, b in zip(list1, list2)]

print(products)
'''
#2 medium matrix addition
'''
a = [[1, 2, 3], [4, 5, 6]]
print(a[0])
print(a[1])

b = a[0]
print(b)
print(a[0][2])

a[0][1] = 7
print(a)

print(b)
b[2] = 9
print(a[0])
print(b)
'''
#extra practice with matrix
'''
row, cols = (5,5)
arr = [[0]*cols]*row
for row in arr:
    print(row)
'''
#3 medium matrix addition
'''
X = [[12,7,3],
    [4 ,5,6],
    [7 ,8,9]]

Y = [[5,8,1],
    [6,7,3],
    [4,5,9]]

result = [[0,0,0],
         [0,0,0],
         [0,0,0]]
for i in range(len(X)):
   for j in range(len(X[0])):
       result[i][j] = X[i][j] + Y[i][j]

for r in result:
   print(r)
'''
#4 medium de-up remove duplicates
'''
mylist = ["a", "b", "a", "c", "c"]
mylist = list(dict.fromkeys(mylist))
print(mylist)
'''
#5 medium leetspeak 
'''
s = raw_input("Enter a string: ")

leet = {'a': '4', 'e': '3', 'i': '1', 'o': '0', 'A': '4', 'E': '3', 'I': '1', 'O': '0', 'S': '5', 'T': '7'}

for k, v in leet.items(): 
    s = s.replace(k, v)

print(s)
'''
#6 medium long-long vowels ----need work on getting vowels longer
'''
sentence = raw_input('Enter your sentence: ' )
for letter in sentence:
    if letter in 'aeiou':
        print(sentence)
'''
#7 medium ceasar cipher---needs review
'''
def encrypt(string, shift):
 
  cipher = ''
  for char in string: 
    if char == ' ':
      cipher = cipher + char
    elif  char.isupper():
      cipher = cipher + chr((ord(char) + shift - 65) % 26 + 65)
    else:
      cipher = cipher + chr((ord(char) + shift - 97) % 26 + 97)
  
  return cipher
 
text = raw_input("enter string: ")
s = int(input("enter shift number: "))
print("original string: ", text)
print("after encryption: ", encrypt(text, s))
'''
#1 large Tic-tac-toe
'''
def tic_tac_toe():
    board = [1, 2, 3, 4, 5, 6, 7, 8, 9]
    end = False
    win_commbinations = ((0, 1, 2), (3, 4, 5), (6, 7, 8), (0, 3, 6), (1, 4, 7), (2, 5, 8), (0, 4, 8), (2, 4, 6))

    def draw():
        print(board[0], board[1], board[2])
        print(board[3], board[4], board[5])
        print(board[6], board[7], board[8])
        print()

    def p1():
        n = choose_number()
        if board[n] == "X" or board[n] == "O":
            print("\nYou can't go there. Try again")
            p1()
        else:
            board[n] = "X"

    def p2():
        n = choose_number()
        if board[n] == "X" or board[n] == "O":
            print("\nYou can't go there. Try again")
            p2()
        else:
            board[n] = "O"

    def choose_number():
        while True:
            while True:
                a = input()
                try:
                    a  = int(a)
                    a -= 1
                    if a in range(0, 9):
                        return a
                    else:
                        print("\nThat's not on the board. Try again")
                        continue
                except ValueError:
                   print("\nThat's not a number. Try again")
                   continue

    def check_board():
        count = 0
        for a in win_commbinations:
            if board[a[0]] == board[a[1]] == board[a[2]] == "X":
                print("Player 1 Wins!\n")
                print("Congratulations!\n")
                return True

            if board[a[0]] == board[a[1]] == board[a[2]] == "O":
                print("Player 2 Wins!\n")
                print("Congratulations!\n")
                return True
        for a in range(9):
            if board[a] == "X" or board[a] == "O":
                count += 1
            if count == 9:
                print("The game ends in a Tie\n")
                return True

    while not end:
        draw()
        end = check_board()
        if end == True:
            break
        print("Player 1 choose where to place a cross")
        p1()
        print()
        draw()
        end = check_board()
        if end == True:
            break
        print("Player 2 choose where to place a nought")
        p2()
        print()

    if input("Play again (y/n)\n") == "y":
        print()
        tic_tac_toe()

tic_tac_toe()
'''
#2 matrix multiplication----fix to make 2X2

A = [[12, 7], 
    [4, 5]] 
  
# take a 3x4 matrix     
B = [[5, 8], 
    [6, 7]] 
      
result = [[0, 0], 
        [0, 0]] 
  
# iterating by row of A 
for i in range(len(A)): 
  
    # iterating by coloum of B  
    for j in range(len(B[0])): 
  
        # iterating by rows of B 
        for k in range(len(B)): 
            result[i][j] += A[i][k] * B[k][j] 
  
for r in result: 
    print(r) 
