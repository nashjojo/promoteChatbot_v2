# promoteChatbot_v2
基于rasa的金融推销机器人(第二版)



**版本更新**<br>
舍弃了chatterbot框架，使用rasa_nlu和rasa_core训练模型

**场景**<br>
电话里的信用卡推销

**依赖库的安装**<br>
pip install rasa_core==0.9.0<br>
(安装ta也会自动安装rasa_nlu)

**开发环境**<br>
linux<br>
python3.6

## 使用方法
python bot.py run

## 效果：
### 基本信息的问答
usr: 你们是什么银行的<br>
bot: 哦，我们这边是光大银行的信用卡。<br>
usr: 办理需要钱吗<br>
bot: 办理全程是不收取任何费用的。<br>
usr: 你叫什么<br>
bot: 我姓李，木子李，叫我小李就行了。标准的90后呢！<br>
usr: 你们公司地址在哪<br>
bot: 我们公司的地址在北京市西城区。<br>

### 基于槽填充的多轮对话
usr: 那行，帮我办一张吧<br>
bot: 您想办多长年限的卡？我们有十年、五年、两年的<br>
usr: 两年的<br>
bot: 好，请稍等<br>
bot: 您想办多大额度的卡？我们有一千万、一百万、十万的<br>
usr: 十万的<br>
bot: 好，请稍等<br>
bot: 您好，已经帮您办好了，额度十万，年限两年，感谢您的支持。<br>

### 推销话术
bot: 您好，这里是光大银行信用卡合作商，来电是想邀请您办理光大银行信用卡<br>
usr: 您好<br>
bot: 您好! 我是小李，请问您办过信用卡吗？<br>
usr: 办过<br>
bot: 嗯嗯，办过的话也可以考虑下的，每家银行信用卡的活动、服务都不一样的，多一张信用卡也是多一笔备用金在手边嘛。<br>
bot: 我们的优惠活动种类很多哦，譬如10元观影、美食、洗车，每年3次航空延误险，携程酒店满500减100等礼遇。<br>
bot: 很不错的卡，您可以考虑办一下哦<br>
---<br>
usr: 没办过<br>
bot: 没有办过没关系呢，办信用卡好处多多哦，能免息透支消费，享受信用卡自带的权益与优惠活动呢<br>
bot: 我们这卡不仅免年费，还有很多活动，譬如10元观影、美食、洗车，每年3次航空延误险等礼遇，福利非常多哦<br>
bot: 您可以办一张试试看哦<br>

### 未识别的意图
usr: 北冥有鱼，其名为鲲<br>
bot: 您能再说一遍吗，我没听清<br>
usr: 身体发肤，受之父母<br>
bot: 不好意思哦，刚没听清，您可以再说一遍吗？<br>
usr: 生活不只有眼前的苟且，还有诗和远方<br>
bot: 麻烦您再说一下，我这边信号不是很好。<br>


## data文件夹缺少的词向量文件
链接：https://pan.baidu.com/s/1vy-YD5FHRiJyRsJM5lhyfA 
提取码：76la 


## 训练方法
### 训练NLU模型
sh train.sh
### 训练Core模型
python bot.py train-dialogue
