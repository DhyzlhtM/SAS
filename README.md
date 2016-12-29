#### SAS
##### SAS  程序布局
> * SAS 语句不区分大小写。  
* 一条语句可以持续到第二行（只要不把一个单词分开）。  
* 几条语句可以用一行。  
* 可以在任何一列中开始一条语句

##### 注释
    *Read animals’weights from file;
     DATA animals;
     INFILE’c:\MyRawData\Zoo.dat’;
     INPUT Lions Tigers;
     PROC PRINT DATA=animals; /*Print the results*/
     RUN;

> 有两种注释方法，一种是*号和；号；一种是用/* */表示，注意第二种注释方法不能放在第一列

##### 使用 IF-THEN  
      条件语句 IF-THEN 的基本形式为：IF 条件 THEN 执行;
      比如：IF Model='Mustang' THEN Make='Ford';
      还有 IN 比较符，比如这句中 IF Model IN('Corvette','Camaro') THEN Make='Chevrolet';  
      代表当Model 为 Corvette 或 Camaro 的时候，将 Chevrolet 赋给 Make。
