# Creating a Nonogram solver
# by Karen Roberts
# Graduate Poject 24 Aug 2017



### Create Class for nonogram size
class nonogramsize:
    def __init__(self, rsize, csize):
        self.rsize = rsize
        self.csize = csize

    def __str__(self):
        return str(self.rsize) + "x" + str(self.csize)

    def show(self):
        print(self.rsize, "x", self.csize)


### Get user input for the row and column sizes of the puzzle
rsize = int(input("Please enter row size: "))
csize = int(input("Please enter column size: "))

### Print the output of what the nxm puzzle size is
print("This is a", nonogramsize(rsize, csize), "Nonogram Solver")




### Create a list containing possible picture grid entries
plist = ['*', '-', 'x']
vlist = [1,0]

# Create blank puzzle and name it

# Print out the blank puzzle grid
for j in range(0, csize):
    print()
    for i in range(0, rsize):
        print(str(plist[1]), end=" ")
    i+=1
j+=1
print()
print()







#### Create row list containing hint lists for each row

## Create empty rlist for row i
rlist = []

## Create empy rblist for row i
rblist = []


for i in range(0, rsize):

    # Create loop that asks how many hints are in row i for this rsize puzzle
    rhcount = int(input("How many hints are in this row? "))

    # Create empty inner hint list for row i hint a
    rhlist = []

    # Create empty inner black hint list for row i hint a
    brehintlist = []
    
    # Create loop that asks rhcount hints for row i
    for a in range(0, rhcount):


        # Asks for user to enter hint a for row i
        erhint = int(input("Please input hint in this row:  "))



        #Change hints to binary strings
        brehint = [1]*erhint

        #Appends newly converted entry to black row entry list brehintlist
        brehintlist.append(brehint)
        print(brehintlist)

        # Appends newly entered hint a entry to rhlist for row i
        rhlist.append(erhint)


    # Appends newly appened rhlist to rlist
    rlist.append(rhlist)

    #Appends newly appended binary converted list brehinlist to brlist
    rblist.append(brehintlist)
print(rlist)
print(rblist)







#### Create column list containing hint lists for each column

## Create empty rlist for column j
clist = []

## Create empy rblist for column j
cblist = []


for j in range(0, csize):

    # Create loop that asks how many hints are in column j for this csize puzzle
    chcount = int(input("How many hints are in this column? "))

    # Create empty inner hint list for column j hint b
    chlist = []

    # Create empty inner black hint list for column j hint b
    bcehintlist = []
    
    # Create loop that asks chcount hints for column j
    for b in range(0, chcount):


        # Asks for user to enter hint a for column j
        echint = int(input("Please input hint in this column:  "))



        #Change hints to binary strings
        bcehint = [1]*echint

        #Appends newly converted entry to black column entry list bcehintlist
        bcehintlist.append(bcehint)
        print(bcehintlist)

        # Appends newly entered hint a entry to chlist for column j
        chlist.append(echint)


    # Appends newly appened chlist to clist
    clist.append(chlist)

    #Appends newly appended binary converted list bcehinlist to bclist
    cblist.append(bcehintlist)
print(clist)
print(cblist)



########################## Developer Notes ######################################

# For the 5x5 puzzle:
#
#          1 2   1 1
#          2 1 5 1 2
#     1 2  - - - - -
#     2 1  - - - - -
#       3  - - - - -
#   1 1 1  - - - - -
#     3 1  - - - - -
#
#  The solution:
#
#          1 2   1 1
#          2 1 5 1 2
#     1 2  * - * * -
#     2 1  - * * - *
#       3  - * * * -
#   1 1 1  * - * - *
#     3 1  * * * - *
#
#  What my output lists should look like
# rlist = [[1,2], [2,1], [3], [1,1,1], [3,1]]
# clist = [[1,2], [2,1], [5], [1,1], [1,2]]
# rblist = [[[1],[1,1]], [[1,1], [1]], [1,1,1], [[1], [1], [1]], [[1,1,1], [1]]]
# cblist = [[[1], [1,1]], [[1,1], [1]], [1,1,1,1,1], [[1], [1]], [[1], [1,1]]]
# vlist = ['*', '-', 'x']

# Recal Character picture grid project from grad research
# Character Picture Grid
# grid =[matrix.......]
#for j in range(0,csize):
#    print()
#    for i in range(0,rsize):
#       print(str(grid[i][j]), end=" ")
#    i+=1
#j+=1
