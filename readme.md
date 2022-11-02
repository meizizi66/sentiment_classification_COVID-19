# 疫情期间网民情绪识别

## 一、简介


本项目为DataFountain比赛项目[疫情期间网民情绪识别](https://www.datafountain.cn/competitions/423 "赛题详情 - DataFountain")，给出抓取的有关新冠肺炎的微博作为训练集，要求对训练集进行情感分类，情感有积极(1)、中性(0)、消极(-1)三种。

## 二、详细的输入输出

用到的数据在data里，无标签的数据可以到官网下载，Bert模型[BERT-Base, Chinese](https://storage.googleapis.com/bert_models/2018_11_03/chinese_L-12_H-768_A-12.zip)，详情请见[google-research/bert](https://github.com/google-research/bert)。

> 竞赛数据以csv格式进行存储，包括nCoV_100k.labled.csv和nCoV_900k.unlabled.csv两个文件，其中：
> - nCoV_100k.labled.csv：包含10万条用户标注的微博数据，具体格式如下：[微博id,微博发布时间,发布人账号,微博中文内容,微博图片,微博视频,情感倾向]
> 1. 微博id，格式为整型。
> 2. 微博发布时间，格式为xx月xx日 xx:xx。
> 3. 发布人账号，格式为字符串。
> 4. 微博中文内容，格式为字符串。
> 5. 微博图片，格式为url超链接，[]代表不含图片。
> 6. 微博视频，格式为url超链接，[]代表不含视频。
> 7. 情感倾向,取值为{1,0,-1}。
> - nCoV_900k.unlabled.csv为90万条未标注的微博数据，包含与“新冠肺炎”相关的90万条未标注的微博数据，具体格式如下：
[微博id,微博发布时间,发布人账号,微博中文内容,微博图片,微博视频]
> 1. 微博id，格式为整型。
> 2. 微博发布时间，格式为xx月xx日 xx:xx。
> 3. 发布人账号，格式为字符串。
> 4. 微博中文内容，格式为字符串。
> 5. 微博图片，格式为url超链接，[]代表不含图片。
> 6. 微博视频，格式为url超链接，[]代表不含视频。

以csv文件格式提交，采用UTF8编码，形式如：

|测试数据id|情感极性|
|:----:|:----:|
|09568|1|
|37361|0|

# 三、提交记录

提交采用BiLSTM，准确率0.63532567，激活函数为sigmoid。

提交采用BiLSTM，准确率0.63222879，激活函数为softmax。
