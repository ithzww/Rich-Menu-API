# Rich-Menu-API


- สร้างรูป Rich Menu 2 แบบ สำหรับสลับไป สลับมา
- กำหนดตำแหน่งของ Rich Menu ให้คลิกแล้วสลับไป สลับมา
- ใช้ API สร้าง Rich Menu และกำหนดค่า สำหรับให้สลับไปสลับมา

### menu1
```
{
  "size": {
    "width": 2500,
    "height": 1686
  },
  "selected": true,
  "name": "menu1",
  "chatBarText": "Bulletin",
  "areas": [
    {
      "bounds": {
        "x": 1350,
        "y": 4,
        "width": 1150,
        "height": 839
      },
      "action": {
        "type": "richmenuswitch",
        "richMenuAliasId": "al-menu2",
        "data": "richmenu=al-menu2"
      }
    }
  ]
}
```
### menu2
```
{
  "size": {
    "width": 2500,
    "height": 1686
  },
  "selected": true,
  "name": "menu2",
  "chatBarText": "Bulletin",
  "areas": [
    {
      "bounds": {
        "x": 1313,
        "y": 8,
        "width": 1187,
        "height": 835
      },
      "action": {
        "type": "richmenuswitch",
        "richMenuAliasId": "al-menu1",
        "data": "richmenu=al-menu1"
      }
    }
  ]
}
```

### Create Rich Menu
```
Headers:
  + Authorization: Bearer {channel access token}
  + Content-Type: application/json
Endpoint: https://api.line.me/v2/bot/richmenu
Method: POST
Body:

ถ้าหากถูกต้อง จะได้ Response
{ "richMenuId": "richmenu-xxx" }
```

### Upload Rich Menu Image
```
Headers:
  + Authorization: Bearer {channel access token}
  + Content-Type: image/jpeg หรือ image/png
Endpoint: https://api-data.line.me/v2/bot/richmenu/{{richMenuId}}/content
Method: POST

ถ้าหากไม่มีอะไรผิดพลาดจะได้ response เป็น {} กลับมา 
```

### Set Alias Rich Menu
```
Headers:
  + Authorization: Bearer {channel access token}
  + Content-Type: application/json
Endpoint: https://api.line.me/v2/bot/richmenu/alias
Method: POST
Body:

{
    "richMenuAliasId": "al-menu2-s-09",
    "richMenuId": "richmenu-xxx"
}

```

### Get Rich Menu Lists 
```
Headers:
  + Authorization: Bearer {channel access token}
Endpoint: https://api.line.me/v2/bot/richmenu/alias/list
Method: GET
```

### Set Default Rich Menu
```
Headers:
  + Authorization: Bearer {channel access token}
Endpoint: https://api.line.me/v2/bot/user/all/richmenu/{{richMenuId}}
Method: POST
```

### Delete Rich Menu
```
Headers:
  + Authorization: Bearer {channel access token}
Endpoint: https://api.line.me/v2/bot/richmenu/{{richMenuId}}
Method: DELETE
```
