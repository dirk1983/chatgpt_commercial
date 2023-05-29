# chatgpt_commercial
**本项目是基于我的免费开源版本 https://github.com/dirk1983/chatgpt 开发的商业版，同样使用PHP开发，没用任何框架，方便二次开发。**

**和我的免费开源项目相比有以下几项差异：**

| 差异 | 开源版 | 商业版 |
| --- | --- | --- |
| 是否开源 | 完全开源 | 完全开源，支持二开。更新需要绑定域名，不允许转卖 |
| 项目定位 | 个人自用或小范围分享，对服务器资源要求低 | 商业化运营，支持用户付费使用，对服务器资源要求高一些 |
| 问答速度 | stream流模式，session传递问题和上下文，无需数据库，但多人同时使用时可能会卡顿 | stream流模式极速版，更多异常和超时处理机制，数据库传递问题和上下文，多人使用不卡顿 |
| 历史对话 | 不支持用户查看自己的历史对话，仅展示当前对话，管理员可以查看所有用户历史对话 | 用户可以查看自己的所有对话记录，可以切换到任意一个话题的上下文中继续提问 |
| 支持会员 | 不支持 | 支持会员和提供付费业务 |
| API_KEY数量 | 只能配置一个 | 可以配置无数个，自动轮询，自动剔除无效API_KEY |
| 前端界面 | 默认深色背景风格 | 默认浅色背景风格，未来将支持多种风格随意替换 |
| 使用模式 | 只能免费分享给朋友使用，或要求使用者自备API_KEY | 用户可以通过在线支付购买查询次数，或通过淘宝或发卡站购买储值卡使用 |
| 角色和场景 | 支持预设问题，不支持定义角色 | 支持定义角色和针对各场景的预设问题 |
| 画图功能 | 新版已支持画图功能 | 支持画图功能 |
| 切换模型 | 只能设置单一模型 | 支持多种模型自选，费用可以单独设定 |
| 功能扩展 | 免费使用，用户根据自己需要改进代码，开源版未来没有架构层面修改的计划 | 一次购买永久免费升级，用户可以提需求，商业版会不断改进并持续更新 |

**本项目目前已实现的功能如下：**

1. 无需注册会员，微信扫码登录，独有技术，无需用户授权，丝滑体验。也可以设置注册账号使用，使用邮箱、密码登录。并且支持通过第三方会员系统单点登录。
2. 每个微信用户可以设置成免费体验若干条数和天数，对话按次收费。不同的模型可以设置不同的价格。
3. 后台可以设置API_KEY列表，全局+出错时自动轮询，保证用户每次查询都能返回结果。
4. 支持微信支付官方接口（JSAPI模式）和支付宝当面付官方接口，也提供易支付第三方支付安装包。
5. 支持批量生成充值卡，可设置查询次数和有效期，方便没有在线支付接口的朋友挂到发卡站、淘宝店、微店、扫站长微信二维码转账。
6. 进一步优化接口响应速度，实现秒级回复，并支持查询和继续历史对话。
7. 支持切换模型，支持切换角色和场景，支持OpenAI画图功能。模型、角色、场景在后台都可以自定义。
8. 支持关键词过滤，支持百度内容审核，问题和答案都可以进行过滤和审核。
9. 支持在后台修改API接口的反代地址及代理地址，网站可放在国内运营。
10. 支持网站公告功能，支持后台自动更新程序。

**近期功能规划：**

1. 适配新版UI，演示地址：http://next.ipfei.com
2. 提供插件功能

**部署要求：**
1. 运行本项目必须要有自己的服务器，虚拟主机+Mysql数据库也可以，我不提供服务器或虚拟主机服务，请各位自行购买。
2. 最好是在海外服务器上部署本项目，比如腾讯云东京轻量，国内服务器访问OpenAI接口的话需要代理或反代。
3. 对CPU没有太高的要求，内存最好不小于1GB，硬盘容量20GB也能用，后期随着问答日志的增加可再考虑扩容。
4. 本项目对性能和带宽消耗极低，对于几百个用户的规模各云主机运营商最低的配置就够用。
5. 内部论坛上已有详细的安装流程和配置文档，部署起来很简单，小白用户也能自己搞定。
6. 使用自己的服务号登录的话需要有公司，注册微信官方支付接口也需要。没有公司的可以使用我提供的公共服务号，并使用微店、淘宝等出售充值卡。也可以使用易支付等第三方支付平台收款，稳定性差一些。

**其他说明：**
1. 本商业版网站目前已完成如上所述的功能，其他功能将尽快完善。
2. 当前价格399元，限量100人，未来随着功能不断完善可能会提升价格，但只要一次购买终身免费升级。
3. 只要是通用需求我会尽快完善免费更新。我的微信群已有近4000群友，都是潜在用户，我有动力用好产品打动他们。
4. 商业版完全开源，支持远程自动更新。网站更新和登录需要授权并绑定域名，提供顶级域名即可，二级域名可随时更换。
5. 每个购买者可加入内部论坛和微信群，讨论产品，对接资源。圈子氛围融洽，干货满满，机会多多，多个朋友多条路，网站399，朋友值千金。一流产品靠运营。
6. 源码仅限购买者使用，请不要免费分享或转卖本项目源码，否则将永久被拉黑。君子协定，自觉遵守，唯有人品，可立一生。
7. 欢迎大家多多宣传本项目。购买者越多，项目越能良性运营下去，每个人都能持续受益。
8. 测试网址和购买方式请进群获取，每个用户免费提问20次，欢迎测试并提出宝贵意见。


**有购买意愿的朋友请加群咨询，名额有限，欲购从速。之前的群人满200了，懒得加好友单独拉了，有兴趣的进新群吧。**

群内仅限咨询商业版事宜，商人、已购用户、发广告的请不要再加了，谢谢配合。

![商业群二维码](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/8bd93573-e9cd-4789-b0b6-f8eba4bd2e9f)



**前台界面截图如下（目前界面比较简单，后续会不断改进，欢迎大家提供好看的前端用来借鉴。）：**

PC端：
![1](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/9eb8a2cc-26a4-4abe-9e44-190181d9fbb7)
![2](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/3770f430-69a0-4a08-b506-6f019ce25efd)
![3](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/fd1d07c5-9c89-4c2f-80c2-22458440961b)
![4](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/857054c2-3bfb-48b5-acaa-234fe1704753)
![5](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/cd5a0b49-db7a-4ddb-8620-31d84d5ea87a)
![6](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/13d008ee-db16-4b60-966a-88e067d4ff10)
![7](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/a37a62f0-68cb-47d9-8bfa-9b40a352f21c)
![8](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/06b152ae-a61f-4cd5-8f58-817dd3506cae)
![9](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/9ebc0923-3206-4764-9be7-e778804a407a)
![10](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/60d6e8e7-a57f-4f84-aa9b-0f6c66f6193a)

手机端：
![m1](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/ab2d5af8-bb11-4176-90ae-90cc1e89f8a5)
![m2](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/c9831ef7-5ce5-4725-9382-4ab715ae1394)
![m3](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/422fa0db-20f0-421f-a659-598bb2a36974)
![m4](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/383c5caf-c64d-49fb-9e00-ac6d539d131d)
![m5](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/6525abff-4293-408a-b814-9ca52aa30b1a)
![m6](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/e670e39f-c62e-4243-ae48-b72c814bfda3)
![m7](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/c2daaf16-b623-46a1-82bb-e76027af069b)
![m8](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/327323d9-4400-4fba-b96d-48d8b20d8254)

后台：
![b1](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/48bc2f59-50f8-4c11-96e1-3e8c60106992)
![b2](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/8bc4dbec-9c74-4717-8810-52f42bd6eef2)
![b3](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/d384dcc5-0d87-4c24-ac95-c26cedf5e45b)
![b4](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/5c742ce3-fa2c-4b61-b4c3-051805be74db)
![b5](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/0a9ba3cd-fb62-4639-bcee-505c981061de)
![b6](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/b882ce39-cb30-4734-8a6c-0d9e04e5598a)
![b7](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/286870d9-e4a2-4c49-a394-6547c56c18aa)
![b8](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/426adeef-3386-4a3a-8604-76637acccb38)
![b9](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/d8bdcfdd-7c98-4cbd-a4ea-d7d60a080c5b)
![b10](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/ef32b410-f62f-472d-ad0e-f8eba68b699b)
![b11](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/70f42d6b-d6f0-4064-b52c-5c39884aa81e)
![b12](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/0da6acad-baab-479d-a6c5-70fbb08d01c0)
![b13](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/c6b8fa6c-85c4-4c94-b08c-a88eb5d08d35)
![b14](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/18f474a6-d355-45a8-ba59-2016924f4a7c)
![b15](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/cc111947-dc5d-4143-9bcb-d4de63170c76)
![b16](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/bdf444da-22bd-40e9-b2f8-78ad521021c1)
