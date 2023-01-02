# python

'''
ROLL NO : 46,53,55
CLASS : KOC01
GAME NAME : Rock, paper, scissor'''

import random

#no.of rounds.
n=0
def rounds():
    n=int(input("\nSelect Number of ROUNDS: "))
    return n

#loops for game
def rps(n,name,counter_c,counter_p):
    for i in range(0,n):
        actions=[1,2,3]
        comp_input=random.choice(actions)
        print("\nROUND "+str(i+1))
        print(str(name)+":")
        user_input=int(input("Enter your choice: "))
        if user_input > 3 or user_input < 1:
            print("\nInvalid input\nDISQUALIFIED")
        else:
            print("COMPUTER: "+str(comp_input))
            if user_input==comp_input:
                print("\nSTATUS: Draw")
            #for computer
            elif (user_input == 1 and comp_input == 2) or (user_input == 2 and comp_input == 3) or (user_input == 3 and comp_input == 1):
                print("\nSTATUS: Computer Win")
                counter_c+=1
                print("SCORE: Computer " + str(counter_c) + "\t" + str(name) + " " + str(counter_p))
            #for user
            elif (user_input == 1 and comp_input == 3) or (user_input == 2 and comp_input == 1) or (user_input == 3 and comp_input == 2):
                print("\nSTATUS: You win")
                counter_p+=1
                print("SCORE: computer " + str(counter_c) + "\t" + str(name) + " " + str(counter_p))

    return (counter_c,counter_p)


    def winner (counter_c,counter_p):
        if counter_c==counter_p:
            print("\nFINAL RESULT:------MATCH DRAW------")
        elif counter_c > counter_p:
            print("\nFINAL RESULT:------COMPUTER WIN------\n BETTER LUCK NEXT TIME")
        else:
            print("\nFINAL RESULT:------YOU WIN------\n-----------CONGRATULATIONS------------")
def play_again():
    inp=str(input("\n Play Again? (y/n):"))
    if inp.lower() != "y":
        print("\n------------THANK YOU FOR PLAYING------------")
        return 0
    else:
        return 1

def game():
    player=False
    while player==False:
        r=rounds()
        result=rps(r,name,counter_c,counter_p)
        count_c=result[0]
        count_p=result[1]
        winner = (count_c,count_p)
        play=play_again()

        if play==1:
            continue
        else:
            player=True


print("!!!ROCK PAPER SCISSOR!!!")
print("*** PRESS ENTER AFTER EVERY INPUT ***")
#player input
name=input("\nEnter player name: ")
name=str(name.upper())
print("\nPLAYER 1:"+name)
print("PLAYER 2: COMPUTER")
print("\n               "+str(name)+" v/s COMPUTER")
print("\n For ROCK: PRESS 1\tFor PAPER: PRESS 2\tFor SCISSOR: PRESS 3")
print("LET'S BEGIN->->->")
counter_c=0
counter_p=0
game()
            
