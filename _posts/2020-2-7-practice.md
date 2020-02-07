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
#  最小公倍数

```
import math
a,b=map(int,input().split())
print(a*b//math.gcd(a,b))
```
# 龟兔赛跑预测
刚开始看到这个题目以为要列一个物理关系，后来想到一秒一秒去求时间反而更简单。
```
v1,v2,t,s,l=map(int,input().split())
len1=len2=m1=m2=0
while len1<l and len2<l :
  len1+=v1
  len2+=v2
  m1+=1
  m2+=1
  if len1>=l or len2>=l:
    break
  if len1-len2>=t:
    len2+=s*v2
    m2+=s
if m2*v2>m1*v1:
  print("T")
  print(l//v2)
elif m2*v2<m1*v1:
  print("R")
  print(m2)
else:
  print("D")
  print(m2)
```
#  FJ的字符串
  归纳证明和递归的本质是一样的。
 ```
  def f(n):
    if n==1:
        return   "A"
    else:
        return f(n-1)+chr(65+n-1)+f(n-1)
n=int(input())
print(f(n))
```
# 字母图形
```
n,m=input().split()
for j in range(int(n)):
        if j>int(m):
                for a in range(int(m)):
                        print(chr(65+j-a),end="")
        else:
                for k in range(j):                 
                        print(chr(65+j-k),end="")
        for i in range(int(m)-j):
            print(chr(65+i),end="")
        print("")
 ```
 
# 表达式计算
虽然eval()的速度慢并且有安全风险，但是它可以传表达式进来，某些情况下很方便。
 ```
s=input()
print(eval(s))
```
# 闰年判断
```
from datetime import datetime
s=int(input())
try:
    n=datetime(s,2,29).day
    print(1)
except:
    print(0)
```
    
