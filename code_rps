#stage 5/5: rock-paper-scissors+ game complete
import random

def rps_game():
    default = []
    rating = 0
    name = input("Enter your name: ")
    print("Hello, " + name)

    def power(opt, us, co):
        k = ' '.join(opt.copy()).split(us)
        k = ' '.join(k[::-1])
        m = k.split()
        p = [n for n in range(0, (round(len(m) / 2))) if co in m[n]]
        if p:
            co > us
            print(f'Sorry, but the computer chose {co}')
        else:
            us > co
            print(f'Well done. The computer chose {co} and failed')

    current_scores = open('rating.txt', 'r')
    for i in current_scores.readlines():
        if name in i:
            rating = int(i.strip().split()[1])
    options = input()
    if options == '':
        default = ['rock', 'paper', 'scissors']
    else:
        for i in options.split(','):
            default.append(i)
    print("Okay, let's start")
    
    while True:
        user = input('')
        comp = random.choice(default)
        if user == '!exit':
            print('Bye!')
            break
        elif user == '!rating':
            print('Your rating: ', rating)
        elif user != '!exit' and user not in default:
            print('Invalid Input')
            continue
        elif user == comp:
            print(f'There is a draw ({user})')
            rating += 50
        elif user == 'rock' and comp == 'paper':
            print('Sorry, but the computer chose paper')
        elif user == 'paper' and comp == 'scissors':
            print('Sorry, but the computer chose scissors')
        elif user == 'scissors' and comp == 'rock':
            print('Sorry, but the computer chose rock')
        elif user == 'paper' and comp == 'rock':
            print('Well done. The computer chose rock and failed')
            rating += 100
        elif user == 'scissors' and comp == 'paper':
            print('Well done. The computer chose paper and failed')
            rating += 100
        elif user == 'rock' and comp == 'scissors':
            print('Well done. The computer chose scissors and failed')
            rating += 100
        else:
            power(default, user, comp)
            if user > comp:
                rating += 100
    current_scores.close()


rps_game()
