## 脚本功能：

1、通过Github Action自动定时运行[checkin.py](https://github.com/chh-yu/closet/blob/main/main.py)脚本。

2、通过cookies自动登录（[https://glados.rocks/console/checkin](https://glados.rocks/console/checkin))，脚本会自动进行checkin，可实现多个账号签到。

3、然后通过“pushplus”（[https://www.pushplus.plus/](https://www.pushplus.plus/))，自动发通知到微信上。



## 使用方法：

1. 先“Fork”[仓库](https://github.com/chh-yu/closet)。（不需要修改任何文件！）

2. 登录GLaDOS后获取cookies。（简单获取方法：浏览器快捷键F12，打开调试窗口，点击“network(网络)”获取）
![捕获](https://user-images.githubusercontent.com/89286395/213177136-53e16eea-c1de-4390-bdda-07faa002df27.PNG)
![IMG_20230118_204916](https://user-images.githubusercontent.com/89286395/213177186-8628fd0f-aaa5-4a5d-adc9-4ad107874ebd.jpg)
选中cookie，右键复制值，然后去仓库粘贴到COOKIES下即可。

3. 为项目创建Personal access tokens


4. 在自己的仓库`Settings`里创建3个`Secrets`，分别是：（不开启通知，只需要创建COOKIES即可）

   - COOKIES（**必填**）
   - SERVE（推送开关，off关闭通知，填on的话，会同时开启cookie失效通知和签到成功通知）
   - SCKEY（填写pushplus的token，不开启则不用填）
   - GHTOKEN (填写Personal access tokens)

5. 以上设置完毕后，每天北京时间凌晨3点左右会自动触发，并会执行自动checkin，如果开启pushplus，会在3点15分左右自动发通知到微信上。

### 额外说明：有多个glados账号时，在变量COOKIES里使用`&&`分割不同的账号的cookie，不需要空格换行等。

## 签到失败
1. 建议首先尝试更新COOKIES密钥

## 更新日志
### 2023.8.1
修复接口更新导致的签到失败问题，用户需更新仓库设置中的**COOKIES**密钥