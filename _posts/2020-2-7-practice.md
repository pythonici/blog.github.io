# 审美课

```python
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

```python
import math
a,b=map(int,input().split())
print(a*b//math.gcd(a,b))
```
# 龟兔赛跑预测
刚开始看到这个题目以为要列一个物理关系，后来想到一秒一秒去求时间反而更简单。
```python
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
 ```python
  def f(n):
    if n==1:
        return   "A"
    else:
        return f(n-1)+chr(65+n-1)+f(n-1)
n=int(input())
print(f(n))
```
# 字母图形
```python
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
 ```python
s=input()
print(eval(s))
```
# 闰年判断
```python
from datetime import datetime
s=int(input())
try:
    n=datetime(s,2,29).day
    print(1)
except:
    print(0)
```
# 打开文件
二进制格式打开文件，文件编码格式检测，指定编码格式写入。
```python
import chardet
with open("三国演义.txt","rb+") as f:
    print(chardet.detect(f.readline()))
    f.seek(-1,2)
    f.write('hello'.encode('utf-8'))
```
# 一元一次方程的解
```python
n=''
a,b=input().split("=")
if '+' in a or '-'in a:
    m=a.split('+')
    for i in m:
        if '-' in i:
            b=b+'-'+'('+i+')'
        else:
            b = b + '-' + i
for i in b:
    if i.isalpha():
        y=i
        n=n+'j'
    else:
        n=n+i
n=eval(n)
print("%c=%.3f"%(y,-n.real/n.imag))
```
# CF6A Triangle
```python
flag=100
n=list(map(int,input().split()))
x=[None]*10
pd=[None]*10
def dfs(dee):
    global  flag
    if dee==4:
        if x[1]+x[2]>x[3] and x[1]+x[3]>x[2] and x[2]+x[3]>x[1]:
            print("TRIANGLE")
            exit(0)
        if x[1]+x[2]>=x[3] and x[1]+x[3]>=x[2] and x[2]+x[3]>=x[1]:
            flag=0
        return flag
    for i in range(1,5):
        if not pd[i]:
            pd[i]=1
            x[dee]=n[i-1]
            dfs(dee+1)
            pd[i]=0
    return flag
dfs(1)
if flag==0:
    print("SEGMENT")
else:
    print("IMPOSSIBLE")
```
# 填涂颜色
```python
x=[0,0,1,-1]
y=[1,-1,0,0]
n=int(input())
A=[[None]*n for i in range(n)]
for i in range(n):
    s=input().split()
    for j in range(n):
        A[i][j]=s[j]
B=[[None]*n for i in range(n)]
for i in range(n):
    for j in range(n):
        B[i][j]=A[i][j]

def dfs(i,j):
    A[i][j]='1'
    for z in range(4):
        i+=x[z]
        j+=y[z]
        if i>=0 and i<n and j>=0 and j<n and A[i][j]!='1':
            dfs(i,j)
        i-=x[z]
        j-=y[z]
for i in range(n):
    if A[0][i]=='0':
        dfs(0,i)
    if A[n-1][i]=='0':
        dfs(n-1,i)
    if A[i][0]=='0':
        dfs(i,0)
    if A[i][n-1]=='0':
        dfs(i,n-1)
for i in range(n):
    for j in range(n):
        if A[i][j]=='0':
            A[i][j]='2'

for i in range(n):
    for j in range(n):
        if A[i][j]=='1' and B[i][j]=='0':
            A[i][j]='0'
        print(A[i][j],end=" ")
    print()
```
# 数楼梯
```python
n=int(input())
m=[]
if n==0:
    n=2
    print(0)
elif n==1:
    n=2
    print(1)
m=list(range(n))
m[0]=1
m[1]=2

for i in range(2,n):
    m[i]=m[i-1]+m[i-2]
if n==2:
    pass
else:
    print(m[n-1])
```
# 拼数
```python
n=int(input())
s=map(int,input().split())
s=sorted(s,reverse=True)
p=""
for i in range(n-1):
 for j in range(i+1,n):

    a=str(s[i])
    b=str(s[j])
    if int(a+b)<int(b+a):
        s[i],s[j]=s[j],s[i]
for i in s:
    p+=str(i)
print(int(p))
```
# 纪念品分组
```python
w=int(input())
n=int(input())
x=[]
ans=0
for i in range(3,n+3):
    s=input()
    x.append(s)
x=list(map(int,x))
x=sorted(x)
p=-1
k=n
for i in range(n+1):
     if  p>=n-1:
         break
     if  x[p+1]+x[n-1]<=w:
         ans+=1
         n-=1
         p+=1

     else:
        n-=1
        ans+=1
print(ans)
```
# 均分纸牌
```python
n=int(input())
f=input().split()
m=[]
for i in f:
    m.append(int(i))
mean=sum(m)//n
ans=0
for i in range(n-1):
    if m[i]<mean:
        m[i+1]=m[i+1]-(mean-m[i])
        ans+=1
    elif m[i]>mean:
        m[i+1]=m[i]-mean+m[i+1]
        ans+=1
print(ans)
```
# 分数线划定
```python
n,m=map(int,input().split())
z=[]
for i in range(n):
    k,s=map(int,input().split())
    z.append((k,s))
z.sort(key=lambda x:x[1],reverse=True)
count=0
for i in z:
    if i[1]>=z[int(m*1.5-1)][1]:
         count+=1
print(z[int(m*1.5-1)][1],count)

x,y=zip(*z)
x=list(x)
y=list(y)
for i in range(count):
    if y[i]==y[i+1] and x[i] >x[i+1] :
         x[i],x[i+1]=x[i+1],x[i]
         print(x[i],y[i])
    else:
        print(x[i],y[i])
```
# 贪心
选择最早结束的课，然后选择这一节课结束后开始的课，重复这两个步骤。
```python
b=-1
ans=0
m=[]
n=int(input())
for i in range(n):
    x,y=map(int,input().split())
    m.append((x,y))
m.sort(key=lambda x:x[1])
for i in m:
    x,y=i[0],i[1]
    if b<=x :
        b=y
        ans+=1
print(ans)
```
