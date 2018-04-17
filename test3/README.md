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
##### 2.1：借书记录
##### uml源码如下
````
@startuml

object order {
	 	读者姓名 = "李玥"
	 	图书ISBN号 = "11-33-55"
	 	借出时间 = "2017-5-3"
	 	归还期限 = "2018-6-10"
}


@endumlml

````
![借书记录](https://github.com/liyue0408/is_analysis/blob/master/test3/%E5%80%9F%E4%B9%A6%E8%AE%B0%E5%BD%95.PNG)


2.2：图书对象
````
@startuml

	object book {
    	 	书名 = "Python与机器学习实战"
    	 	ISBN号 = "156-211-003-231"
    	 	总量 = "30"
    	 	库存 = "25"
    	 	价格 = "69"
    	 	出版社 = "电子工业出版社"
    	 	简介 = "决策树，继集成学习，支持向量机"
    	 	作者 = "何宇健"
    	}

@endumll
````
![图书对象](https://github.com/liyue0408/is_analysis/blob/master/test3/%E5%9B%BE%E4%B9%A6%E5%AF%B9%E8%B1%A1.PNG)




##### 2.3：管理员对象

````
@startuml

object BookManager {
		 username = "liyue"
		 password = "liyue123"
}


@enduml
````
![管理员对象](https://github.com/liyue0408/is_analysis/blob/master/test3/%E7%AE%A1%E7%90%86%E5%91%98%E5%AF%B9%E8%B1%A1.png)



##### 2.4：系统对象

````
@startuml



package "library" #DDDDDD {

	object BookManager {
    		 username = "liyue"
    		 password = "liyue123"
    }



	object reader {
    	 	username = "liyue"
    		password = "liyue123
    	}


	object book {
    	 	书名 = "Python与机器学习实战"
    	 	ISBN号 = "156-211-003-231"
    	 	总量 = "30"
    	 	库存 = "25"
    	 	价格 = "69"
    	 	出版社 = "电子工业出版社"
    	 	简介 = "决策树，继集成学习，支持向量机"
    	 	作者 = "何宇健"
    	}

	object order {
    	 	读者姓名 = "李玥"
    	 	图书ISBN号 = "11-33-55"
    	 	借出时间 = "2017-5-3"
    	 	归还期限 = "2018-6-10"
    }
    object return {
            读者姓名 = "李玥"
            图书ISBN号 = "22-32-19"
            还书日期 = "2018-4-3"


    }

	note "<color:blue>省略Getter和Setter方法。</color>" as note1

	book .. note1
	note1 .. 借书记录


	BookManager <|-- return: 管理信息
	reader "1" *-- "N" order : 借书和还书
	return "1" *-- "N" order : 还书
	order "1" o-- "1" book : 一一对应
	借书记录 "N" -- "1"  数据库: 登记和归还
	BookManager "N" -- "N" book : 维护图书
	BookManager "N" -- "N" reader : 维护读者信息


}


@enduml
````

![系统对象](https://github.com/liyue0408/is_analysis/blob/master/test3/%E7%B3%BB%E7%BB%9F%E5%AF%B9%E8%B1%A1.png)




##### 2.5：读者对象

````
@startuml
	object reader {
    	 	username = "liyue"
    		password = "liyue123
    	}
````
![读者对象](https://github.com/liyue0408/is_analysis/blob/master/test3/%E8%AF%BB%E8%80%85%E5%AF%B9%E8%B1%A1.png)

#####2.5：还书
````
@startuml
	object return {
                读者姓名 = "李玥"
                图书ISBN号 = "22-32-19"
                还书日期 = "2018-4-3"
                }
````
![还书](https://github.com/liyue0408/is_analysis/blob/master/test3/%E8%BF%98%E4%B9%A6.png)


