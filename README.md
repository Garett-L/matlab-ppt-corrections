# matlab-ppt-corrections  
要有修改的文件为：[数学建模（刘婷）-Matlab应用1-在微积分及方程中的应用.pptx](https://github.com/jalopo/matlab-ppt-corrections/files/8574828/-Matlab.1-.pptx)  
我使用的matlb版本为R2022a  
## 一、极限、导数
### 第5页
```diff
%原：
clear
syms x;
! g=sym('cos(x+sin(y(x)))=sin(y(x))');
f=diff(g,x)
```
```diff
%应改为：
clear
syms x;
+ g=str2sym('cos(x+sin(y(x)))=sin(y(x))');
f=diff(g,x)
```
## 二、积分
### 第8页 
在第8页中的`quad(fun,a,b)`  
![image](https://user-images.githubusercontent.com/104341854/165550478-b7985a57-9778-4c73-a5dc-7619f7ad108b.png)  
所以建议改成：`integral(fun,xmin,xmax)`   
### 第9页
相应的第9页的`q3=quad('sin(x)',0,1)`应改为`q3=integral(@(x)sin(x),0,1);`  
### 第10页
在第10页中的`dblquad(fun,xmin,xmax,ymin,ymax,tol,method)`和`triplequad(fun,xmin,xmax,ymin,ymax,zmin,zmax,tol)`  
![image](https://user-images.githubusercontent.com/104341854/165559790-0b8f981a-6a6a-452f-b8e6-abcf328b3578.png)![image](https://user-images.githubusercontent.com/104341854/165560008-25437144-74ad-4f5d-9941-ea2041c59a71.png)  
所以建议改成`integral2(fun,xmin,xmax,ymin,ymax)`和`integral3(fun,xmin,xmax,ymin,ymax,zmin,zmax)`  
### 第11页
相应的，第11页中的练习1：`I=dblquad(‘fxy’,-1,1,-1,1)`应改为`I = integral2(fxy,-1,1,-1,1);`  
相应的，第11页中的练习2，而且第一行的`*`应改为`.*`:
```diff
%原：
! F = @(x,y,z)y*sin(x)+z*cos(x);
! Q = triplequad(F,0,pi,0,1,-1,1);
! Q
```
```diff
%应改为：
+ F = @(x,y,z)y.*sin(x)+z.*cos(x);
+ Q = integral3(F,0,pi,0,1,-1,1);
+ disp(Q)
```
### 第12页
`sysms x y`应改为`syms x y`
## 三、方程的matlab求解
### 第14页
`solve('x^2-5*x+4',x)`应改为`solve(x^2-5*x+4,x)`

