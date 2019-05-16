# Quick-ranking

网站快速排名v1.0，适用SEO

程序说明：

程序使用两个线程来运行，线程1在无忧代理上获取免费的ip地址，线程2执行排名函数，这么做是确保数据库中的ip不会被消耗完。

1、由于免费的代理多数是无效的，线程1在获取到ip后还会筛选出真正有效可用的ip地址，并将其存入数据库。

2、排名函数主要是从数据库中随机选择ip地址，然后通过该ip进入到需要访问的网站，使用random模块的作用是防止搜索引擎判断是机器操作
所以使用随机点击与滑动，虽然这么做不能确定是否真实有用，通过同一个网站反复使用该程序，对于排名兴许会有效果。

问题：

1、程序最大的问题其实在开始便暴露出来，多线程的模式运行程序导致数据库中依旧会存在已经使用过的ip（虽然ip会取之不竭），重复使用过多次数
的ip可能会给网站带来不好影响。

2、在找到网站点击进去后程序会执行随机点击和随机滑动的操作，但是经过测试，程序只能随机滑动，无法进行随机点击的操作。

3、可能还存在用户体验等方面的问题，也可能包含搜索引擎算法等相关问题，程序可能有效，也可能无效，但网站快速排名程序后续依旧会优化……
