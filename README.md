# API

- 今日推荐
```
http://www.app-echo.com/api/recommend/sound-day?page=1
```

返回数据object
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



- 专辑
```
http://www.app-echo.com/api/album/list?limit=20&condation=1%3A0%2C2%3A0
```

- echo名人
```
http://www.app-echo.com/api/famous/famous-user?limit=5
```

- 视频回声榜，原创回声榜，热门回声榜，每日精选
```
http://www.app-echo.com/api/other/index
```

返回数据
{
    status:"",
    desc:"",
    hot_recommend:  //每日精选
    {
        
    }

}

- 获取专辑详细信息
```
// id为obj_id

http://www.app-echo.com/api/sound/info?id=1289833&comment=1
```

