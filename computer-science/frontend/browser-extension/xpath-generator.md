# xpath generator 是如何实现的?


wp_id: 725
Status: publish
Date: 2017-08-20 18:57:00
Modified: 2020-05-16 11:50:53


写爬虫的话做到最后基本上最终没法自动化的就是指定要抽取的元素的xpath了, 要定向爬一个网站的内容基本上都会归结到去找下一页和数据元素的xpath. 如果能把xpath的生成交给不会写程序的运营同学来做的话, 能够极大地解放程序员的生产力.

毕竟xpath也算是一个DSL, 对于不会编程的同学还是有一定难度的. SQL写得熟练的PM多得是, 想找一个会写xpath的运营同学则是很困难, 毕竟术业有专攻, 运营需要面对的问题和我们程序猿还是有很大不同. 多年的经验, 感觉能教会他们yaml已经是极限了...

那么能不能有一个图形化的工具来生成xpath呢? 答案显然是有的, chrome浏览器就内置了生成xpath的工具, 如下图所示:

![chrome xpath](https://ws4.sinaimg.cn/large/006tNc79ly1flhwpu64uvj31f20keaj4.jpg)

这幅图生成的xpath是: `//*[@id="fc_B_pic"]/ul[1]/li[1]/a[1]`

然而chrome的xpath生成却有几个缺点:

1. chrome的xpath只会想上去找带有id的元素, 而根据实际的情况, 往往找到带有class的元素就可以保证找的xpath是对的了.
2. chrome生成的元素是尽量保证元素唯一的, 也就是当你想要搞一个能能够选中多个元素的xpath时, chrome 无能为力, 还是需要自己去改写.
3. 另外就是生成之后不能方便的用图形工具去验证.

未完待续