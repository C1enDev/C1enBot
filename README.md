# C1enBot
rt  
项目依赖 golang  
支持WS与Mirai,Go-CQHTTP,OICQ等交互
C1enDev-QQ群 454102262  
  [![miraigo](https://img.shields.io/badge/OneBot-MiraiGo-green.svg?style=social&logo=appveyor)](https://github.com/Mrs4s/MiraiGo)
  [![oicq](https://img.shields.io/badge/OneBot-OICQ-green.svg?style=social&logo=appveyor)](https://github.com/takayama-lily/oicq)
  [![mirai](https://img.shields.io/badge/OneBot-Mirai-green.svg?style=social&logo=appveyor)](https://github.com/mamoe/mirai)
  ## 功能
> 在编译时，以下功能除插件控制外，均可通过注释`main.go`中的相应`import`而物理禁用，减小插件体积。
> 通过插件控制，还可动态管理某个功能在某个群的打开/关闭。
> 插件的优先级为`import`的先后顺序
<details>
  <summary>插件控制</summary>

  - [x] /响应 (在发送的群/用户开始工作)

  - [x] /沉默 (在发送的群/用户停止工作)

  - [x] /全局响应 (在所有位置开始工作，无视单独的沉默)

  - [x] /全局沉默 (在所有本应沉默的位置停止工作，显式指定启用的位置不受影响)

  - [x] /启用 xxx (在发送的群/用户启用xxx)

  - [x] /禁用 xxx (在发送的群/用户禁用xxx)

  - [x] /全局启用 xxx

  - [x] /全局禁用 xxx

  - [x] /还原 xxx (在发送的群/用户还原xxx的开启状态到初始状态)

  - 注：当全局未配置或与默认相同时，状态取决于单独配置，后备为默认配置；当全局与默认不同时，状态取决于全局配置，单独配置失效。

  - [x] /改变默认启用状态 xxx

  - [x] /禁止 service qq1 qq2... (禁止 qqs 使用服务 service)

  - [x] /允许 service qq1 qq2... (重新允许 qqs 使用服务 service)

  - [x] /封禁 qq1 qq2... (禁止 qqs 使用全部服务)

  - [x] /解封 qq1 qq2... (允许 qqs 使用全部服务)

  - [x] /用法 xxx

  - [x] /服务列表

  - [x] /设置服务列表显示行数 xx

	默认值为9,该设置仅运行时有效,zbp重启后重置
  - [x] @Bot 插件冲突检测 (会在本群发送一条消息并在约 1s 后撤回以检测其它同类 bot 中已启用的插件并禁用)

</details>
<details>
  <summary>动态加载插件</summary>

  `import _ "github.com/FloatTech/ZeroBot-Plugin-Dynamic/dyloader"`

  - 本功能需要`cgo`，故已分离出主线。详见[ZeroBot-Plugin-Dynamic](https://github.com/FloatTech/ZeroBot-Plugin-Dynamic)

</details>

### *高优先级*
<details>
  <summary>聊天</summary>

  `import _ "github.com/C1enDev/C1enBot/plugin/chat"`

  - [x] [BOT名字]

  - [x] [戳一戳BOT]

  - [x] 空调开

  - [x] 空调关

  - [x] 群温度

  - [x] 设置温度[正整数]

</details>
<details>
  <summary>睡眠管理</summary>

  `import _ "github.com/C1enDev/C1enBot/plugin/sleep_manage"`

  - [x] 早安 | 晚安

</details>
<details>
  <summary>ATRI</summary>

  `import _ "github.com/C1enDev/C1enBot/plugin/atri"
  `
  - [x] 具体指令看 /用法 atri

  - 注：本插件基于 [ATRI](https://github.com/Kyomotoi/ATRI) ，为 Golang 移植版

</details>
<details>
  <summary>群管</summary>

  `import _ "github.com/C1enDev/C1enBot/plugin/manager"`

  - [x] 禁言[@xxx][分钟]

  - [x] 解除禁言[@xxx]

  - [x] 我要自闭 | 禅定 x [分钟 | 小时 | 天]

  - [x] 开启全员禁言

  - [x] 解除全员禁言

  - [x] 升为管理[@xxx]

  - [x] 取消管理[@xxx]

  - [x] 修改名片[@xxx][xxx]

  - [x] 修改头衔[@xxx][xxx]

  - [x] 申请头衔[xxx]

  - [x] 踢出群聊[@xxx]

  - [x] 退出群聊[群号]@Bot

  - [x] \*入群欢迎

  - [x] \*退群通知

  - [x] 设置欢迎语[欢迎~]  可选添加 [{at}] [{nickname}] [{avatar}] [{id}]

  - [x] 在[MM]月[dd]日的[hh]点[mm]分时(用[url])提醒大家[xxx]

  - [x] 在[MM]月[每周 | 周几]的[hh]点[mm]分时(用[url])提醒大家[xxx]

  - [x] 取消在[MM]月[dd]日的[hh]点[mm]分的提醒

  - [x] 取消在[MM]月[每周 | 周几]的[hh]点[mm]分的提醒

  - [x] 在"cron"时(用[url])提醒大家[xxx]

  - [x] 取消在"cron"的提醒

  - [x] 列出所有提醒

  - [x] 翻牌

  - [x] [开启 | 关闭]入群验证

  - [x] [开启 | 关闭]gist加群自动审批

  - [x] 对信息回复:[设置 | 取消]精华

  - [x] 取消精华 [信息ID]

  - [x] /精华列表

  - [ ] 同意好友请求

  - [x] 对信息回复: 撤回

  - [ ] 警告[@xxx]

  - 注：使用gist加群自动审批，请在群介绍添加以下说明，同时开启`需要回答问题并由管理员审核`：加群请在github新建一个gist，其文件名为本群群号的字符串的md5(小写)，内容为一行，是当前unix时间戳(10分钟内有效)。然后请将您的用户名和gist哈希(小写)按照username/gisthash的格式填写到回答即可。

  - 设置欢迎语可选添加参数说明：{at}可在发送时艾特被欢迎者 {nickname}是被欢迎者名字 {avatar}是被欢迎者头像 {uid}是被欢迎者QQ号 {gid}是当前群群号 {groupname} 是当前群群名

</details>
<details>
  <summary>词典匹配回复</summary>

  `import _ "github.com/C1enDev/C1enBot/plugin/thesaurus"`

  - [x] 切换[kimo|傲娇|可爱]词库
  - [x] 设置词库触发概率0.x (0<x<9)

</details>
<details>
  <summary>定时指令触发器</summary>

  `import _ "github.com/FloatTech/zbputils/job"`

  - 注意：触发器具有限速，每 2s 仅允许最多一次触发

  - [x] 记录以"完全匹配关键词"触发的(代表我执行的)指令

  - [x] 取消以"完全匹配关键词"触发的(代表我执行的)指令

  - [x] 记录在"cron"触发的(别名xxx的)指令

  - [x] 取消在"cron"触发的指令

  - [x] 查看所有触发指令

  - [x] 查看在"cron"触发的指令

  - [x] 查看以"完全匹配关键词"触发的(代表我执行的)指令

  - [x] 注入指令结果：任意指令

  - [x] 执行指令：任意指令

  - 注：任意指令可以使用形如`?::参数1提示语::1!`,`?::参数2提示语::2!`,`?::?可选参数3提示语，不回答将填入空值::3!`,`!::从url获取的参数::4!`,`!::?可选的从url获取的参数，出错将填入空值::5!`的未定参数，在注入时一一匹配
