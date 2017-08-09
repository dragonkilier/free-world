## free-world
#study git,now i send the assignment1 task6.py 
def findmaxposition(alist):
    n=len(alist);
    maxposition=0;
    for i in range(0,n,1):
        if alist[i]>alist[maxposition]:
            maxposition=i;
    return maxposition

def findrepeat(alist,num):
    n=len(alist);
    c=0
    for i in range(0,n,1):
        if alist[i]==num:
            c=1;
            break
    return   c  
        






#temppretue:26, 19, 22, 21, 13, 22, 18, 22, 20, 27, 18, 24, 15, 28, 26, 27, 20, 20, 23, 24, 27, 26, 15, 23, 22, 20, 23, 17, 18, 18
import random
the_list=[];
alist=[];
days=int(input("enter the number of days:"));
i=0; 
while i<days:
    t=int(input("enter the next day:"));
    the_list.append(t);
    i=i+1;
#sort the list from max to min
for i in range(0,days,1):
    maxposition= findmaxposition(the_list[i:days])+i;
    temp=the_list[i];
    the_list[i]=the_list[maxposition];
    the_list[maxposition]=temp;
#display the list after sorted
print("Excluding the repeated numbers, the list is:");
for i in range(0,days,1):
    a=the_list[i];
    if len(alist)==0:
        alist.append(a)
    else:
        if findrepeat(alist,a)==0:
            alist.append(a);
for i in range(0,len(alist),1):
    print(alist[i]);
