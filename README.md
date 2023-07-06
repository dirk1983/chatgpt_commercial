# chatgpt_commercial
**本项目是基于我的免费开源版本 https://github.com/dirk1983/chatgpt 开发的商业版，同样使用PHP开发，没用任何框架，方便二次开发。**

**和我的免费开源项目相比有以下几项差异：**

| 差异 | 开源版 | 商业版 |
| --- | --- | --- |
| 是否开源 | 完全开源 | 所有代码未加密未混淆，支持二开。更新、用户登录需要绑定域名，不允许转卖 |
| 项目定位 | 个人自用或小范围分享，对服务器资源要求低 | 商业化运营，支持用户付费使用，对服务器资源要求高一些 |
| 问答速度 | stream流模式，session传递问题和上下文，无需数据库，但多人同时使用时可能会卡顿 | stream流模式极速版，更多异常和超时处理机制，数据库传递问题和上下文，多人使用不卡顿 |
| 历史对话 | 不支持用户查看自己的历史对话，仅展示当前对话，管理员可以查看所有用户历史对话 | 用户可以查看自己的所有对话记录，可以切换到任意一个话题的上下文中继续提问 |
| 支持会员 | 不支持 | 支持会员和提供付费业务 |
| API_KEY数量 | 只能配置一个 | 可以配置无数个，自动轮询，自动剔除无效API_KEY |
| 前端界面 | 默认深色背景风格 | 支持多种风格替换，最新适配ChatGPT-Next-Web风格 |
| 使用模式 | 只能免费分享给朋友使用，或要求使用者自备API_KEY | 用户可以通过微信支付、支付宝在线购买，或通过淘宝或发卡站购买储值卡使用 |
| 角色和场景 | 支持预设问题，不支持定义角色 | 支持定义角色和针对各场景的预设问题 |
| 画图功能 | 新版已支持画图功能 | 支持OpenAI画图、简单的MJ画图、SD画图功能 |
| 切换模型 | 只能设置单一模型 | 支持多种模型自选，费用可以单独设定 |
| 功能扩展 | 免费使用，用户根据自己需要改进代码，开源版未来没有架构层面修改的计划 | 一次购买永久免费升级，用户可以提需求，商业版会不断改进并持续更新 |

**本项目目前已实现的功能如下：**

1. 无需注册会员，微信扫码登录，独有技术，无需用户授权，丝滑体验。也可以设置注册账号使用，使用邮箱、密码登录。并且支持通过第三方会员系统单点登录。
2. 每个用户可以设置成免费体验若干条数和天数，每天登录、邀请好友注册送查询次数，对话按次收费。不同的模型可以设置不同的价格。
3. 后台可以设置API_KEY列表，全局+出错时自动轮询，保证用户每次查询都能返回结果。每种模型单独设置API_KEY，支持第三方GPT4的API。
4. 支持微信支付官方接口（JSAPI模式）和支付宝当面付官方接口，也提供易支付第三方支付安装包。
5. 支持批量生成充值卡，可设置查询次数和有效期，方便没有在线支付接口的朋友挂到发卡站、淘宝店、微店、扫站长微信二维码转账。
6. 进一步优化接口响应速度，实现秒级回复，详细错误提示，超时处理，并支持查询和继续历史对话。
7. 支持切换模型，支持切换角色和场景，支持OpenAI画图、简单的MJ画图、SD画图功能。模型、角色、场景在后台都可以自定义。
8. 支持关键词过滤，支持百度内容审核，问题和答案都可以进行过滤和审核。
9. 支持在后台修改API接口的反代地址及代理地址，网站可放在国内运营。支持自定义AI身份，隐藏openai和chatgpt有关信息。
10. 支持用户自行开发自定义插件，升级不受影响。内部论坛已提供用户付费购买的插件，如分销插件、其他风格的UI、专业的画图、联网搜素插件等。
11. 支持网站公告功能，支持后台一键更新到最新版本。

**近期功能规划：**

1. 开发知识库有关功能

**部署要求：**
1. 运行本项目必须要有自己的服务器，虚拟主机+Mysql数据库也可以，我不提供服务器或虚拟主机服务，请各位自行购买。
2. 最好是在海外服务器上部署本项目，比如腾讯云东京轻量，国内服务器访问OpenAI接口的话需要代理或反代。
3. 对CPU没有太高的要求，内存最好不小于1GB，硬盘容量20GB也能用，后期随着问答日志的增加可再考虑扩容。
4. 本项目对性能和带宽消耗极低，对于几百个用户的规模各云主机运营商最低的配置就够用。
5. 内部论坛上已有详细的安装流程和配置文档，部署起来很简单，小白用户也能自己搞定。
6. 使用自己的服务号登录的话需要有公司，注册微信、支付宝官方支付接口也需要。没有公司的可以使用我提供的公共服务号，并使用微店、淘宝等出售充值卡。也可以使用易支付等第三方支付平台收款，稳定性差一些。

**其他说明：**
1. 当前价格999元，一次购买终身免费升级。
2. 在我这里购买的用户自动获得代理资格，可以销售给其他用户赚差价。
3. 如果仅自用也可以在代理商处购买，价格更低。
4. 商业版包含全部源码，未作任何加密或混淆，支持远程自动更新。网站更新和登录需要授权并绑定域名，提供顶级域名即可，二级域名可随时更换。
5. 每个购买者可加入内部论坛学习部署和安装教程，小白也能轻松搞定。
6. 源码仅限购买者使用，请不要免费分享或转卖本项目源码，否则将永久被拉黑。君子协定，自觉遵守，唯有人品，可立一生。
7. 测试网址：https://chatpro.ipfei.cn
8. 购买链接：https://item.taobao.com/item.htm?id=713331539595

**版本发布日志：**
http://bbs.ipfei.com/forum.php?mod=forumdisplay&fid=37

**有购买意愿的朋友也可以加微信好友咨询，微信小号，可能回复不会太及时**

![微信截图_20230306154434](https://user-images.githubusercontent.com/5563148/223048985-4cac05cb-acf0-4f04-aad5-1c3dcec609d0.png)



**前台界面截图如下：**

**PC端：**

![image](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/c6b4c2e2-235e-4b1c-92d1-404307df0049)

![image](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/dde0265e-9d60-4e7e-9517-5d7521451aa3)

![image](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/af0c22d5-0a7c-4785-b87a-42d18b1230b7)

![image](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/2ba1d898-9ab6-4659-8bab-ab7b114b73e6)

![image](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/ad6c7ce4-4462-4dcf-a896-e8a046564a6b)

![image](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/2986cbb5-957c-4ce5-88d0-4bb6333285c6)

![image](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/f8804b0d-ee02-4d82-82bc-52ef581278fd)

![image](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/cef0e820-179e-4ae1-bcf8-bfc62670a80d)


**手机端：**

![dff7397e7f02170eb0a0e10bdcb93cf](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/a9b30aeb-91a5-4740-a4c6-58f52c2d5302)

![602142571f86f7498b792e21b6f263c](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/48674568-d5ee-4171-9fc4-e51d44bb0639)

![dc18f0dc15cd0610f3426773fdc10eb](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/5529fc34-8589-4d3d-b30d-f8a8372ea069)

![4b95c8b65b3681e4e907d9e563cf4bb](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/e7ba779d-5c00-482e-912f-24605aa6cccb)

![cddbd5dc3309b758585694501eed054](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/e422683f-74af-4e51-91f9-94ed7427301b)

![b7fb07588da8e80cc2eb262bf1a3929](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/5ad8eef4-d3b1-4f97-a11c-2a5e3102a07b)

![ea69e7a897335c4683c6c386c376dda](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/2965e0c5-8ee2-4a5b-9ecc-961c85825c23)

![5d76e5e25a9d87a00bfa82657d0e5eb](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/ae589370-bc46-4aed-8cc9-ef1c638786dd)

![cf13da25828c2fe0ef642f05e284fc9](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/c0ade0dc-b8b5-4681-8fdf-fb4164a48231)

![ea3906c97323810c8fde372d5d2576f](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/f702cf58-ff17-494b-a56d-49930b4f1d17)

![e2efaf36692ab0f097018f362098115](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/4e6b9d7f-8500-4628-8263-d73b779cc12e)


**后台：**
![b1](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/48bc2f59-50f8-4c11-96e1-3e8c60106992)

![b2](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/8bc4dbec-9c74-4717-8810-52f42bd6eef2)

![b3](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/d384dcc5-0d87-4c24-ac95-c26cedf5e45b)

![b4](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/91acac0f-92d9-4e26-ae6e-5f4afb8cf400)

![b5](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/0a9ba3cd-fb62-4639-bcee-505c981061de)

![b6](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/b882ce39-cb30-4734-8a6c-0d9e04e5598a)

![b7](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/286870d9-e4a2-4c49-a394-6547c56c18aa)

![b8](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/b5fe9cc8-6553-4b20-b35c-a2ad4f0ae9c6)

![b9](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/d8bdcfdd-7c98-4cbd-a4ea-d7d60a080c5b)

![b10](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/ef32b410-f62f-472d-ad0e-f8eba68b699b)

![b11](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/70f42d6b-d6f0-4064-b52c-5c39884aa81e)

![b12](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/0da6acad-baab-479d-a6c5-70fbb08d01c0)

![b13](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/c6b8fa6c-85c4-4c94-b08c-a88eb5d08d35)

![b14](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/18f474a6-d355-45a8-ba59-2016924f4a7c)

![b15](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/cc111947-dc5d-4143-9bcb-d4de63170c76)

![b16](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/bdf444da-22bd-40e9-b2f8-78ad521021c1)
