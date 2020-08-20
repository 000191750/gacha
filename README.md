# gacha
适用于[HoshinoBot](https://github.com/Ice-Cirno/HoshinoBot)的可以自动更新的全限定卡池。包含27个限定卡池, 国服日服台服卡池, 以及混合卡池. 仅测试了v2而没有对v1进行测试. 开发时使用的是HoshinoBot V1的第一个版本, 在后续版本中咖啡佬又做出了一些修改, 如果您使用后续版本而出现问题, 请提交issue.

想法来自[HoshinoBot](https://github.com/Ice-Cirno/HoshinoBot)的一个[Pull Request（#113）](https://github.com/Ice-Cirno/HoshinoBot/pull/113), 但是从其源站获取的卡池是数字ID格式, 于是利用`_pcr_data.py`的数据将其转变为第一个中文名称, 如果遇到角色信息缺失的情况会忽略该角色, 并在控制台显示warning, 请注意及时更新, 其中ID为1912的角色千炸里脊资源站未找到. 

本项目GitHub地址：https://github.com/pcrbot/gacha

Gitee地址：https://gitee.com/varmixer/gacha

卡池数据更新来源: https://api.redive.lolikon.icu/gacha/default_gacha.json

## 指令与功能
* 更新卡池: 更新卡池, 仅限超级管理员, 可群聊可私聊, 无需@, 无需开启服务. 
* 选择卡池: 与原指令相同, 请根据提示操作. 
* (自动)自动更新:每日16时3分自动更新卡池. 
  

其余指令与原先抽卡系统一致, 请自动通过机器人帮助查看


## 开始使用
### 如果您已经在使用全限定卡池
1. 克隆本项目, 复制`update.py`文件到HoshinoBot的抽卡模块目录下, 例如`~/HoshinoBot/hoshino/modules/priconne/gacha/`, 请根据实际情况修改路径.
2. 修改`gacha/`目录下的`__init__.py`文件, 在任意位置添加以下内容(推荐在代码开头部分)
    ```
    from .update import *
    ```
3. 发送命令“更新卡池”来进行一次强制更新, 此更新仅修改卡池配置文件`config.json`中的四个对应卡池而不会修改其他限定池内容.(但是排版会被格式化)
### 如果您未使用过全限定卡池
1. 切换至PCR模块目录下(请自行根据实际情况修改路径):
   ```
   cd ~/HoshinoBot/hoshino/modules/priconne
   ```
2. 移除原有的`gacha/`目录, 建议自行备份以防止出现问题:
   ```
   rm gacha/ -r 
   ```
3. 克隆本项目:
   ```
   git clone https://github.com/pcrbot/gacha.git
   ```
4. 重新启动机器人

## 其他
1. 自动更新出现错误或者是发现新卡池而完成自动更新, 会通知SUPERUSER列表的第一名用户, 如果您不想接受到通知, 可以将`update.py`第10行改为:
    ```
    NOTICE = 0
    ```
2. 更新卡池后原卡池会被备份至`backup.json`, 如出现错误可由此恢复. 
   
3.安装后如果出现找不到config.json，请将update.py中的路径改为绝对路径，如：
    ```
    /home/ubuntu/HoshinoBot/hoshino/modules/priconne/gacha/config.json
    ```
    
## 更新日志

### 2020/8/18
* 解决了使用Hoshino后续版本时, 繁体指令提示冲突的问题
* 解决了看看UP时出现USE_CQPRO不存在的问题(#1)

## 本模块原README
本模块基于 0皆无0（NGA uid=60429400）dalao的[PCR姬器人：可可萝·Android](https://bbs.nga.cn/read.php?tid=18434108)，移植至nonebot框架而成。

重构 by IceCoffee

源代码的使用已获原作者授权。
