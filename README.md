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
| 前端界面 | 默认深色背景风格 | 支持多种风格替换，适配ChatGPT-Next-Web风格 |
| 使用模式 | 只能免费分享给朋友使用，或要求使用者自备API_KEY | 用户可以通过微信支付、支付宝在线购买，或通过淘宝或发卡站购买储值卡使用 |
| 角色和场景 | 支持预设问题，不支持定义角色 | 支持定义角色和针对各场景的预设问题 |
| 画图功能 | 新版已支持画图功能 | 支持OpenAI画图、MJ画图、SD画图功能 |
| 改图识图 | 不支持 | 支持多种改图、识图模型 |
| 语音对话 | 不支持 | 支持语音直接对话，用户可发送语音，AI自动回复并朗读，可选择多种朗读模型和发音人 |
| 切换模型 | 只能设置单一模型 | 支持多种模型自选，费用可以单独设定 |
| 本地知识库 | 不支持 | 支持在后台上传文档，建立专属知识库模型 |
| 联网模型 | 不支持 | 支持将任意模型联网使用，用来自搜索引擎的数据作为上下文提问 |
| 功能扩展 | 免费使用，用户根据自己需要改进代码，开源版未来没有架构层面修改的计划 | 一次购买永久免费升级，用户可以提需求，商业版会不断改进并持续更新 |

**本项目目前已实现的功能如下：**

1. 无需注册会员，微信扫码登录，独有技术，无需用户授权，丝滑体验。手机或安卓浏览器可以使用微信小程序一键登录。也可以设置注册账号使用，使用邮箱、密码登录。并且支持通过第三方会员系统单点登录。
2. 每个用户可以设置成免费体验若干条数和天数，每天登录、邀请好友注册送查询次数，对话按次收费。不同的模型可以设置不同的价格。
3. 后台可以设置API_KEY列表，全局+出错时自动轮询，保证用户每次查询都能返回结果。每种模型单独设置API_KEY，支持第三方GPT4的API。
4. 支持微信支付官方接口（JSAPI模式）和支付宝当面付官方接口，也提供易支付第三方支付安装包。
5. 支持批量生成充值卡，可设置查询次数和有效期，方便没有在线支付接口的朋友挂到发卡站、淘宝店、微店、扫站长微信二维码转账。
6. 进一步优化接口响应速度，实现秒级回复，详细错误提示，超时处理，并支持查询和继续历史对话。
7. 支持切换模型，支持切换角色和场景，支持OpenAI画图、MidJourney画图、StableDiffusion画图等功能。模型、角色、场景在后台都可以自定义。
8. 支持关键词过滤，支持百度内容审核，问题和答案都可以进行过滤和审核。
9. 支持在后台修改API接口的反代地址及代理地址，网站可放在国内运营。支持自定义AI身份，隐藏openai和chatgpt有关信息。
10. 支持用户自行开发自定义插件，升级不受影响。内部论坛已提供用户付费购买的插件，如分销插件、其他风格的UI、专业的画图、联网搜素插件等。
11. 支持所有主流国内外大模型官方接口（具体可参考截图），为付费用户免费提供微信服务号登陆接口、小程序登陆接口、StableDiffusion画图接口、微软TTS文字转语音接口、海外免费OpenAI/Bard/SD画图接口。
12. 支持将任意模型联网使用，用来自搜索引擎的数据作为上下文提问。
13. 支持本地知识库功能，采用OpenAI官方接口，可以在后台上传文档创建assistant，用户在前台可以调用相关模型进行对话。
14. 支持语音对话功能，后台支持配置语音识别接口及多个文字转语音接口。
15. 支持图床功能，可将网站上涉及的图片统一保存到图床服务器上，加速用户访问，节省服务器流量。
16. 支持网站公告功能，支持后台一键更新到最新版本。

**本项目目前已支持的模型列表：**

*国外模型：*
1. OpenAI官方：gpt-3.5-turbo-0125、gpt-3.5-turbo-instruct（擅长执行具体指令，无上下文）、gpt-4-turbo-preview（最具性价比）、gpt-4-0125-preview等、dall-e-3（画图）、gpt-4-vision-preview（识图）、dall-e-2（改图）；
2. 由于使用官方APIKEY成本和门槛都很高，大多数用户都是购买第三方接口的额度来调用gpt-4等模型，并且第三方接口可以支持某些官方没有的模型，如gpt-4-all，gpts上的应用gpt-4-gizmo-xxx等；
3. Claude官方：claude-3-opus-20240229、claude-3-sonnet-20240229、claude-2.1、claude-2.0、claude-instant-1.2（Claude的所有模型均包含文本对话及识图能力）；
4. 谷歌Bard：gemini-pro、gemini-pro-vision（识图）；

*国内模型：*
1. 文心千帆：ERNIE-Bot-turbo、ERNIE-Bot、ERNIE-Bot-4、BLOOMZ-7B、CodeLlama-7b-Instruct、Stable-Diffusion-XL（画图）；
2. 通义千问：qwen-turbo、qwen-vl-plus（识图）；
3. 清华智谱：glm-4、glm-3-turbo、glm-4v（识图）、cogview-3（画图）；
4. 360智脑：360GPT_S2_V9；
5. 讯飞星火：大模型1.5、2.0、3.0、3.5；
6. 百川智能：Baichuan2-Turbo、Baichuan2-Turbo-192k；
7. 腾讯混元：ChatStd、ChatPro；
8. 阿里StableDiffusion：stable-diffusion-v1.5（画图）、stable-diffusion-x1（画图）；
9. 月之暗面：moonshot-v1-8k、moonshot-v1-32k、moonshot-v1-128k；
10. LinkAI：这是一个第三方知识库网站，请将app_code写到模型参数后面；
11. 本地知识库：模型参数值填写知识库ID即可，如：asst_eduOuMQnER4nFKyDdCJo7Wur

**部署要求：**
1. 运行本项目必须要有自己的服务器，虚拟主机+Mysql数据库也可以，我不提供服务器或虚拟主机服务，请各位自行购买。
2. 最好是在海外服务器上部署本项目，比如腾讯云东京轻量，领完优惠券每个月只要20多元，国内服务器访问部分海外接口需要反代。
3. 对CPU没有太高的要求，内存最好不小于1GB，硬盘容量20GB也能用，后期随着问答日志的增加可再考虑扩容。
4. 本项目对性能和带宽消耗极低，对于几百个用户的规模各云主机运营商最低的配置就够用。
5. 内部论坛上已有详细的安装流程和配置文档，部署起来很简单，小白用户也能自己搞定。
6. 使用自己的服务号登录的话需要有公司，注册微信、支付宝官方支付接口也需要。没有公司的可以使用我提供的公共服务号，并使用微店、淘宝等出售充值卡。也可以使用易支付等第三方支付平台收款，稳定性差一些。

**其他说明：**
1. 当前价格999元，一次购买终身免费使用和升级。
2. 商业版包含全部源码，未作任何加密或混淆，支持远程自动更新。网站更新和登录需要授权并绑定域名，提供顶级域名即可，二级域名可随时更换。
3. 每个购买者可加入内部论坛学习部署和安装教程，小白也能轻松搞定。
4. 源码仅限购买者使用，请不要免费分享或转卖本项目源码，否则将永久被拉黑。君子协定，自觉遵守，唯有人品，可立一生。
5. 测试网址：https://chatpro.ipfei.com
6. 购买链接：https://item.taobao.com/item.htm?id=713331539595
7. 由于程序代码未做加密，一旦售出无法退货，请您购买前考虑清楚是否真的需要。
8. 现阶段想单纯靠网站吸引用户已经很难，除非您之前已有粉丝或用户。
9. 本项目非常适合公司内部使用，可以学习、比较各模型差异，提高生产力等。
10. 代码没用任何框架，没用任何composer依赖库，全是原生PHP，因此非常容易修改和二次开发。
11. 购买本项目可以快速入门和了解AI，内部论坛上有我和其他用户写的很多相关知识、教程和免费资源。
12. 已购用户如果愿意可以申请加入用户群，大家多多交流，多个朋友多条路。AI是通往未来的必经之路，早日进入圈子不会迷路。


**版本发布日志：**

最新版本为v6.0.2410，版本发布日期请点击这里查看：https://bbs.ipfei.cn/forum.php?mod=forumdisplay&fid=37

**有购买意愿的朋友也可以加微信好友咨询，请备注下购买商业版，谢谢**

![image](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/67256e5b-32b9-42d8-8a50-21ee4865e2f3)


**前台界面截图如下：**

**PC端：**

![1](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/68376963-ff12-4065-bb9b-3e2ac1a42fda)

![2](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/15a2b7bf-7d8e-4831-b480-1c1ea07232d0)

![3](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/a3a31600-48a1-42a9-8b15-6c2b34cfc234)

![4](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/f14730f9-3690-4efc-8499-0bef6e4eacb1)

![5](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/1abe4956-54a8-401d-a841-b44169b5b84d)

![6](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/821a6043-06e8-4bab-8dd7-b3fa34572dd7)

![7](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/eb5ba757-93b3-4356-a87d-3a4d92946979)

![8](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/4773c0b8-7abe-4d6a-bd3c-b62b0437e0f5)

![9](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/b8558674-53b3-489b-9254-3e245d0e7cd1)

![10](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/51217178-d218-4984-ba50-59925725a08b)

![11](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/2c7502c3-8358-4409-a7ce-892e8ac24df4)

![12](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/d2e9350f-88a8-409f-98ef-2bcd9041571e)

![13](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/fd481db2-9dbf-46fa-8fe6-6f7b119ca5b1)

![14](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/c18eee32-843a-4a2d-b2b5-982be78df885)

![15](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/88a02ec1-9a71-43c3-a0a8-aafdd6b0e219)

![16](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/0d95149b-6632-4504-bae4-3ce613ecbc71)

![17](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/b591b57f-05f9-4933-a9db-70745fa284d8)

![18](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/5fc2a998-b34e-4b94-b6d3-1a279eeb6896)

![19](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/2a939538-82af-4061-880c-a1eaaa39a28a)

![20](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/306f3369-bd83-40b7-afaf-24d394f81d45)

![21](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/50d45269-db4e-41d8-8c1a-0470cf823694)

![22](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/d3191172-d1f4-49b8-bb43-c653bad56958)

![23](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/98ee3e13-bf09-4e1e-a1b9-b15c093d05c7)

![24](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/185b26e0-8765-4bcc-bc49-e240aa1c5601)


**手机端：**

![1](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/057a992e-8786-4c3b-aeae-30453bcc7821)

![2](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/8ef22176-6fc9-41fb-9234-9393cacefb70)

![3](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/8e741569-3b59-4431-a8e7-87e69fe64919)

![4](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/8ae0ff67-ac21-4f04-9f71-7d4bb9b2b5f9)

![5](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/0594aa9b-537e-45ab-9b8f-871d887c95f4)

![6](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/431ca7e7-79e0-4534-95a4-3e1aeb09c0e7)

![7](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/97cbfdf9-7a78-486d-b830-bbffff88caad)

![8](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/9c29caeb-fc1c-4490-9f2d-04712874c7b5)

![9](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/7329575f-5490-48a9-9f82-18e14a349efd)

![10](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/476e2b7c-da93-44f5-b88d-a80e0f03dff0)

![11](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/5d3d9a78-a809-4673-8bbc-fba0443122a9)

![12](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/650c2e3e-8de4-4785-9411-8166039fd726)

![13](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/8aef66fa-38da-4077-ac47-817e5c4c1a00)

![14](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/1371c886-67c2-4292-832c-3ea0ea51442f)


**后台：**

![1](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/36e3b4a0-b5c7-48dc-af02-5596ff044d11)

![2](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/456ea375-e2d7-488c-b01c-54c7169c1aca)

![3](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/e86658b0-e471-4c30-95ca-9095095a637a)

![4](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/63471412-422a-4a67-aeb8-e36b0306bcbf)

![5](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/255d50a3-7976-4cde-af62-9a8db2ec4acb)

![7](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/dc62440c-e073-48a8-bb1d-8e9f36153062)

![8](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/f4b05538-a3a5-47d8-9b6b-bfd1168676ad)

![9](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/36a35d8a-a4fd-416a-abe8-f06c4e384e0f)

![10](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/0751b8b6-1875-4a85-a966-bbece7823ce7)

![11](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/59e1512c-1c0c-4f3d-85cd-2227aefcb73f)

![12](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/18360aa9-f86a-460d-86cc-5e39fb66e38e)

![13](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/e9bdd4a2-a94c-411d-bea8-a1b4dfb2b6cc)

![14](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/666006c0-ca67-4c99-8b40-fd66fd14373b)

![15](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/39eafc0d-0d4f-4994-b86d-2723442b26a5)

![16](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/30647b6d-33fb-43ee-be3d-3f4d3666a0a7)

![17](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/d5852df0-65e4-40c7-a22b-b57b01d24786)

![18](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/f39cbbfd-d6f2-4a3b-8a98-3d78776e7c29)


![b16](https://github.com/dirk1983/chatgpt_commercial/assets/5563148/bdf444da-22bd-40e9-b2f8-78ad521021c1)
