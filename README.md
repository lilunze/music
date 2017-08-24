# API

- 今日推荐

```
http://www.app-echo.com/api/recommend/sound-day?page=1
```

返回数据object

```
{
    desc:success,
    list:[
        {
            admin_id:"-1",
            area:"1",
            created_at:"1503496802",
            extension:"",
            id:"49398",
            is_stage:"0",
            is_today_recommend:"1",
            obj_id:"1290939",   //专辑id
            obj_type:"1",
            online_time:"1503496802",
            sorting:"0",
            sound:
            {
                id: "1290939",
                name: "", 
                comment_count: "",   //评论数
                like_count: "",     //喜欢数
                share_count: "",   //分享数
                pic: "",    //歌曲封面图片 
                
            }
            status:"1",
            tab_mask:"0",
            top_time:"0",
            type:"3",
            updated_at:"2017-08-23 22:00:02"
        }
    ]
}
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


