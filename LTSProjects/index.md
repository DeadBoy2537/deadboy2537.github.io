## 欢迎来到落叶小镇Github页面

这是落叶小镇服务器用于备份资源所创建的页面
目前正在进行汉化补丁与菜单界面的工作
你可以从Releases中下载自动打包的资源
或使用Git工具将仓库内的文件下载下来

<a href="https://github.com/DeadBoy2537/LTSProjects" target="_blank">本仓库链接</a>

### 编辑&创建补丁

里面的文件使用一些专门的文本编辑器即可编辑（如电脑上的VS Code，手机上的Spck Editor）
以下是DeluxeMenus与ProtocolStringReplacer配置文件的编写示例（EliteMobs的直接修改源文件就行了）

```markdown
#DeluxeMenus

menu_title: 'example'
#菜单标题
open_command: example
#打开菜单的命令
update_interval: 1
#更新频率
size: 54
#菜单规格
args:
  example: -1
args_usage_message: "example"
items:
#设定菜单按钮
  example:
  #设定按钮名字
    material: example
    #设定按钮材质
    slot: 0
    #设定按钮所在的格子号
    display_name: 'example'
    #按钮显示的名字
    left_click_commands:
    - '[message] example'
    - '[player] example'
    #左键所执行的操作

#更多相关教程可查看https://deluxemenu.wiki.complexstudio.net/
```

```markdown
ProtocolStringReplacer

# 此替换配置文件的相关设定.
Options:
  # 是否开启本替换配置. 若为false则不会为这个文件处理. 若未定义, 默认为false.
  Enable: true
  # 本文件的优先级. 若有多个替换配置, 优先级高的最早替换. 默认为5.
  Priority: 5
  # 可选参数
  Version: '1.210805'
  # 可选参数
  Author: 'Rothes'
  # 匹配字符串的方式. 可选值:
  # 'Contain' : 只要包含就替换 (默认)
  # 'Equal' : 要求设置与原字符串完全匹配
  # 'Regex' : 使用Java正则表达式
  # 不区分大小写.
  Match-Type: 'Contain'
  # 筛选功能. 用于指定此文件替换字符串的条件.
  Filter:
    # 监听类型.
    # 指定替换何处的字符串. 默认为全部. 可选值:
    # Chat 替换聊天(chat|actionbar)信息文本
    # Sign 替换告示牌文本
    # Title 替换标题(title|subtitle)文本
    # Entity 替换实体名文本
    # Boss-Bar 替换Boss血量条文本
    # ItemStack 替换物品(物品名|Lore|书署名|书内容)文本
    # Window-Title 替换容器标题文本
    # ScoreBoard 替换计分板(标题|实体名称)
    # 不区分大小写.
    Listen-Types:
      - Chat
      - Window-Title
      - ItemStack
      - Sign
    # 针对计分板监听的特定过滤
    ScoreBoard:
      # 是否替换计分板标题. 默认为false.
      Replace-Title: false
      # 是否替换计分板中的实体名称. 默认为false.
      # 注: 对于玩家, 实体名称为玩家名称; 对于非玩家则为UUID.
      Replace-Entity-Name: false

# 替换的字符串列表.
# 左侧的key为原字符串 右侧的value为替换后的字符串.
# 替换模式优先度: Json > Common, 忽略文件优先度.
Replaces:
  # 常规文本替换模式.
  Common:
    '我的名字': '｛player_name｝'
    '一个命名牌': '我的命名牌'
    'mx': '是萌新'

  # Json 替换模式, 适合高级用户.
  # 不支持使用 Json 替换的监听类型有:
  # ItemStack(版本1.12及以上书内容除外)、版本 1.9.4 以下的 Sign,
  # 以及计分板中的实体名称、版本1.12及以下的计分板标题.
  Json:
    # 修改客户端上熔炉界面标题显示的名称.
    '{"translate":"container.furnace"}': '{"text":"恭喜您打开了一个熔炉! 666!"}'

#更多相关教程可查看https://rothes.gitbook.io/protocolstringreplacer
```

创建补丁只需在相应目录创建.yml即可（DeluxeMenus内的gui_menus，ProtocolStringReplacer内的Replacers）
需要注意DeluxeMenus需要更新config.yml才可正式启用菜单

```markdown
#例子

gui_menus:
#菜单文件目录
  main_menu:
  #菜单名字
  file: main_menu.yml
  #文件名字
```

### 使用补丁

本补丁适用于JAVA版SPIGOT服务器（理论上所有SPIGOT的派生版本都能使用，比如PAPERSPIGOT）

先安装对应的插件:

DeluxeMenus: <a href="https://www.spigotmc.org/resources/deluxemenus.11734/" target="_blank">下载地址</a>

EliteMobs: <a href="https://www.spigotmc.org/resources/⚔elitemobs⚔.40090/" target="_blank">下载地址</a>

ProtocolStringReplacer: <a href="https://www.spigotmc.org/resources/protocolstringreplacer.96573/" target="_blank">下载地址</a>

(建议 PlaceholderAPI: <a href="https://www.spigotmc.org/resources/placeholderapi.6245/" target="_blank">下载地址</a>)

然后将本仓库内的文件全部放在服务端的plugins文件夹内即可使用

Releases: <a href="https://github.com/DeadBoy2537/LTSProjects/releases/latest" target="_blank">下载地址</a>

### 交流群

落叶小镇服务器的讨论群，欢迎加入

QQ群聊: <a href="https://jq.qq.com/?_wv=1027&k=nC0T6Jua" target="_blank">加入</a>

Telegram群聊: <a href="https://t.me/+V4iovZgXfEp2c62B" target="_blank">加入</a>
