# matlab-ppt-corrections
#文件名：数学建模（刘婷）-Matlab应用1-在微积分及方程中的应用.ppt
#我使用的matlb版本为R2022a

#1.第五页
#原：
clear
syms x;
g=sym('cos(x+sin(y(x)))=sin(y(x))')
f=diff(g,x)
#应改为：
clear
syms x;
g=str2sym('cos(x+sin(y(x)))=sin(y(x))')
f=diff(g,x)
```diff
+ this will be highlighted in green
- this will be highlighted in red
```
