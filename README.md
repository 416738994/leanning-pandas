# leanning-pandas
Do what i want
pandas
一维数据，Series,s = pd.Series([1,3,5,np.nan,6,8])
二维数据，DataFrame
一，创建数据

1.通过添加index 跟标签行 以及矩阵创建二维操作数组
dates = pd.date_range('20130101', periods=6)
pd.DataFrame(np.random.randn(6,4), index=dates, columns=list('ABCD'))
Dataframe（数据，索引，标题）
2.还可以通过字典的方式创建DataFrame
df2 = pd.DataFrame(
{'A':1,
 'B' : pd.Timestamp('20130102')
 'C' : pd.Series(1,index=list(range(4)),dtype='float32'), #range(4) means [0, 1, 2, 3]
 'D' : np.array([3] * 4,dtype='int32'),
 'E' : pd.Categorical(["test","train","test","train"]),
 'F' : 'foo'
}
)
df2
     A          B    C  D      E    F
0  1.0 2013-01-02  1.0  3   test  foo
1  1.0 2013-01-02  1.0  3  train  foo
2  1.0 2013-01-02  1.0  3   test  foo
3  1.0 2013-01-02  1.0  3  train  foo
#这个案例中有几个地方地方需要关注的
1. A,B，F列自动填充了4列
2. C,D列申明了是4列，假设C/D列少于4列了？ 报错，数组必须是等宽 ValueError: arrays must all be same length

二，查看数据
df.head(n), 查看前n列的数据
df.tail(n), 查看底部n列的数据

df.index,查看索引
df.values，查看值
df.columns，查看列名

df.describe，快速描述值  percentiles, include, exclude
percentiles ，控制的是取样范围，百分之几的样本量
#######

        A    C    D
count  4.0  4.0  4.0
mean   1.0  1.0  2.0
std    0.0  0.0  0.0
min    1.0  1.0  2.0
25%    1.0  1.0  2.0
50%    1.0  1.0  2.0
75%    1.0  1.0  2.0
max    1.0  1.0  2.0
25，50，75是分位数！！！什么叫分位数我也不知道，
主体上来讲，.25,.50,.75 主要是来体现，Q3跟Q1的位间距，位间距越少，说明数据越集中

#######



#多维数据
