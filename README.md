# Noor-and-her-pond_hackerearth
Noor is going fish farming. There are N types of fish. Each type of fish has size(S) and eating factor(E). A fish with eating factor of E, will eat all the fish of size

.

Help Noor to select a set of fish such that the size of the set is maximized as well as they do not eat each other.
Input

The first line contains T, the number of test cases. The first line of a test case contains an integers N. N is the number of types of fish. Each of the next N lines contains two integers S and E meaning the size and eating factor of a fish.
Output

For each test cases, print a single integer, the maximum number of fish Noor can have in his pond. 
1
3
4 1
5 4
7 3
Sample o/p
2
T = int(input())
for i in range(T):
    N = int(input())
    S = []
    E = []
    pond = []
    for i,j in zip(range(N),range(N)):
        i,j = map(str,input().split())
        S.append(int(i))
        E.append(int(j))
    for i,j in zip(S,E):
        if i>j:
            pond.append(i)
            S.remove(i)
            pond.append(j)
            E.remove(j)
    for i,j in zip(range(len(S)),range(len(pond))):
        lst = pond[1::2]
        if len(S) and S[i]>lst[j]:
            pond.append(S[i])
            S.remove(S[i])
            pond.append(E[i])
            E.remove(E[i])
    tot = round(len(pond)/2)
    print(tot)
    print(pond)
