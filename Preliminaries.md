# Preliminaries

$\usepackage{mathrsfs}$

### Fineite Field

#### 	Definition of Finite Field

![image-20230709182137607](C:\Users\75179\AppData\Roaming\Typora\typora-user-images\image-20230709182137607.png)

**NOTE:** 

1. ​	有限域涉及两种运算(+,*)

2. 图中$$0_F$$和$$1_F$$都是单位元，0是加法的单位元，1是乘法的单位元。

3. 加法和乘法上都有逆元，加法一定有逆元，但是在某些域上，不是所有的乘法运算都有逆元

4. $ {\forall}u\in\mathbb{F}, $ ${\forall}v\in\mathbb{F}$,减法可以用加法表述：
   $$
   u - v = u + (-v)
   $$

5. $ {\forall}u\in\mathbb{F}, $ ${\forall}v\in\mathbb{F}$,除法可以用乘法表述:
   $$
   u/v=u*v^{-1}
   $$

#### 	Definition  Explantions

此处分为两种有限域：$(\mathbb{F}_{q^{n}},+,*)$ , $(\mathbb{F}_{q},+,*)$ 

![image-20230709185350861](C:\Users\75179\AppData\Roaming\Typora\typora-user-images\image-20230709185350861.png)

![image-20230709185618527](C:\Users\75179\AppData\Roaming\Typora\typora-user-images\image-20230709185618527.png)

### Cyclic Groups

#### Definition of Cyclic Groups

​	群区别于域，主要是由一种运算构成的，也就是乘法或者加法二选一。群主要分为三种类型，Abelian Group, Abelian Group with Cyclic, Abelian Group with Cyclic of Prime Order.群的名称看上去是在套娃，一层一层的升级。一般在方案中，$\mathbb{G}$表示群的空间，$g$ 表示生成元， $p$表示群的阶。接下分别展示群的定义：

![image-20230709190357289](C:\Users\75179\AppData\Roaming\Typora\typora-user-images\image-20230709190357289.png)

![image-20230709190624683](C:\Users\75179\AppData\Roaming\Typora\typora-user-images\image-20230709190624683.png)

<div align = "center">Abelian Group with Cyclic of Prime Order</div>

![image-20230709190956125](C:\Users\75179\AppData\Roaming\Typora\typora-user-images\image-20230709190956125.png)

#### Computing Problems Over Group

**上面讲解群的基本定义，那么我们为什么要用群呢？** 

在加密过程需要一定的算力，当计算的复杂度超过了计算机能达到的极限，则在计算上敌手是无法攻破，敌手就无法获取到任何信息。离散对数问题在一些群上计算是简单的，而在特殊的群下，没有非常高效的方法就计算它们。因此，在一些特殊的群中解决DL问题是困难的。 下面是对离散对数进行定义：

![image-20230709193436496](C:\Users\75179\AppData\Roaming\Typora\typora-user-images\image-20230709193436496.png)

#### Group Chooses

![image-20230709193706426](C:\Users\75179\AppData\Roaming\Typora\typora-user-images\image-20230709193706426.png)

![image-20230709193754130](C:\Users\75179\AppData\Roaming\Typora\typora-user-images\image-20230709193754130.png)

### Pairing 

双线性配对是把两个不同群的元素映射进一个乘法群，主要分为两种双线性配对，一种是对称的双线性配对，另外一种是非对称的双线性配对。

<div align = "center">Symmeetric Pairing</div>

![image-20230709194106315](C:\Users\75179\AppData\Roaming\Typora\typora-user-images\image-20230709194106315.png)

<div align = "center">Asymmeetric Pairing</div>

![image-20230709194258001](C:\Users\75179\AppData\Roaming\Typora\typora-user-images\image-20230709194258001.png)

### Hash Function

哈希函数将任意长度的字符串作为输入，并返回一个固定长的字符串作为输出。注意：大多数公钥密码方案都需要哈希函数。Hash函数分为两类： 一次哈希函数和不可碰撞哈希函数。定义如下：
		

![image-20230709194551394](C:\Users\75179\AppData\Roaming\Typora\typora-user-images\image-20230709194551394.png)

在密码方案中，会构造多个hash函数情况，是因为输出的内容不一致，下面有三种hash表示形式：

![image-20230709194818923](C:\Users\75179\AppData\Roaming\Typora\typora-user-images\image-20230709194818923.png)

### Insecure Scheme

- [ ] $pk=(g,g^{a}),sk=a\in\mathbb{Z_{p}},\sigma_{m}=g^{a*m}$,当给出$(pk,m,\sigma_{m})$伪造前面$sigma_{m}$

A chooes a random number $t$, computes $pk=g^{at}, \sigma_{m}=g^{atm}$, then sends $(pk,m,\sigma_{m})$

- [ ] $pk=(g,g^{a}),sk=a\in\mathbb{Z_{p}},\sigma_{m}=g^{a+m}$,当给出$(pk,m,\sigma_{m})$伪造前面$sigma_{m}$

A chooes a random number $t$, computes $pk=g^{at}, \sigma_{m}=g^{at+m}$, then sends $(pk,m,\sigma_{m})$

- [ ] $pk=(g,g^{a},g^{b}),sk=(a,b)\in\mathbb{Z_{p}},\sigma_{m}=a+mb\mod q$,当给出$(pk,m,\sigma_{m})$伪造前面$sigma_{m}$

- [ ] $pk=(g,g^{a},g^{b}),sk=(a,b)\in\mathbb{Z_{p}},\sigma_{m}=(g^{ab+mr},g^{r})$,当给出$(pk,m,\sigma_{m})$伪造前面$sigma_{m}$
- [ ] $pk=(g,g^{a},g^{b}),sk=(a,b)\in\mathbb{Z_{p}},\sigma_{m}=(g^{ab+mr*b},g^{r})$,当给出$(pk,m,\sigma_{m})$伪造前面$sigma_{m}$

