This repo is for assignment purposes File = open("HarryPotterAndTheSorcerersStone.txt", encoding ='UTF-8')

DictionaryOfWords = {}
Novel = []

i = 0

for line in File.readlines():

line = line.replace(".","").replace(",","").replace('?','').replace('!','').replace('[','').replace(']','').replace('(','').replace(')','').replace('%','').replace('//','')


for line in line.split(' '): 
                                                                         
    if line in DictionaryOfWords.keys():     
                                                                         
        DictionaryOfWords[line].extend([i])        
                                                                         
    else:
        DictionaryOfWords[line] = [i]      
                                                                         
    
    Novel.append(line)        
                                                                         
    i+=1
def GetQuery():

word = input("what word do you want to query for  ")
Number = int(input("how many results do you want to see "))

return (word, Number)
def PrintContext(index):

global Novel                          

for i in range(index-5,index+5) :          
    
    print( Novel[i] , end = ' ')          
    
print('\n')
def PrintResult(word, Number):

global DictionaryOfWords                

L = DictionaryOfWords[ word ] 

for i in range(0,min(len(L),Number)):
    
    PrintContext(i)   
Query = input("If you have any Query , Please enter Y or if you don't have any query then enter N \n Please press Enter after entering your choice! ")

if Query == "Y": GetQuery()

else: pass

while 1>0 :

Choice = input('Press Y in order to Continue with the next query or N to end. \n Please press Enter after entering your choice! ')

if Choice== "Y" :

    GetQuery()
                   
else:

    break