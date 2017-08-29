最近闲来无事，就像做一些有趣的东西，于是翻出之前的TODO，计划做一个音乐APP。
查询了baidu,google,github,strackoverflow,segmentfaul等各大网站和论坛，发现目前比较主流的音乐平台像QQ音乐，网易云，酷狗等均没有为用户提供可调用的API和流媒体资源。
最后通过抓包分析，发现echo回声的APP的网络请求中又返回可用的json数据，并且包含流媒体资源链接，这对于向开发一个音乐APP的人来说，无疑是一件好事情，下面是分析除的API:

# API

- 获取今日推荐列表


```
http://www.app-echo.com/api/recommend/sound-day?page=1
```

传递参数

|key|type|含义|
|:---:|:---:|:---:|
|page|number|传递的页码信息|

>返回首页的数据是16条，其余是15条

- 获取新上专辑列表

```
http://www.app-echo.com/api/album/list?limit=参数1&condation=参数2&page=参数3
```

传递参数

|key|type|含义|
|:---:|:---:|:---:|
|limit|number|每页返回的数据量|
|condation|string|想要获取的专辑类型|
|page|number|专辑列表的页码信息|

专辑类型组合查询

|类型|全部|摇滚|流行|电子|古典|爵士|民谣|原声|说唱|世界音乐|轻音乐|蓝调|节奏蓝调|
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:------:|:----:|:--:|:------:|
|value|A0|A1|A2|A3|A4|A5|A6|A7|A8|A9|A10|A11|A12|

|类型|全部|70年代|80年代|90年代|00年代|10年代|
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
|value|A0|A1|A2|A3|A4|A5|

> 组合查询condation参数实例:1%3 风格 %2C2%3 年代  例如：90年代摇滚  为 1%3A1%2C2%3A3

- 获取热门专辑

```
http://www.app-echo.com/api/album/list-for-tab?type=hot&limit=参数&page=参数2
```

传递参数
|key|type|含义|
|:--:|:--:|:--:|
|limit|number|每页返回的数据量|
|page|number|专辑列表的页码信息|




- 获取专辑详细信息

```
http://www.app-echo.com/api/album/info?id=参数
```

传递的参数

|key|type|含义|
|:---:|:---:|:---:|
|id|number|专辑的唯一标识id|



- 获取歌曲详细信息

```
http://www.app-echo.com/api/sound/info?id=参数&comment=1
```

传递参数
|key|type|含义|
|:--:|:--:|:--:|
|id|number|歌曲的唯一标识id|

- echo名人

```
// 名人
http://www.app-echo.com/api/famous/famous-user?limit=参数1

// 群星
http://www.app-echo.com/api/famous/top-user?page=参数1&limit=参数2

// 新入驻
http://www.app-echo.com/api/famous/latest-users?page=参数1&limit=参数2

// 推荐
http://www.app-echo.com/api/famous/recommend-users?page=参数1&limit=参数2

// 24小时热门
http://www.app-echo.com/api/famous/daily-commend-users?page=参数1&limit=参数2

// 名人分类标签
http://www.app-echo.com/api/famous/type-list

// 对应分类的名人
http://www.app-echo.com/api/famous/user-list-by-type?famous_type=参数1&limit=参数2
```

传递的参数

|key|type|含义|
|:---:|:---:|:---:|
|limit|number|每页返回的数据量|
|page|number|列表的页码信息|
|famous_type|number|名人分类的唯一标识id|



- 名人的详细信息


```
// 基本信息
http://www.app-echo.com/api/user/info?id=参数

// 详细信息
http://www.app-echo.com/api/star/info?uid=参数

```

传递参数

|key|type|含义|
|:---:|:---:|:---:|
|id|number|名人的唯一标识id|
|uid|number|名人的唯一标识id|



- 获取热门榜单

```
http://www.app-echo.com/api/rank/sound-hot?periods=参数1&limit=参数2&page=参数3
```

传递的参数


|key|type|含义|
|:---:|:---:|:---:|
|periods|string|获取榜单类型|
|limit|number|每页返回的数据量|
|page|number|请求的列表页码信息|


periods关键字类型

|periods|含义|
|:---:|:---:|
|daily|日榜|
|weekly|周榜|
|monthly|月榜|



- 获取原创榜单

```
http://www.app-echo.com/api/rank/sound-origin?periods=参数1&limit=参数2&page=参数3

```


- 获取视频榜单

```
http://www.app-echo.com/api/rank/mv-hot?periods=daily&limit=12&page=参数3
```


- 每日精选

```
http://www.app-echo.com/api/other/index
```

> 返回的数据中 hot_recommend 字段为每日精选



- 获取频道首页数据

```
http://www.app-echo.com/api/channel/index
```

> 频道首页的数据返回与下面讲到的热门数据相同



- 获取频道类别

```
http://www.app-echo.com/api/channel/tag
```



- 获取最新频道列表

```
http://www.app-echo.com/api/channel/index?order=new
```



- 获取最热频道列表

```
http://www.app-echo.com/api/channel/index?order=hot
```



- 获取对应频道类别的专辑

```
http://www.app-echo.com/api/channel/index?tag_id=参数
```


传递的参数

|key|type|含义|
|:---:|:---:|:---:|
|tag_id|number|频道类别的唯一标识id|

以上是作者分析的大部分常用的API，基本上包含了大部分的信息，如果想要更多细致的内容可以自己深入分析，或者给作者提需求。

下面附上作者发现的比较好的API资源链接：

[知乎资源](https://www.zhihu.com/question/27817786?from=profile_question_card)
[github资源](https://github.com/TonnyL/Awesome_APIs/blob/master/Chinese.md)