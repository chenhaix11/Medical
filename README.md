# Medical_Diagnosis_KG 
# 医疗诊断知识图谱
随着国内外医疗信息化水平的迅速崛起，产生了海量的有关医学方面的相关数据，除此之外，在互联网上对于健康和智慧医疗的访问量呈指数形式递增，如何有效的利用这些医学数据成为了一个意义重大的课题。医疗诊断知识图谱提供了对医学数据进行高效组织、管理和利用的手段，能够完成更加快捷精确的医学咨询服务。然而，目前构建医疗诊断知识图谱存在着诸多挑战，例如医学数据跨语种且结构复杂，缺乏高效灵活的医疗诊断知识图谱构建技术等等。针对这些问题，本文对构建医疗诊断知识图谱的关键技术进行了全面的概述与分析。此外，还包括医疗诊断知识图谱在医学分词、智能问答、智能诊断等医疗服务中的实现。
## 功能开启要将app.py 如下代码注释关闭
handler = ChatBotGraph() #智能问答

handlers = QuestionClassifier() #医学分词

run_train()#模型训练
## 3个需要neo4j数据库连接的模块
medical_diagnostic_graph.py

answer_search.py

query_graph.py
## 运行过程及问题

运行医疗诊断知识图谱，首先将app.py中如下代码注释掉：
```python
handler = ChatBotGraph() #智能问答
handlers = QuestionClassifier() #医学分词
run_train()#模型训练
```

打开app.py第5行代码报错ModuleNotFoundError: No module named 'pylsp_jsonrpc',缺了pylsp_jsonrpc这个包，但是这行代码没有用到可以直接注释掉。

![](https://github.com/chenhaix11/Medical_Diagnosis_KG/blob/main/images/1.jpeg)

运行app.py时，报错ModuleNotFoundError: No module named 'ahocorasick'，需要安装这个库。

![](https://github.com/chenhaix11/Medical_Diagnosis_KG/blob/main/images/2.png)

但是安装ahocorasick库报错，这是因为"ahocorasick"库已经升级并改名为"pyahocorasick"，所以找不到这个库了。需要将安装命令改为：

```python
pip install pyahocorasick -i HTTPS://mirrors.aliyun.com/pypi/simple/
```

再次运行app.py出现“以一种访问权限不允许的方式做了一个访问套接字的尝试”的问题，

![](https://github.com/chenhaix11/Medical_Diagnosis_KG/blob/main/images/3.png)

可以在Edit Configurations的Additional options处输入-p 7600或者-p+其他端口，最后OK就可以了。

![](https://github.com/chenhaix11/Medical_Diagnosis_KG/blob/main/images/4.png)
![](https://github.com/chenhaix11/Medical_Diagnosis_KG/blob/main/images/5.png)

重新运行程序就可以了。
需要注意的是，由于上一步中已将端口改为7600，点“登录”或其他功能后出现的页面也需将端口改为7600，否则会出现“无法访问此页面”的问题。

![](https://github.com/chenhaix11/Medical_Diagnosis_KG/blob/main/images/6.png)
![](https://github.com/chenhaix11/Medical_Diagnosis_KG/blob/main/images/7.png)
![](https://github.com/chenhaix11/Medical_Diagnosis_KG/blob/main/images/8.png)



