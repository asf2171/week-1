# week-1
#AForsberg Week 1 Tutorial 

#Andrea Forsberg
#Datamining Week 1 Assignment 


import random

class Player:
    
    playerID = 0
    pot = 0.0
    lastCard = 0
    
    def __init__(self, inputID, startingPot):
        self.playerID = inputID
        self.pot = startingPot
        
    def play(self, dealerCard):
        self.lastCard = random.choice(cards)
        
        if self.lastCard < dealerCard:
            self.pot -= gameStake
            return 'player ' + str(self.playerID) + ' Lose, ' + str(self.lastCard) + ' vs ' + str(dealerCard)
        else:
            self.pot += gameStake
            return 'player ' + str(self.playerID) + ' Win, ' + str(self.lastCard) + ' vs ' + str(dealerCard)
        
    def returnPot(self):
        return self.pot
        
    def returnID(self):
        return self.playerID


def playHand(players):
    
    for player in players:
        print player.play(random.choice(cards))
        
def checkBalances(players):
    
    for player in players:
        print 'player ' + str(player.returnID()) + ' has $' + str(player.returnPot()) + ' left.'
        

gameStake = 50  
cards = range(10)

players = []

for i in range(2):
    players.append(Player(i, 1000))

for i in range(5):
    print ''
    print 'start game ' + str(i)
    playHand(players)

print ''
print 'game results:'
checkBalances(players)

#Outcome 


start game 0
player 0 Lose, 0 vs 7
player 1 Win, 8 vs 6

start game 1
player 0 Win, 8 vs 6
player 1 Win, 6 vs 0

start game 2
player 0 Lose, 4 vs 8
player 1 Lose, 1 vs 5

start game 3
player 0 Lose, 6 vs 9
player 1 Win, 9 vs 5

start game 4
player 0 Lose, 1 vs 6
player 1 Lose, 0 vs 3

game results:
player 0 has $850 left.
player 1 has $1050 left.
