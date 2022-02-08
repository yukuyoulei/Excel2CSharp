使用方法：

1.导出文件夹内所有excel文件

  Excel2Code.exe -dir Excels
  
2.导出指定excel文件

  Excel2Code.exe Excels/test.xlsx Excels/test2.xlsx
  
------------------
·Sheet名称以#开头的Sheet，会被识别为基础类型集合，第一列为类型，第二列为变量名，第三列为内容，内容为 int/string/bool 时，第一列可以为空，会自己推测类型

------------------
·Sheet名称不以#开头每个Sheet中，会被识别为数据，这种Sheet第一行为注释，第二行为数据类型，第三行为变量名

数据类型支持各种基础类型，但是要保证填充的内容合法；支持各种基础类型的数组，同样需要保证填充的内容合法；支持Key和Value都为基础类型的字典，同样需要保证填充的内容合法。

------------------

·Sheet名为“单词空格单词”格式时，Sheet名被切割为“类名 变量名”。

a.当只有第四行一个数据时，这个Sheet会被识别为成员变量；

b.当有多行数据时，这个Sheet会被识别为这个类的字典，即Dictionary<第一列的类别, 类>；

c.如果第一行第一列中包含list，则被识别为列表，即List<类>。

·当Sheet名只有一个单词时，会被识别为类名，这个Sheet导出的变量名则根据内容识别为 a."m类名"/ b."d类名"/c."l类名"

------------------
Excel2CSharp/Excel2Code/bin/Debug/net5.0/Excels/目录下有目前支持的所有写法的例子，生成的C#文件在Excel2CSharp/Excel2Code/bin/Debug/net5.0/Codes/目录下
