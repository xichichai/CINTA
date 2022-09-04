#CINTA第一次作业

1.用 *C* 语言编程实现判断输入为偶数的函数，即如果输入为偶数，返回 *T rue*，否则返回 *F alse*。

//FileName:odd_or_even.c

include<stdio.h>

#define True   1

#define False   0

***\*int\**** ood_or_even(***\*int\****);

***\*int\**** main()

{

  ***\*int\**** a;

  scanf("%d",&a);

  ***\*if\****(ood_or_even(a)==True)

​    printf("odd");

  ***\*else\****

​    printf("even");

}

***\*int\**** ood_or_even(***\*int\**** a)

{

  ***\*if\****((a&1)!=0)

​    ***\*return\**** True;

  ***\*else\****

​    ***\*return\**** False;

}

---



2.用 *C* 语言编程实现一种迭代版本的简单乘法。

//FileName:multiplication.c

#include<stdio.h>

***\*int\**** main()

{

  ***\*int\**** a,b;

  ***\*int\**** sum=0;

  scanf("%d %d",&a,&b);

  ***\*while\****(b!=0)

  {

​    ***\*if\****((b&1)!=0)

​    {

​      sum+=a;

​      a=a<<1;

​      b=b>>1;

​    }

​    ***\*else\****

​    {

​      a=a<<1;

​      b=b>>1;

​    }

  }

  printf("%d",sum);  

}

---



3. 证明命题1.1

   证明存在性：

   ​	构造集合S = {a − bk : k ∈ Z 且 a − bk ≥ 0}.
   ​	显然，集合 S 非空。由良序原则，存在一个最小元 r ∈ S，且 r = a − qb。	因此，
   ​	a = qb + r, r ≥ 0。

   ​	设r>=b,则r=b+n(n∈Z)。

   ​	则a=qb+r=qb+b+m=(q+1)b+m,与商和余数原则不符。

   证明唯一性：

   ​	假设存在多个整数符合条件

   ​	则有a=q<sub>1</sub>b+r<sub>1</sub>,a=q<sub>2</sub>b+r<sub>2</sub>(q<sub>i</sub> ≥ 0,i ∈ Z)(b>r<sub>i</sub>≥ 0,i ∈ Z)

   ​	设q<sub>1</sub>>q<sub>2</sub>,从而r<sub>1</sub><r<sub>2</sub>
   $$
   b=\frac{r2-r1}{q1-q2}①
   $$
   ​	q<sub>1</sub>-q<sub>2</sub>≥ 1	b>r<sub>2</sub>-r<sub>1</sub>>0
   $$
   所以\frac{r2-r1}{q1-q2}<b ②
   $$
   ​	

   ​	式①②相互矛盾

   ​	所以假设不成立，唯一性得证

   ---

   ##附加题

   1. 给定一个整数 *v*，如何判断 *v* 是否 2 的某次方？比如，*v* = 4 = x^2^，返回 *T rue*； *v* = 9 = 2^3^ +1 并非 2 的次方，返回 *F alse*。请写一个 *C* 语言的函数来实现以上功能。

      法1:位置计数

      //FileName:position.c

      \#define False 0

      \#define True 1

      \#include<stdio.h>

      **int** binary(**int** b)

      {

        **int** num=0;

        **if**(b<=0)

      ​    **return** False;

        **else**

      ​    **while**(b!=0)

      ​    {

      ​      **if**(num>1)

      ​        **break**;

      ​      **else** **if**((b&1)==0)

      ​      {

      ​        b=b>>1;

      ​      }

      ​      **else**

      ​      {

      ​        num++;

      ​        b=b>>1;

      ​      }

      ​    }

        **if**(num==1)

      ​    **return** True;

        **else**

      ​    **return** False;

      }

      法2:更简便

      \#define False 0

      \#define True 1

      \#include<stdio.h>

      **int** binary(**int** b)

      {

        **int** num=b&(b-1);

        **if**(num==0)

      ​    **return** True;

        **else**

      ​    **return** False;

      }

      ---

      2.证明任意形如 111 *· · ·* 111的整数都不是平方数，*n >* 2。

      证明1：(失败，原因：没有探究平方数的普遍规律)

      ​	111...111=(10^n^-1)/9

      ​	设111...111=(10^n^-1)/9=m^2^(m ∈ Z，n>2)
      
      ​	所以10^n^-1=(3m)^2^，，，证明无法进行下去
      
      证明2:
      
      ​	任意自然数都可以用2k+1表示奇数，2k表示偶数（k ∈ N）
      
      ​	(2k+1)^2^=4k^2^+4K+1,(2k)^2^=4k^2^
      
      ​	从而推出，任意一个数的平方被4除必然余0或1
      
      ​	为了方便判定是否能被4整除，我们将111...111拆分为111...100+11
      
      ​	显然得出，111...111被4除的余数总等于3（1的数量大于2）
      
      ​	因此，任意形如111...111的整数都不是平方数
      
      ​	
      
      ​	
      
      ​	