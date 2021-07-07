# Parallelogram-Determiner
This program determines whether an object is a parallelogram. If it is, it will proceed on to determine if it is a rectangle or rhombus.

import math
class Parallelogram:
    def isParallelogram(self):
        Parallelogram = bool(True)
        sides = input("Are opposite sides congruent? (Enter 'Y' or 'y' for yes): ")
        if(sides != "y" and sides != "Y"):
            Parallelogram = False
            return Parallelogram
        else:
            Parallelogram = True
        parallel = input("Are opposite sides parallel? (Enter 'Y' or 'y' for yes): ")
        if(parallel != "y" and parallel != "Y"):
            Parallelogram = False
            return Parallelogram
        else:
            Parallelogram = True
        angles = input("Are opposite angles congruent? (Enter 'Y' or 'y' for yes): ")
        if(angles != "y" and angles != "Y"):
            Parallelogram = False
            return Parallelogram
        else:
            Parallelogram = True
        consecutiveAngles = input("Are consecutive angles supplementary (Enter 'Y' or 'y' for yes): ")
        if(consecutiveAngles != "y" and consecutiveAngles != "Y"):
            Parallelogram = False
            return Parallelogram
        else:
            Parallelogram = True
        return Parallelogram

class Rectangle(Parallelogram):
    def isRectangle(self):
        Parallelogramchecker = Parallelogram.isParallelogram(self)
        # Parallelogramchecker checks if object is parallelogram before proceeding to check if it is a rectangle
        if(Parallelogramchecker == False):
            return False, False
        else:
            angles = input("Are all 4 angles right angles? (Enter 'Y' or 'y' for yes): ")
            if(angles != 'y' and angles != "Y"):
                return False, Parallelogramchecker
            sides = input("Are opposite sides congruent? (Enter 'Y' or 'y' for yes): ")
            if(sides != 'y' and sides != 'Y'):
                return False, Parallelogramchecker
            diagonals = input("Do diagonals bisect each other and are they congruent? (Enter 'Y' or 'y' for yes): ")
            if(diagonals != 'y' and diagonals != "Y"):
                return False, Parallelogramchecker
            return True, True

class Rhombus(Parallelogram):
    def isRhombus(self):
        proceed = input("Please enter 'Y' or 'y' to proceed: ")
        while(proceed != 'Y' and proceed != 'y'):
            proceed = input("Please reenter 'Y' or 'y': ")
        perpendicular = input("Are diagonals perpendicular (Enter 'Y' or 'y' for yes): ")
        if(perpendicular != 'y' and perpendicular != "Y"):
            return False
        sides = input("Are all 4 sides congruent (Enter 'Y' or 'y' for yes): ")
        if(sides != 'y' and sides != 'Y'):
            return False
        diagonals = input("Do diagonals bisect opposite angles (Enter 'Y' or 'y' for yes): ")
        if(diagonals != 'y' and diagonals != "Y"):
            return False
        return True
print("This program will determine if a shape is a parallelogram and a rectangle")
rerun = "Y"
while(rerun == "Y" or rerun == 'y'):
    a = Rectangle()
    c = Rhombus()
    b = a.isRectangle()
    if(b[0] == True and b[1] == True):
        print("object is a rectangle")
    elif(b[1] == True and b[0] == False):
        print("object is not a rectangle but is a parallelogram")
    else:
        print("object is not a parallelogram and not a rectangle")
    if(b[0] == False and b[1] == True):
        print("Now, it will check if the parallelogram is a rhombus")
        d = c.isRhombus()
        if(d == True):
            print("object is a rhombus")
        else:
            print("object is not a rhombus")
    rerun = input("Want to run the program again? (Enter 'Y' or 'y' for yes): ")
