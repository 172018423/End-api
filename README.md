# PRD_短视频分析助手

---

## PRD 价值主张设计 


### PRD1.加值宣言 

运用人工智能技术(**视频内容分析**,**媒体内容审核**)来加持短视频分析，解决用户痛点


---

### PRD2.核心价值 

* 目前短视频市场正迎来爆发，这款app将为视频内容发布者提升视频的曝光量

* 能输出视频内容的泛标签，从而提高用户搜索准确度

* 帮助视频内容审核者大幅度提高效率

---

### PRD3.核心价值与用户痛点 

* 短视频数量众多，用户无法精准搜索到自己所需的视频内容，发布者的视频曝光量也难以得到提升

* 视频内容发布者要花费大量的时间去审核发布者发布的视频是否符合发布规则

---

### PRD4.人工智能概率性与用户痛点 

* **视频内容分析**：泛标签提取是基于自然语言处理，当内容复杂时识别可能会出错，导致分类错误。还有一些特殊物品还无法识别，例如一些药品，水果等

* **媒体内容审核**：当图像场景颜色并不丰富或者遮挡时，尤其出现大块单色物体时，系统将无法识别或者识别错误

---

### PRD5.需求列表与人工智能API加值 

* **百度API**：视频内容分析,媒体内容审核

* 接口描述：

1.**视频内容分析**-通过多维AI技术，对视频进行智能分析，输出视频内容的泛标签，从而提高搜索准确度和用户推荐视频的曝光量

2.**媒体内容审核**-可对视频、语音、图片、文本等多媒体内容进行审核，可覆盖色情、暴恐、政治敏感、广告、违禁事物等多维度识别，为您大幅降低人工审核的风险和成本。

* 接口地址：

1.[视频内容分析](https://cloud.baidu.com/product/video/vca)

2.[媒体内容审核](https://cloud.baidu.com/product/mcr.html)

* 请求方法：POST



---

## 原型 

### 原型1.交互及界面设计与信息设计

* 信息设计

![输入图片说明](https://images.gitee.com/uploads/images/2020/0110/093853_3ba44d51_1829822.png "原型信息设计.PNG")

* 界面设计：

![输入图片说明](https://images.gitee.com/uploads/images/2020/0110/093915_c889e9d2_1829822.png "1.PNG")

![输入图片说明](https://images.gitee.com/uploads/images/2020/0110/093923_ec0c7134_1829822.png "2.PNG")

![输入图片说明](https://images.gitee.com/uploads/images/2020/0110/093930_45b6ce4f_1829822.png "3.PNG")

![输入图片说明](https://images.gitee.com/uploads/images/2020/0110/093938_0e51f123_1829822.png "4.PNG")

![输入图片说明](https://images.gitee.com/uploads/images/2020/0110/093946_aebc5cfb_1829822.png "5.PNG")

![输入图片说明](https://images.gitee.com/uploads/images/2020/0110/093958_561b89e3_1829822.png "6.PNG")

![输入图片说明](https://images.gitee.com/uploads/images/2020/0110/094011_2097a501_1829822.png "8.PNG")


### 原型3.原型文档

* [完整原型请点击此查看](http://nfunm172018423.gitee.io/video_assistant_prototype_2)

* [Github下载链接](https://github.com/172018423/video-)



---

## API 产品使用关键AI或机器学习之API的输出入展示 

### API输入输出尝试

* 代码：

```
import requests as req
api = 'https://api-cn.faceplusplus.com/facepp/v3/detect'
api_key = 'ea8v9eHeYWpgMw7jvD5CsN5pODwyJZ41'
api_secret = 'WxNyyqVtkeHLApDLC9n846NshHAokkf2'
vedeo_url = 'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1568615911164&di=c4fc76c9a7e1350fac590e8cf292d230&imgtype=0&src=http%3A%2F%2Fimages.chizhouren.com%2Fforum%2F201510%2F11%2F152607pzqruiwiirdiylye.jpg'
rep = req.post(api,data={'api_key':api_key,'api_secret':api_secret,'image_url':image_url})
 {
    "code": 0,
    "message": "NoError",
    "codeDesc": "Success",
    "data":[
        {
            "confidence": 20, 
            "category": "pornDetection", 
            "suggestion": "block", 
            "subCode": "0", 
            "label": "porn"
        },
        {
            "confidence": 30, 
            "category": "pornDetection",
            "suggestion": "pass", 
            "subCode": "0", 
            "label": "hot"
        },
        {
            "confidence": 50, 
            "category": "pornDetection",
            "suggestion": "pass", 
            "subCode": "0", 
            "label": "breast"
        },
        {
            "confidence": 50, 
            "category": "pornDetection",
            "suggestion": "pass", 
            "subCode": "0", 
            "label": "ass"
        },
        {
            "confidence": 50, 
            "category": "pornDetection",
            "suggestion": "pass", 
            "subCode": "0", 
            "label": "bareBody"
        },
        {
            "confidence": 50,
            "category": "pornDetection",
            "suggestion": "pass", 
            "subCode": "0", 
            "label": "unrealHotPeople"
        },
        {
            "confidence": 100,
            "category": "OCR",
            "suggestion": "block", 
            "label": "ocr",
            "subCode": "0", 
            "ocrMsg":"加微信看爽片"
        },
        {
            "confidence": 100,
            "category": "OCR",
            "suggestion": "block", 
            "label": "UgcAntiSpam    ",
            "subCode": "0"
        },
        {
            "confidence": 80,
            "category": "political",
            "suggestion": "block", 
            "label": "political",
            "subCode": "0", 
            "candidates":[{"confidence":80,"name":"张三"}, {"confidence":70,"name":"李四"}]
        },
        {
            "confidence": 100,
            "category": "QRCode",
            "suggestion": "block", 
            "label": "QRCode",
            "subCode": "0", 
            "candidates":["http://u.wechat.com/EGn4HWqn3jXK8xvx52uUYRE","http://u.wechat.com/EGn4HWqn3jXK8xvx52uUYkE"]
        },
        {
            "confidence": 70,
            "category": "liveScene",
            "suggestion": "block", 
            "subCode": "0", 
            "label": "smoke"
        }
    ]
}
```

* 结果：
```
{'code': 0,
 'message': 'NoError',
 'codeDesc': 'Success',
 'data': [{'confidence': 20,
   'category': 'pornDetection',
   'suggestion': 'block',
   'subCode': '0',
   'label': 'porn'},
  {'confidence': 30,
   'category': 'pornDetection',
   'suggestion': 'pass',
   'subCode': '0',
   'label': 'hot'},
  {'confidence': 50,
   'category': 'pornDetection',
   'suggestion': 'pass',
   'subCode': '0',
   'label': 'breast'},
  {'confidence': 50,
   'category': 'pornDetection',
   'suggestion': 'pass',
   'subCode': '0',
   'label': 'ass'},
  {'confidence': 50,
   'category': 'pornDetection',
   'suggestion': 'pass',
   'subCode': '0',
   'label': 'bareBody'},
  {'confidence': 50,
   'category': 'pornDetection',
   'suggestion': 'pass',
   'subCode': '0',
   'label': 'unrealHotPeople'},
  {'confidence': 100,
   'category': 'OCR',
   'suggestion': 'block',
   'label': 'ocr',
   'subCode': '0',
   'ocrMsg': '加微信看爽片'},
  {'confidence': 100,
   'category': 'OCR',
   'suggestion': 'block',
   'label': 'UgcAntiSpam    ',
   'subCode': '0'},
  {'confidence': 80,
   'category': 'political',
   'suggestion': 'block',
   'label': 'political',
   'subCode': '0',
   'candidates': [{'confidence': 80, 'name': '张三'},
    {'confidence': 70, 'name': '李四'}]},
  {'confidence': 100,
   'category': 'QRCode',
   'suggestion': 'block',
   'label': 'QRCode',
   'subCode': '0',
   'candidates': ['http://u.wechat.com/EGn4HWqn3jXK8xvx52uUYRE',
    'http://u.wechat.com/EGn4HWqn3jXK8xvx52uUYkE']},
  {'confidence': 70,
   'category': 'liveScene',
   'suggestion': 'block',
   'subCode': '0',
   'label': 'smoke'}]}
   ```

---

### API2.使用比较分析 

* 百度与腾讯与阿里云的比较（参考链接：[人脸识别哪家强？](https://www.zhihu.com/question/37060782)）：

1.在视频内容分析方面，百度是国内首个基于视频内容理解的分析技术，提供独有的场景化服务。经过海量视频数据训练，分析，建模，输出TAG达万级别，识别精度高。

2.从侧重点方面来看，腾讯云的识别侧重于CMS政务，阿里云侧重于电商，百度云则更侧重于内容发布识别还有人脸识别方面的服务。

---

### API3.使用后风险报告

* 参考链接:[人工智能在视频识别领域的应用](https://www.doc88.com/p-2157492931800.html)


* 发展性：

1.网络视频已成为网络娱乐产业的核心支柱，未来短视频平台将开放大量的商业化机会，流量变现带来较大的市场规模增长。

2.视频内容分析技术已经渗透到了各行各业，例如生物医学图像，机器人视觉感官等领域。

3.媒体内容审核已在视频标签分类还有视频审核中得到初步应用，未来所有主流的视频平台都将会采用这项技术来提高运作效率。

4.未来本项目将会往平台方面发展，形成一个互联网买家和卖家数据分析云平台，透过一个结构化，系统化的短视频大数据分析平台，帮助用户分析热点创意，打造高爆款短视频。

5.通过数据分析抢占短视频商业应用的制高点，利用5g，大数据，云计算等新技术手段，在短视频领域进行全生命周期智能化服务是大势所趋。


* 风险：

1.人脸识别的仿冒认证。人脸识别系统可以对摄像头采集的人脸图像进行辨认，却无法识别采集的人脸图像是来自真人还是一张照片。

2.人工智能算法主导的视频内容生产与信息分发，带来了信息茧房效应与算法偏见等问题，冲击网络舆论生态。
