# API
- 返回json
- 來個swagger吧?
- http://json.parser.online.fr/

# 認證
## POST: /user-login
- 登入用
- 帶入帳號密碼返回一組token

### 接受
```
account:str
password:str
```
### 返回
```
{
    token:str,
    msg:str,
    devMsg:str,
    staCode:number
}
```




# 取得列表

## GET: /get-available-area     (ok)
- 取得可旅遊地區(台北、台中、高雄)

### 返回
```
id:integer
name:string
longitude(10, 7)
latitude(10, 7)
```

### 範例格式
```
{
    "area":[
      {
        "id":1,
        "name":"台中",
        "lat":24.147736,
        "lon":120.673648
      },
      {
        "id":2,
        "name":"台北",
        "lat":25.032969,
        "lon":121.565418
      },
      {
        "id":3,
        "name":"台南",
        "lat":22.999728,
        "lon":120.227028
      }
    ]
}
```

## GET: /get-all-point-type     (ok)
- 取得目前景點分類種類(玩、景、逛)

```
{
    "types":[
        {
            "id":1,
            "name":"玩"
            
        },
        {   
            "id":2,
            "name":"喝"
        },
        {
            "id":"3"
            "name":"玩"
        }
    ],
}
```

# 查詢(通用)

## POST: /recommend-food
- 推薦餐廳

#### 欄位
```
token
lon
lat
range
```
#### 返回
- 待補

## POST: /place-name-autocomplete
- 模糊搜尋資料庫內景點地名

#### 欄位
```
search : string
```

#### 返回
- 假設search = 一中
- 返回前五筆有"台"字之結果。名稱與ID

``` 
{
    "res":[
        {"id":1,"name":"一中街"},
        {"id":2,"name":"台中一中"}
    ], 
    "sta":"ok"
}
```

## GET: /area-info/{id}  (ok)
- 取得區域資訊

```
area: {
    id: 2,
    name: "台北",
    longitude: "121.5654177",
    latitude: "25.0329694",
}
```

#### 返回

```
id:integer
name:string
longitude(10, 7)
latitude(10, 7)
```

## GET: /place-info/{id} （ＯＫ）
- 取得該地點詳細資料

# 推薦模式API
## POST: /get-nearby-place
- 取得自身地點附近景點
- 返回最多三個

#### 欄位
```
lon:float 自身所在經度
lat:float 自身所在緯度
range:num 要搜尋半徑多少公尺
travel_area_id:num 目前在哪個地區旅遊(id)
with_out_place_ids:[num,num...] 排除的地點id
```
~~last_select_pacle_id 上一個選擇地點的id~~

#### 返回
```
{
    "datas":[{
       "place_name":string,
       "place_address":string
       "lon":float,
       "lat":float,
       "place_introduce_text":string,
       "place_id":num,
       "place_rating":float,
       //該地點停留時間
       "place_stay_time":50,
       //相對於最後一個選擇點的交通時間
       "trafic_time_relative_last_select":num(分鐘),
       place_img_url:string
    },{
       //同上 
    },{
       //同上 
    }],
    "num":3,
    "sta":"ok"
}
```

## POST: /get-nearby-place-fake
- "隨機"返回三個地點資料


#### 欄位
```
lon:float 自身所在經度
lat:float 自身所在緯度
range:num 要搜尋半徑多少公尺
travel_area_id:num 目前在哪個地區旅遊(id)
with_out_place_ids:[num,num...] 排除的地點id
```
~~last_select_pacle_id 上一個選擇地點的id~~

#### 返回
```
{
    "datas":[{
       "id":num,
       "title":string,
       "address":string
       "longitude":float,
       "latitude":float,
       "recommendation":string,
       "rating":float,
       "stay_time":50,
       "place_img_url":string
       
       //相對於最後一個選擇點的交通時間
       "trafic_time_relative_last_select":num(分鐘),
       
    },{
       //同上 
    },{
       //同上 
    }],
    "num":3,
    "status":"OK"
}
```