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

Random类
使用Random类必须先创建对象，如
Random ran=new Random();
int r1=ran.nextInt(100);//0-100之间的数

BigInteger类：表示大整数（超过了long类型能表示的值）类，用于封装大整数类的数学运算
BigInteger big1=new BigInteger("2222222222");
BigInteger big2=new BigInteger("6666666666");
//加减乘除、取模
System.out.println(big1.add(big2));
System.out.println(big1.subtract(big2));
System.out.println(big1.multiply(big2));
System.out.println(big1.divide(big2));
System.out.println(big1.remainer(big2));

BigDecimal类：表示超大 小数类，用于小数类的精确数学运算
BigDecimal bigd1=new BigDecimal("3.23422");
BigDecimal bigd2=new BigDecimal("2.414");
//其他与上面类似
//除不尽会报错，System.out.println(bigd1.divide(bigd2,4,BigDecimal.ROUND_HALF_UP));来解决

补充：对象克隆技术（不能简单赋值时）

Timer类是一种线程设施，可以用来实现某一个时间或者某一段时间后安排一个任务的执行，Timer类需要与TimerTast类配合使用。
三种应用示例：
package com.time;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Timer;
import java.util.TimerTask;

public class Test1 {
    public static void main(String[] args) throws ParseException {

        Timer ti = new Timer();//控制定时任务的执行方式

        TimerTask task = new TimerTask() { //定义定时任务的执行
            @Override
            public void run() {
                System.out.println("定时任务被执行");
            }
        };
        //一段时间后执行
        //ti.schedule(task, 3000);//单位是毫秒，3000即3秒

        //固定时间点执行
        //ti.schedule(task,new SimpleDateFormat("yyyy/MM/dd HH:mm:ss").parse("2020/04/05 11:00:00"));

        //重复执行任务
        ti.schedule(task,2000,1000);//2秒后开始执行，每秒执行一次

    }
}

