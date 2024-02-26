# switch语句

C语言提供`switch`语句可直接处理多分支选择结构。`switch语句`的作用是根据表达式的值，使流程跳转到不同的语句，`switch`语句的一般形式如下：

```
switch(表达式){   case   常量1: 语句1  case   常量2: 语句2  …  case   常量n: 语句n  default:  语句n+1}
```

注意：

1. `switch`后面花括号内的表达式，其值的类型应为整数类型（包括字符类型）。
2. `switch`下面的花括号内是一个复合语句。这个复合语句包括若干语句，它是`switch`语句的语句体。语句体包含多个以`case`开头的语句行和一个以`default`开头的行。
3. `case`后面跟一个常量或常量表达式，`case 常量表达式:`只相当于一个语句标号。
4. 执行`switch`语句时，先计算`switch`后面表达式的值，然后将它与各个`case`比较，如果与某一个`case`标号中的常量相同，流程就转到此`case`标号后面的语句。如果没有与`switch`表达式相匹配的`case`常量，流程转去执行`default`标号后面的语句，也可以没有`default`标号。
5. 在`case`后的各常量表达式的值不能相同，否则会出现编译错误。
6. 执行一个`case`子句后，应当用`break`语句使流程跳出`switch`语句。

举例，如果按照A等为`80`分以上，B等为`70~79`分，C等为`60~69`分，D等为`60`分以下划分，用`switch`语句来实现，示例代码：

```
  int score;   scanf("%d",& score);  switch(score/10)  {     case 10:     case 9:     case 8: printf("A\n");break;    case 7: printf("B\n");break;     case 6: printf("C\n");break;    default: printf("D\n");  }
```

程序分析：

1. 定义`score`为`int`型变量，表达式`score/10`为整型，输入`85`，则表达式`score/10`的值为`8`，进`case 8`分支，执行输出语句“`A`”，遇到`break`，跳出`switch`结构。
2. 如果希望将`score`定义成`float`型变量，可以存放浮点数，表达式`score/10`为实型，编译不能通过，因为系统要求`switch`后的表达式为整型，此时可以利用强制类型转换`(int)score/10`将转换为整型。