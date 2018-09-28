# ichw2.md
# 题1.图灵证明停机问题的原因，证明方法和背后数学原理？
## 原因
图灵在提出图灵机的概念后提出了停机问题，目的是为了讨论图灵机能否判断任意一个问题可解与否（比如判断任意丢番图方程是否有整数解）。
## 方法
图灵采用了反证法，构造了一个自我指涉的程序，调用后产生悖论，说明不能判定是否停机。
## 数学原理
自我指涉的逻辑不完备性，即**哥德尔不完备定理**---*一个自洽系统中必定存在一个命题，它既不能被证实，也不能被证伪。*  
  
  
# 题2.向中学生科普二进制补码的原理。
*（假设各位中学生小朋友已经掌握原码和反码了）*  
## 首先给大家讲一下补码的表示方法：
给定码长为N，给出一个整数 X∈【-2^(N-1),2^(n-1)-1】。  
**若X为非负**，则与原码表示相同；  
**若X为负**，则将原码求反再加1，即寻找一个数Y，使Y=2^N+X(或减X的绝对值)，Y即为所求补码。  
## 补码和钟表盘--补码加减的计数原理：
假设有一个**16刻度**的表盘，那么它可以对应一个4位码长的补码表示。  
其中15点，就是-1点，这与补码中用15表示-1道理相同。  
而补码便于运算的特点也可以从中得到解释：  
表盘上数字相加后可以循环的特点，使得补码运算时可以将符号位也纳入运算，并且只有一个0，让补码在加减运算中具有极大的优势。  
**例1**：2-3=-1  
在16刻度表盘上，2=2点，-3=13点，2点+13点=15点，即-1。  
**例2**：4-2=2  
在16刻度表盘上，4=4点，-2=14点，4点+14点=18点=2点，即2。  
  
  
# 题3.关于浮点数的几个问题。
*为方便表示，我在符号部分，指数部分，小数部分之间使用空格将其分开*  
**默认为Excess-63**  
  
± 0 = * 0000000 00000000  
1.0 = 0 0111111 00000000  
-1.0= 1 0111111 00000000  
± ∞ = * 1111111 00000000  
NaN= * 1111111 non zero  
  
*关于下题中最大最小的叙述，我理解为**绝对值**的大小，这样更有意义*  
  
最大非规范化数= * 0000000 11111111  
最小非规范化数= * 0000000 00000001  
最大规范化数 = * 1111110 11111111  
最小规范化数 = * 0000000 00000010  
