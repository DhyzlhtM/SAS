# SAS  
## 1.1 SAS 
##### SAS  程序布局
> * SAS 语句不区分大小写。  
* 一条语句可以持续到第二行（只要不把一个单词分开）。  
* 几条语句可以用一行。  
* 可以在任何一列中开始一条语句
* 每一个 SAS 语句都由一个分号结尾

##### 注释
    *Read animals’weights from file;
     DATA animals;
     INFILE’c:\MyRawData\Zoo.dat’;
     INPUT Lions Tigers;
     PROC PRINT DATA=animals; /*Print the results*/
     RUN;

> 有两种注释方法，一种是*号和；号；一种是用/* */表示，注意第二种注释方法不能放在第一列  

## 1.2 SAS数据集   
##### 变量和观测值
      SAS 数据集也被叫做表、观测值也被叫做行、变量也被叫做列
##### 数据类型  
      在 SAS 中只有两种数据类型——数值型和字符型。  
      数值型完全是数据，可以被加减乘除、可以是正负且是小数。  
      字符变量是除数值之外的类型，可以是数值、字母、和一些特殊的字符（￥、！），最多可以占用 32767个字节长度。
##### 缺失  
      字符变量的缺失值用空格表示，数值变量的缺失值用句号（.）表示。  
##### SAS 命名规则  
      为你的变量和数据集命名，使它们容易被辨别。  
      A,B,C 这样的名字可能看起来很完美，写程序的时候也很方便。  
      但当你 6 个月后再使用这些数据时，你会发现 name，height，weight 这样的名字更有用。  
      为变量和数据集命名时要遵守如下规则：
>* 名字的长度要小于等于 32 个字节。  
* 以字母或下划线开头。  
* 可以包含字母、数字、或者是下划线，不能是%$!*&#@。  
* 可以是小写或大写字母，且不区分大小写。
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
