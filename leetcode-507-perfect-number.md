# 力扣 507完美数

## using c++

```c++
leetcode507 完美数
题目：除一以外当一个数的所有除数（除本身）的和为其本身，称为完美数。
class solution:
  def CheckPerfectNumber(self,num,int)->bool;
  if num<=1;#排除题目中条件一
  return false;
  for tmp in range(2,int(num**0.5)+1);#缩小搜索范围节约开销
  a,b=divmod(num,tmp);#in py divmod(int,int),return[int#商， int#余数]
  if b==0;#如果余数等于0，则整除，加入到运算数组中
  ans+=a+tmp;#依据题目的定义把所有的商相加
  if ans>num;#判断是不是完美数
  return false;
  return ans==num;  
```

