---
title: javase_day05
date: 2019-08-06 19:10:32
tags:
---
# 循环结构、一维数组

2019/8/1 14:03:13

-----

## 循环结构

### 双重循环（难点、重点）
	（1）语法格式
		for(初始化表达式1；条件表达式2；修改初始值表达式3){
			for(初始化表达式4；条件表达式5；修改初始值表达式6){
				循环体
			}
		}
		
	（2）执行流程
		执行表达式1=>判断表达式2是否成立
			=>若成立，则执行表达式4=>判断表达式5是否成立
					=>若成立，则执行循环体=>执行表达式6=>判断表达式5是否成立
					=>若不成立，则内层循环结束=>表达式3=>判断表达式2是否成立
			=>若不成立，则外层循环结束
			
	（3）注意事项
		a.外层循环变量变一下，内层循环从头到尾跑一圈
		b.当需要打印多行多列时，则需要使用双重for循环；
		
### break关键字
	在嵌套的循环结构中，break用于退出所在循环体
	如果要退出外层循环体，需要使用标号的方式
		for(...){						outer:for(...){
			for(...){							for(...){
				break;							break outer;		
			}									}
		}								}
		
### while循环（会用）
	（1）语法格式
		while（条件表达式）{
			循环体；
		}
	（2）执行流程
		判断条件表达式是否成立
			=>若成立，则执行循环体=>判断条件表达式是否成立
			=>若不成立，则结束循环
			
	（3）注意事项
		a.while循环和for循环都属于当型循环，完全可以互换；
		b.while循环更善于明确循环条件但不明确循环次数的场合；
		  for循环通常更善于明确循环次数/循环范围的场合中；
		c.while(true)和for(;;)都表示无限循环；
		

## 一维数组（重点）

### 基本概念
	当需要在程序中记录单个数据内容时，则声明一个变量即可；
	当需要在程序中记录多个类型相同的数据内容时，则声明一个一维数组即可
	而一维数组本质上就是在内存中申请一段连续的存储单元；
	
### 声明方式
	（1）语法格式
		数据类型[] 数组名 =new 数据类型 [数组的长度]
	如：
		int[] arr= new int[3];	- 表示声明一个长度为3元素类型为int类型的一维数组
		int num =3;				- 表示声明一个初始值为3元素类型为int类型的变量
		int arr[] = new int[3]	- 不推荐使用
	 
	（2）元素初始化
		数据类型[] 数组名={初始值1, 初始值2, ...};
		如：
			int[] arr = {11, 22, 33, 44, 55}; - 声明数组的同时指定元素的初始值
			

### 练习
	（1）提示用户输入一个正整数n，使用while循环实现1/1 + 1/2 + ...+1/n
	（2）使用双重for循环分别打印以下图案：
       *****     *    i=1时，1个*   ***** i=1时，5个*                  *
       *****     **   i=2时，2个*   ****  i=2时，4个*                 ***
       *****     ***  i=3时，3个*   ***   i=3时，3个*                *****
       *****     **** i=4时，4个*   **    i=4时，2个*               *******
       *****     *****i=5时，5个*   *     i=5时，1个*              *********
    

## 作业
	1.	重点掌握数组的声明和初始化方式
	2.	编程实现九九乘法表的打印(参考PPT)
	3.	声明一个长度为5元素类型为int类型的一维数组，打印数组中的所有元素值；
     	使用元素11、22、33、44分别对数组中的前四个元素赋值，再打印所有元素值；
     	将元素55插入到下标为0的位置，原有元素向后移动，再打印所有元素值；
     	再将元素55从数组中删除，删除方式为后续元素向前移动，最后位置置为0并打印；
     	查找数组中是否存在元素22，若存在则修改为220后再次打印所有元素；
    4.	声明一个初始值为11 22 33 44 55的一维数组并打印所有元素
    	声明一个长度为3元素类型为int类型的一维数组并打印所有元素
    	实现将第一个数组中间3个元素赋值到第二个数组中
    	再次打印第二个数组中的所有元素
    5.	编程统计用户输入任意一个正整数中每个数字出现次数的统计并打印。
    	如：123123  => 1出现2次，2出现2次，3出现2次
    6.	编程实现双色球抽奖游戏(参考PPT)。  