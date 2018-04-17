# 实验3：图书管理系统领域对象建模
|学号|班级|姓名|照片|
|:-------:|:-------------: | :----------:|:---:|
|201510414408|软件(本)15-4|李玥|![flow1](../myself.jpg)|
## 1. 图书管理系统的类图

### 1.1 类图源码如下：
```
@startuml

package "library" #DDDDDD {

	class BookManager {

		+维护图书()
		+归还图书()
		+借还图书()
		+维护读者信息()
	}
	class reader {

		+查询借阅图书信息()
		+预订图书()
		+取消预订图书()
	}


	class book {
	 	-书名
	 	-ISBN号
	 	-总量
	 	-库存
	 	-价格
	 	-出版社
	 	-作者
	}

	class order {
	 	-读者姓名
	 	-图书ISBN号
	 	-借出时间
	 	-归还期限
	}

	 note "<color:white>省略Getter和Setter方法。</color>" as note1

	book .. note1
	note1 .. 借书记录
	reader "1" *-- "N" order : 借书和还书
	order "1" o-- "1" book : 一一对应
	order "N" -- "1" BookManagerr : 登记和归还
	BookManager "N" -- "N" book : 维护图书
	BookManager "N" -- "N" reader : 维护读者信息


}



@enduml
````
### 1.2 截图如下：
![系统类](https://github.com/liyue0408/is_analysis/blob/master/test3/%E7%B3%BB%E7%BB%9F%E7%B1%BB.png)

## 2. 图书管理系统对象图:
### 2.1 读者对象：
#### 源代码：

#### 截图：
