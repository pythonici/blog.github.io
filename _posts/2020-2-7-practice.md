# 审美课

```
h,w=map(int,input().split())
A=[[None]*w for i in range(h)]
count=0
flag=0
for i in range(h):
    s=input().split()
    for j in range(w):
        A[i][j]=int(s[j])
for i in range(h):
    for k in range(i+1,h):    
        for j in range(w):     
           if A[i][j]+A[k][j]==1
              flag+=1
           else:
                break
        if flag==w:
            count+=1
        flag=0
print(count)
```
