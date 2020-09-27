# a simple parser for python. use get_number() and get_word() to read
def parser():
    while 1:
        data = list(input().split(' '))
        for number in data:
            if len(number) > 0:
                yield(number)   

input_parser = parser()

def get_word():
    global input_parser
    return next(input_parser)

def get_number():
    data = get_word()
    try:
        return int(data)
    except ValueError:
        return float(data)

# numpy and scipy are available for use
import numpy as np
import scipy

n = get_number()
array = []
shoes = []

for i in range (n):
    size = get_number()
    side = get_word()
    shoes = [size, side]
    array.append(shoes)

array.sort()
array.append([999, 'T'])


pairs = 0
firstRun = True
numOfL = 0
numOfR = 0
currentList = [42069,'L']

for element in array:
    if firstRun:
        firstRun = False
        currentList = element
        
    while True:
        if currentList == element:
            numOfL = numOfL + 1
            break
        else:
            if ((currentList[1] != element[1]) and (currentList[0] == element[0])):
                numOfR = numOfR + 1
                break
            elif currentList[0] != element[0]:
                pairs = pairs + min(numOfL, numOfR)
                currentList = element
                numOfL = 0
                numOfR = 0
            
pairs = pairs + min(numOfL, numOfR)      

print(pairs)
