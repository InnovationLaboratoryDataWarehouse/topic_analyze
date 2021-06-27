# topic_analyze

利用爬虫爬取1950-1966年这16年间，毛泽东和刘少奇的相关文本（《毛泽东思想万岁》和《刘少奇选集》），对这些文本进行主题分析和比较，进行基本的可视化处理。

# 数据爬取和清洗

《毛泽东思想万岁》来自中文马克思主义文库，《刘少奇选集》来自人民日报，删除了日期不明和字数少于1000字的文章，保留下来了共计187篇文章，并拆分为28873个句子。

# topic_analyse

使用df-idf，用one-hat表示句子，并利用非负矩阵分解（NMF, Non-negative Matrix Factorization）降维为12个维度。经过区分，将十二个维度命名为：'路线斗争','国际外交','社会主义改造','历史经验','经济建设','反帝斗争', '知识分子'， '思想改造', '人民公社', '发展规划', '外国渗透', '国内建设'。

# 可视化

比较毛泽东和刘少奇在不同主题维度上的侧重点，发现毛泽东更重视国际局势的变化、阶级斗争和思想改造。尤其是在1962年以后，毛泽东对于国际外交和思想改造的关心显著增加，我们可以猜想，之后国内的一系列运动，可能与毛主席对于国际局势变化的判断有关。

![image](https://github.com/qiangjiaodeyugang/topic_analyze/blob/main/image/%E4%B8%BB%E9%A2%98%E5%8D%A0%E6%AF%94%E6%AF%94%E8%BE%83.png)

毛泽东不同主题维度的历年累计情况

![image](https://github.com/qiangjiaodeyugang/topic_analyze/blob/main/image/%E6%AF%9B%E6%B3%BD%E4%B8%9C%E9%80%90%E5%B9%B4%E7%B4%AF%E8%AE%A1%E5%8F%98%E5%8C%96.png)

刘少奇不同主题维度的历年累计情况

![image](https://github.com/qiangjiaodeyugang/topic_analyze/blob/main/image/%E5%88%98%E5%B0%91%E5%A5%87%E9%80%90%E5%B9%B4%E7%B4%AF%E8%AE%A1%E5%8F%98%E5%8C%96.png)


![image](https://github.com/qiangjiaodeyugang/topic_analyze/blob/main/image/%E5%9B%BD%E5%86%85%E5%BB%BA%E8%AE%BE.png)


![image](https://github.com/qiangjiaodeyugang/topic_analyze/blob/main/image/%E6%80%9D%E6%83%B3%E6%94%B9%E9%80%A0.png)


