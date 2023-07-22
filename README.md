# Medical_Diagnosis_KG 
## 运行过程及问题

运行医疗诊断知识图谱，首先将app.py中如下代码注释掉：
```python
handler = ChatBotGraph() #智能问答
handlers = QuestionClassifier() #医学分词
run_train()#模型训练
```

打开app.py第5行代码报错ModuleNotFoundError: No module named 'pylsp_jsonrpc',缺了pylsp_jsonrpc这个包，但是这行代码没有用到可以直接注释掉。

![](https://github.com/chenhaix11/Medical_Diagnosis/blob/main/1.jpeg)

运行app.py时，报错ModuleNotFoundError: No module named 'ahocorasick'，需要安装这个库。

![](https://github.com/chenhaix11/Medical_Diagnosis/blob/main/2.png)

但是安装ahocorasick库报错，这是因为"ahocorasick"库已经升级并改名为"pyahocorasick"，所以找不到这个库了。需要将安装命令改为：

```python
pip install pyahocorasick -i HTTPS://mirrors.aliyun.com/pypi/simple/
```

再次运行app.py出现“以一种访问权限不允许的方式做了一个访问套接字的尝试”的问题，

![](https://github.com/chenhaix11/Medical_Diagnosis/blob/main/3.png)

可以在Edit Configurations的Additional options处输入-p 7600或者-p+其他端口，最后OK就可以了。

![](https://github.com/chenhaix11/Medical_Diagnosis/blob/main/4.png)
![](https://github.com/chenhaix11/Medical_Diagnosis/blob/main/5.png)

重新运行程序就可以了。
需要注意的是，由于上一步中已将端口改为7600，点“登录”或其他功能后出现的页面也需将端口改为7600，否则会出现“无法访问此页面”的问题。

![](https://github.com/chenhaix11/Medical_Diagnosis/blob/main/6.png)
![](https://github.com/chenhaix11/Medical_Diagnosis/blob/main/7.png)
![](https://github.com/chenhaix11/Medical_Diagnosis/blob/main/8.png)



