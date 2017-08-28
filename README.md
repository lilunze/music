# API

- 今日推荐

```
http://www.app-echo.com/api/recommend/sound-day?page=1
```

- 专辑

```
http://www.app-echo.com/api/album/list?limit=20&condation=1%3A0%2C2%3A0
```

- echo名人

```
<!-- http://www.app-echo.com/api/famous/famous-user?limit=5 -->
// 名人
http://www.app-echo.com/api/famous/famous-user?limit=12

// 群星
http://www.app-echo.com/api/famous/top-user?page=1&limit=12

// 新入驻
http://www.app-echo.com/api/famous/latest-users?page=1&limit=6

// 推荐
http://www.app-echo.com/api/famous/recommend-users?page=1&limit=6

// 24小时热门
http://www.app-echo.com/api/famous/daily-commend-users?page=1&limit=6

// 名人分类标签
http://www.app-echo.com/api/famous/type-list

// 对应分类的名人
http://www.app-echo.com/api/famous/user-list-by-type?famous_type=2&limit=44
```

- 名人的详细信息

```
// 基本信息
http://www.app-echo.com/api/user/info?id=

// 详细信息
http://www.app-echo.com/api/star/info?uid=

// 获取歌手的专辑排行
http://www.app-echo.com/api/integral/get-rank-list?uid= &limit=50

```



- 视频回声榜，原创回声榜，热门回声榜，每日精选

```
http://www.app-echo.com/api/other/index
```

返回数据

```
{
    status:"",
    desc:"",
    hot_recommend:  //每日精选
    {
        
    }

}
```

- 获取专辑详细信息

```
// id为obj_id

http://www.app-echo.com/api/sound/info?id=1289833&comment=1
```

- 获取热门榜单

```
传递参数limit=返回数据条数
// 日榜
http://www.app-echo.com/api/rank/sound-hot?periods=daily&limit=12

// 周榜
http://www.app-echo.com/api/rank/sound-hot?periods=weekly&limit=12

// 月榜
http://www.app-echo.com/api/rank/sound-hot?periods=monthly&limit=12

```

- 获取原创榜单

```
传递参数limit=返回数据条数
// 日榜
http://www.app-echo.com/api/rank/sound-origin?periods=daily&limit=12

// 周榜
http://www.app-echo.com/api/rank/sound-origin?periods=weekly&limit=12

// 月榜
http://www.app-echo.com/api/rank/sound-origin?periods=monthly&limit=12

```

- 获取视频榜单

```
// 日榜
http://www.app-echo.com/api/rank/mv-hot?periods=daily&limit=12

// 周榜
http://www.app-echo.com/api/rank/mv-hot?periods=weekly&limit=12

// 月榜
http://www.app-echo.com/api/rank/mv-hot?periods=monthly&limit=12
```

- 获取新上专辑

```
// 全部分类
http://www.app-echo.com/api/album/list?limit=20&page=2&condition=1%3A0%2C2%3A0

// 摇滚
http://www.app-echo.com/api/album/list?limit=20&condition=1%3A1%2C2%3A1

// 流行
http://www.app-echo.com/api/album/list?limit=20&condition=1%3A2%2C2%3A1

// 电子
http://www.app-echo.com/api/album/list?limit=20&condition=1%3A3%2C2%3A2

// 古典
http://www.app-echo.com/api/album/list?limit=20&condition=1%3A4%2C2%3A3

// 爵士
http://www.app-echo.com/api/album/list?limit=20&condition=1%3A5%2C2%3A4

// 民谣
http://www.app-echo.com/api/album/list?limit=20&condition=1%3A6%2C2%3A5

// 原声
http://www.app-echo.com/api/album/list?limit=20&condition=1%3A7%2C2%3A0

// 说唱
http://www.app-echo.com/api/album/list?limit=20&condition=1%3A8%2C2%3A0

// 世界音乐
http://www.app-echo.com/api/album/list?limit=20&condition=1%3A9%2C2%3A0

// 轻音乐
http://www.app-echo.com/api/album/list?limit=20&condition=1%3A10%2C2%3A0

// 节奏蓝调
http://www.app-echo.com/api/album/list?limit=20&condition=1%3A12%2C2%3A0

// 蓝调
http://www.app-echo.com/api/album/list?limit=20&condition=1%3A11%2C2%3A0

```

- 获取热门专辑

```
http://www.app-echo.com/api/album/list-for-tab?type=hot&limit=20
```

- 获取专辑详细信息

```
接收专辑的id参数
http://www.app-echo.com/api/album/info?id=参数
```

- 获取频道首页数据

```
http://www.app-echo.com/api/channel/index
```

- 获取频道类别

```
http://www.app-echo.com/api/channel/tag
```

- 获取频道最新

```
http://www.app-echo.com/api/channel/index?order=new
```

- 获取频道最热

```
http://www.app-echo.com/api/channel/index?order=hot
```

- 获取对应频道类别的专辑

```
http://www.app-echo.com/api/channel/index?tag_id=参数
```