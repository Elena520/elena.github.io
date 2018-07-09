# pandas是什么？
- pandas是基于Numpy的一个python数据分析包，主要目的是为了数据分析，提供了大量高级的数据结构和对数据处理的方法.
- pandas 有两个主要的数据结构：Series 和 DataFrame。
# 安装（版本V0.23.x）
- conda install pandas
- python3 -m pip install -upgrade pandas
# Series
    Series是一个一维数组对象,类似于NumPy的一维array。
    它除了包含一组数据还包含一组索引，所以可以把它理解为一组带索引的数组.
    import pandas as pd
    from pandas import Series,DataFrame

    1. 将Python数组转换成Series对象:
    [in] a = Series([1,2,3,-5])
    [in] a
    [out] 0    1
    [out] 1    2
    [out] 2    3
    [out] 3   -5
    [out] dtype: int64

    2. 将python字典转换成Series对象：
    [in] dic = {'a':1,'b':2,'c':3}
    [in] b = Series(dic)
    [in] b
    [out] a    1
    [out] b    2
    [out] c    3
    [out] dtype: int64

    3. 通过index参数显示指定索引：
    [in] c = Series([1,2,3,4],index=['a','b','c','d'])
    [in] c
    [out] a    1
    [out] b    2
    [out] c    3
    [out] d    4
    [out] dtype: int64

    综上：当没有显示指定索引的时候，Series自动以0开始，步长为1为数据创建索引。
         可以通过index参数显示指定索引

    4. 对于Series对象里的单个数据来说，和普通数组一样，根据索引获取对应的数据或重新赋值；
    还可以传入一个索引的数组来获取数据或给数据重新赋值：
    [in] c['a']
    [out] 1

    [in] c[['a','b']]
    [out] a    1
    [out] b    2
    [out] dtype: int64

    [in] c['a'] = 10
    [in] c
    [out] a    10
    [out] b     2
    [out] c     3
    [out] d     4
    [out] dtype: int64

    [in] c[['b','c','d']] = 20
    [in] c
    [out] a    10
    [out] b    20
    [out] c    20
    [out] d    20
    [out] dtype: int64