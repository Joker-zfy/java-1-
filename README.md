# java-1-
java的深入学习第一阶段。
day2
#1
java常用类
System类
示例：
package com.tiaoshi;.exit();.out();等
public class Tiaoshi {
    public static void main(String[] args) {

        //System.out.println("开始");
        //System.exit(0);//没有异常情况下强制退出java虚拟机
        //System.out.println("结束");
        long start=System.currentTimeMillis(); 计时
        for (int i=0;i<=1000;i++){
            System.out.println(i);
        }
            long end=System.currentTimeMillis();
            long time=end-start;
            System.out.println(time);

    }
}
Date类
示例：
        Date start=new Date();
        long sstart=start.getTime();
        //需要测试代码运行时间的代码段
        Date end=new Date();
        long send=end.getTime();
        System.out.println(send-sstart);
Dateformat类：提供日期的格式化显示
Math类
Math类的方法都是静态方法，直接由类名调用
示例：
 int r1=Math.abs(a);
 double r2=Math.sqrt(16);
 int r3=Math.max(44,34);
 double r4=Math.round(15.6);//四舍五入
 double r5=Math.random();
 
double c1=17.2;
double c2=3;
DecimalFormat df=new DecimalFormat("0.00");
String ss=df.format(c1/c2);
System.out.println(r4);
