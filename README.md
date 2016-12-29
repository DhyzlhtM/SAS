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
      * 条件语句 IF-THEN 的基本形式为：IF 条件 THEN 执行;
      * 比如：IF Model='Mustang' THEN Make='Ford';
      * 还有 IN 比较符，比如这句中 IF Model IN('Corvette','Camaro') THEN Make='Chevrolet';  
      * 代表当Model 为 Corvette 或 Camaro 的时候，将 Chevrolet 赋给 Make。
      
      * 一个条件只能有一个执行，如果要多个执行，则需要 DO 和 END 关键字。  
      * 可以用 AND 和 OR 来定义多个条件：IF Model='Mustang' AND Year<1975 THEN Status='classic';

##### 构造子集  
>* IF 语句可以构造子集，取数据集中的部分数据。  
* 基本形式为： IF expression; 比如： IF Sex='f';  
* 如果 IF 条件中的数据是真，则数据步将继续执行。  
* 还可以使用 DELETE 语句，来删除哪些不要的数据： IF expression THEN DELETE;  
* 这两句话是等价的： IF Sex='f'; IF Sex='m'THEN DELETE;

##### 使用 retain 和 sum 语句  
>* variable+expression;  
 * 语句等价于如下形式：  
 * RETAIN variable 0;  
 * variable=SUM(variable,expression);
