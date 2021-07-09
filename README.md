# topic_analyze

利用爬虫爬取1950-1966年这16年间，毛泽东和刘少奇的相关文本（《毛泽东思想万岁》和《刘少奇选集》），对这些文本进行主题分析和比较，进行基本的可视化处理。
所有代码和数据已公开。

因为相当一部分代码是在早期学习过程中所写，必然存在许多冗余和低效的代码段，希望大家体谅。

数据为本人爬取后，供个人学习使用，本身是不平衡的，因此对于结果看看就好。

再次强调，本项目为个人自学过程中的一系列学习过程总结，对分析结果请勿过于苛责。

# 数据爬取和清洗
使用'爬虫——刘少奇选集.ipynb','爬虫——毛万岁.ipynb','毛、刘数据筛选与合并.ipynb','分词.ipynb'。

《毛泽东思想万岁》来自中文马克思主义文库，《刘少奇选集》来自人民日报，删除了日期不明和字数少于1000字的文章，保留下来了共计187篇文章，并拆分为28873个句子。

# word_scatter

使用'文字散布图.ipynb'

比较毛泽东和刘少奇两人的文章在用词上的差异。并生成相关的文字散布图。

![image](https://github.com/qiangjiaodeyugang/topic_analyze/blob/main/image/scattertext_novel_M_L.png)

毛、刘二人词频分布情况。可以看到毛显著的更关心例如‘朝鲜’、‘古巴’等国际局势斗争，以及‘整风’、‘抓’、‘斗’等阶级斗争运动。而刘少奇显著地更关心例如‘国民经济’、‘行业’等经济建设内容。

![image](https://github.com/qiangjiaodeyugang/topic_analyze/blob/main/image/scattertext_topic_model.png)

当我们构造出四个主题模型之后，这种差异就体现的更为明显。我们设立四个主题模型，选择的关键词分别是：
    '阶级斗争': ['右派','知识分子','公社','人民 群众', '马克思主义','资产阶级','抓','整','专政','修正主义','解放','解放斗争'],
    '帝国主义': ['美国','帝国主义','法国','世界','朝鲜','古巴'],
    '思想改造': ['整风','阶级斗争','路线','思想','腐蚀','资产阶级'],
    '经济建设': [ '工商业','企业','经济','发展','先进','建设','私营','公营']。
    
![image](https://github.com/qiangjiaodeyugang/topic_analyze/blob/main/image/scattertext_word_embedding.png)
![image](https://github.com/qiangjiaodeyugang/topic_analyze/blob/main/image/scattertext_doc_based.png)

根据df-idf将词语转换为向量，并通过SVD降维为两个维度后，可以看出两人的关注点是差异明显的。上图为分别以单词和文本为基本单位绘制的二维空间坐标

# topic_analyse

使用df-idf，用one-hat表示句子，并利用非负矩阵分解（NMF, Non-negative Matrix Factorization）降维为12个维度。经过区分，将十二个维度命名为：'路线斗争','国际外交','社会主义改造','历史经验','经济建设','反帝斗争', '知识分子'， '思想改造', '人民公社', '发展规划', '外国渗透', '国内建设'。

## 可视化

比较毛泽东和刘少奇在不同主题维度上的侧重点，发现毛泽东更重视国际局势的变化、阶级斗争和思想改造。尤其是在1962年以后，毛泽东对于国际外交和思想改造的关心显著增加，我们可以猜想，之后国内的一系列运动，可能与毛主席对于国际局势变化的判断有关。

![image](https://github.com/qiangjiaodeyugang/topic_analyze/blob/main/image/%E4%B8%BB%E9%A2%98%E5%8D%A0%E6%AF%94%E6%AF%94%E8%BE%83.png)

毛泽东不同主题维度的历年累计情况

![image](https://github.com/qiangjiaodeyugang/topic_analyze/blob/main/image/%E6%AF%9B%E6%B3%BD%E4%B8%9C%E9%80%90%E5%B9%B4%E7%B4%AF%E8%AE%A1%E5%8F%98%E5%8C%96.png)

刘少奇不同主题维度的历年累计情况

![image](https://github.com/qiangjiaodeyugang/topic_analyze/blob/main/image/%E5%88%98%E5%B0%91%E5%A5%87%E9%80%90%E5%B9%B4%E7%B4%AF%E8%AE%A1%E5%8F%98%E5%8C%96.png)


![image](https://github.com/qiangjiaodeyugang/topic_analyze/blob/main/image/%E5%9B%BD%E5%86%85%E5%BB%BA%E8%AE%BE.png)


![image](https://github.com/qiangjiaodeyugang/topic_analyze/blob/main/image/%E6%80%9D%E6%83%B3%E6%94%B9%E9%80%A0.png)


