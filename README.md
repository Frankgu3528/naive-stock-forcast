### 已经做的事情：
* 用baostock的接口爬取A股的数据存储在`./data`目录下
* 切分2020-1-1到2023-1-1为训练集，2023-1-1到2023-9-1的数据为测试集，用收盘价做变量，拟合三个有代表性的模型（传统统计ARIMA，机器学习模型LightGBM，深度学习模型LSTM）在测试集上进行股价的预测。
* 搭了一个初步的回测系统`backcheck.ipynb`，写了最朴素的量化策略--双均线策略在选定的股票上跑，将收益率与这只股票的涨跌作比较。
### 一些小问题
* 用过去的收盘价做预测会出现一些问题(即如果用前一天的收盘价当做输出就能获得很好的效果)，换成涨跌幅能避免这个问题，同时能避免一些平稳性的检验。
* 回测系统比较朴素，目前只支持某只特定的股票，另外还没把上面三个模型得到的策略加进去。可以进一步写成能在所有上交所交易的股票上进行回测，将三个模型得到的策略与大盘指数进行比较，或者是
* 如果上面没时间做，就偷懒去聚宽等平台上跑。
### 如果要改成pre
* 说一下我们为什么要干这个事情（motivation：想把自己学过的模型拟合到真实数据上，并探究效果如何）
* 说一下我们怎么做的（上面已经很详细了）
* 分析一下我们的结果（曲线怎么样，为什么这么样）
* 说一下我们的结论（为什么这个模型学不到东西，我们进一步有什么改进的思路）