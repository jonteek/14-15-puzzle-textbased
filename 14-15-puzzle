import random
class numberPuzzle:
    
    def __init__(self):
        self.board = []
        self.emptySlotPosition = None

    def shuffleBoard(self,inputList,difficulty):
        if difficulty == 1 :
            numberOfInversions = 32
        if difficulty == 2 :
            numberOfInversions = 64
        if difficulty == 3 :
            numberOfInversions = 128
        if difficulty == 4 :
            numberOfInversions = 256
        while (numberOfInversions >= 1):
            positionToChange = random.randint(1,14)
            currentPositionValue = inputList[positionToChange]
            nextPosition = positionToChange + 1
            nextPositionValue = inputList[nextPosition]
            inputList[positionToChange] = nextPositionValue
            inputList[nextPosition] = currentPositionValue
            numberOfInversions -= 1
            
            
            
        
    def initBoard(self,difficulty):
        self.emptySlotPosition = 16
        self.board.append(0)
        for j in range(1,16):
            self.board.append(j)
        self.shuffleBoard(self.board,difficulty)
        self.board.append(' ')
            
    def isComplete(self):
        if sorted(self.board) == self.board:
            return True
        else:
            return False


    def displayBoard(self):
        d = self.board
        
        print('+---------------+---------------+---------------+---------------+')
        print('|\t%s\t|\t%s\t|\t%s\t|\t%s\t|' % (d[1], d[2], d[3], d[4]))
        print('+---------------+---------------+---------------+---------------+') 
        print('|\t%s\t|\t%s\t|\t%s\t|\t%s\t|' % (d[5], d[6], d[7], d[8]))
        print('+---------------+---------------+---------------+---------------+')
        print('|\t%s\t|\t%s\t|\t%s\t|\t%s\t|' % (d[9], d[10], d[11], d[12]))
        print('+---------------+---------------+---------------+---------------+')
        print('|\t%s\t|\t%s\t|\t%s\t|\t%s\t|' % (d[13], d[14], d[15], d[16]))
        print('+---------------+---------------+---------------+---------------+')
        
    def allowedMoves(self):
        position = self.emptySlotPosition

        if position in [2,3]:
            return [position + 1, position - 1, position + 4]

        elif position == 1:
		return [position + 1, position + 4]

        elif position == 4:
            return [position + 4,position - 1]
        
        elif position in [5,9]:
            return [position + 1, position + 4, position - 4]

        elif position in [6,7,10,11]:
            return [position + 1 , position - 1, position + 4, position - 4]

        elif position in [8,12]:
            return [position - 1, position + 4,position - 4]
        
        elif position == 13:
            return [position + 1, position - 4]

        elif position in [14,15]:
            return [position + 1, position - 1, position - 4]
        
        elif position == 16:
            return [position - 1, position - 4]

    def changePosition(self,newPosition):
        currentPos = self.emptySlotPosition
        currentPosContents = self.board[currentPos]
        newPosContents = self.board[newPosition]
        self.board[currentPos] = newPosContents
        self.board[newPosition] = currentPosContents
        self.emptySlotPosition = newPosition
        
        
            


        
        
        
            
            
        
        

        
a = numberPuzzle()
print("Choose Difficulty Between 1 and 4\n")
difficulty = int(input())
a.initBoard(difficulty)
print("\nWelcome to the fifteen puzzle")
print("\nPress 0 to quit the game")
a.displayBoard()
while a.isComplete() == False:
    allowedPositions = a.allowedMoves()
    print("The the positions of the squares that are possible to move are")
    print(allowedPositions)
    print("\n")
    x = int(input())
    if x == 0 :
        break
    elif x not in allowedPositions:
        print("You cannot move the square in that position")
        print("The positions of the squares that you are allowed to move are")
        print(allowedPositions)
        print("\n")
        
    else:
        a.changePosition(x)
    a.displayBoard()
print("Puzzle Completed")
