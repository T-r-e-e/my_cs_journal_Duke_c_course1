写在最前面：作者初涉次道 此篇仅为作者在学习计算机时一些个人心得的理解 用于日后的复习巩固 如果有任何错误 欢迎且感激您的指出

正式写代码前的步骤：自己做-把想的步骤写下来-归纳-测试


& 变量 类比数学中的x

1.声明 说清楚变量的类型与名字 
       与数学的类比：变量是叫x 还是y 还是α 或者其它，这个变量实际是长度 面积 还是其它。

2.分配

· 分配 运算符 赋值 等可以理解为计算/数学操作

& 函数 英文function 即功效 指具有功效的能做事的东西 函数的使用方法分为调用已有函数和定义函数两种。

例如 printf 功能为将所需要的东西打印在屏幕

声明函数方法如下

例 int myfunction （intx，inty）｛              这里int为函数返回/输出的数据类型 myfuction为名称
        …                                     int x和int y 是这个函数所需的参数 
        return    ；                          return后的数据是答案 它将返回调用这个函数的东西的位置
        ｝

& 条件语句

if/else  if(   ){                        作用 如果达成（）内条件 则执行｛｝内任务
                                             如果没有达成（）内条件 则执行｛｝内任务
                                             此条件语句还可以将else 写为else if 增加多种可能性
                                   }
               else｛

                                   ｝

2. switch  switch(   ){                   作用 （）内结果是case@ 那么就找到case@：
                                               然后执行：后面的任务 直到break；完成switch

                  case    ：
                  
                  break;                               break是结束的标志 如果没有break 
                                                          会继续执行下一条case 直至结束

                                     }
& 循环
1. while 循环 

while(){                                                  作用 当达成（）内条件时 执行｛｝内任务 
                                                              通常会在循环前面计数 在｛｝内最后一步让计数               
                                                              加一 （）内通常为计数次数的限制


}

2.do-while循环                                           先做｛｝内任务 如果达成（）内条件
                                                                则再执行 与while相似 区别在会保证做一次任务

do{


}while();

3.for循环
for(  ;  ;  ){                                                     与while相似 （ ；；）内通常为
                                                               （计数初始；条件；计数加一）


}

//这里一开始将for写出来if，不用IDE的后果竟是如此严重☹️ 请不要效仿！！！


& 二进制与十六进制

& 基本数据类型
char 字符   int 整数   float 浮点数/小数    double 浮点数/小数 比float位数更多

· 图像 声音 等看似非数字的表达其实也是用数字表达 cs50和crash course中皆有涉及

& 结构体与定义类型

1.结构体 即把一些相关数据装进一个盒子里 这样比较清晰（就像整理桌面）

struct rect_t{                                           左例为 定义了一个名为rect_t的类型
int left；                                                 其内容为四个int 
int top；                                                 又声明了一个叫myrect的rect_t类型变量
int bottom；
int right；
 }；

int main（）
{ struct rect_t myrect；
…

2.如上所述 rect_t里包含了四个int，就像一个叫rect_t的大盒子里撞了四个名为int的小盒子，rect_t和int都是类型名称 区别在于 int是“官方”的，而rect_t是自己定义的

· typedef 这个东西就是用于给一个东西重命名且保留原名/取绰号 以下为三种用法

a.
struct rect_tag{
int left；
int bottom；
int right；
int top；
}；
typedef struct rect_tag rect_t；
int main（）
{
 rect_t myrect；
…

b.
typedef struct rect_tag{
int left；
int bottom；
int right；
int top；
} rect_t；

int main（）
{
 rect_t myrect；
…


c.
typedef struct{
int left；
int bottom；
int right；
int top；
} rect_t；

int main（）
{
 rect_t myrect； 
 myrect.left=1                            //这里指类型为rect_t的变量myrect里 int left = 1
…


& 枚举
枚举就是把0123…这些数字赋予一个有意义的名字 让这些有意义的名字有一个数学意义上的数值 ，因此这些名字也可以进行数学互动 如比大小 计算

enum threat_level_t{
Low，
Guarded，
Elevated，
High，
Severe
}；
