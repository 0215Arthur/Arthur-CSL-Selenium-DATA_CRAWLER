# Arthur/CSL-Selenium-DATA_CRAWLER
*@arthurPang*

- 使用selenium+phantomjs pyhton3爬取中超球队数据
+ 使用sklearn包建立球队分类模型
+ 对球队数据及球员进行预处理作为训练集，训练赛事结果分类模型
+ 使用第9轮比赛数据进行测试/预测

爬取球队及球员数据
---------------
数据网址为创冰数据分析   
工具为selenium+phantomjs  
*虽然当前selenium对phantomjs已经不再支持，但二者结合还是效率很高*  
### 遇到的问题
+ phantomjs无法使用 
  + 解决方法：将phantomjs.exe放置当前目录下
+ 动态网页点击存在延时效果，爬取下的数据出现错位情况
  + 解决方法： 使用time.sleep()或webserver.sleep()之类的

jupyter cell代码块中已有自己对数据格式的整合处理相关的代码，但写的不够清晰

机器学习分类
-------
使用了SVM,LR,CART决策树与随机森林进行分类   
鉴于**数据的不平衡性**未能完全解决，分类器的二分类效果较理想  
三分类结果一方面由于数据的特性，一方面受模型的特性限制，效果不理想  
使用混淆矩阵、AUC曲线、Recall、Precision进行评估  


实际预测效果
----------
本项目实际为tj数学建模校赛的C题，在**中超第9轮比赛前建模预测第9轮的结果**  
上传项目的时候比赛结果已经出来了，利用监督学习预测的效果非常不理想 
一方面第9轮的比赛中各队的**阵容**有调整，模型学习并未考虑到该点  
另一方面，所用的训练数据也不够出色  
有待提升，建模时仅粗糙尝试了一次**BP网络**效果不好  
但有可能是当时做的比较急，没有认真分析  
实际上这种题目，把数据集处理的比较合理，数据涵盖因素较全面，用BP/其他神经网络都应该获得较好的效果  
但足球比赛的**不确定性太大**，没有完美的模型可以搞定所有不确定性  
所有吹嘘自己模型准确度的bro都是自欺欺人  
