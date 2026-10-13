# 劳务派遣小程序云聘招聘求职小程序厂招小程序企业求职招聘小程序求职招聘人才简历投递工地招工人力资源中介灵活用工-ym7k

获取源码：ym7k.com/11804/劳务派遣小程序云聘招聘求职小程序厂招小程序企业求职招聘小程序求职招聘人才简历投递工地招工人力资源中介灵活用工-ym7k


基于LBS的附近职位功能与地图集成
“附近职位”是招聘小程序重要模块。2025年腾讯上线“附近的工作”小程序，结合地图位置服务帮助求职者找到离家近的工作。灵活就业人员超两亿，打造“十五分钟就业服务圈”成为趋势。

小程序端通过wx.getLocation获取经纬度，需在app.json配置permission和requiredPrivateInfos声明定位用途。定位策略采用“先缓存、后获取”：首次请求授权，后续优先使用缓存位置（有效期10分钟）。

后端使用Haversine公式计算距离：distance = 2Rarcsin(sqrt(sin²((lat2-lat1)/2)+cos(lat1)cos(lat2)sin²((lng2-lng1)/2)))，R为6371km。支持用户设置距离范围（3km/5km/10km），job表建立lat/lng联合索引支持高效查询。

系统支持列表和地图双模式。列表按距离排序展示职位卡片；地图使用微信<map>组件标注职位位置，bindmarkertap处理点击，callout配置气泡信息。隐私合规需严格遵守：定位用途声明真实准确，不未授权获取位置，位置数据仅用于附近职位查询，提供“不授权定位”降级方案。性能优化：Redis缓存热门城市附近职位，距离计算结果缓存，前端分页加载每页20条。

<img width="1920" height="1239" alt="2026042510472729" src="https://github.com/user-attachments/assets/285ccc52-1058-4800-866e-b5d9967624c0" />
<img width="869" height="574" alt="2026042510472026" src="https://github.com/user-attachments/assets/16177ce6-cc19-4535-8784-c247ad115793" />
<img width="1920" height="1169" alt="202604251047354" src="https://github.com/user-attachments/assets/2ae209b6-5b39-4b88-a6a5-2e65eed780d1" />
<img width="1920" height="1169" alt="2026042510473066" src="https://github.com/user-attachments/assets/2ff0be14-318b-4d0d-a60b-70a38c6ba90e" />
