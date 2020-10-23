# 订阅号H5—语音祝福贺卡活动项目

## 步骤一：准备小程序及云开发环境
1.选择已有的小程序或者新建小程序，获得小程序的appid

2.将本项目下载后解压，使用小程序开发者工具([开发者版-最新版本1.03.2010212](https://developers.weixin.qq.com/miniprogram/dev/devtools/nightly.html)）导入项目，如图所示。appid处填写上一步小程序的appid。
![](readmeres/01.png)

3.小程序开发者工具打开后文件目录如下：
![](readmeres/02.png)

4.打开小程序开发者工具-云开发控制台，在设置中创建一个新的环境，专用于项目的放置，新建时选择按量计费环境。
![](readmeres/03.png)
![](readmeres/04.png)

5.创建成功后，在云开发控制台-设置-扩展功能中开通静态托管服务，如下图所示。
![](readmeres/05.png)

6.等待开通完毕后，在云开发控制台顶部栏-更多中选择【静态网站】，进入静态网站控制页面
![](readmeres/06.png)

## 步骤二：更改项目关键信息

1.从云开发控制台设置中，获取新创建的云开发环境ID，保存。
![](readmeres/07.png)

2.打开项目目录下/webviews/index.html文件，将第10行cloudenvid后更新为自己的云开发环境ID
![](readmeres/08.png)

## 步骤三：上传部署项目资源

1.打开云开发控制台-静态网站管理页面，将项目目录下的/webviews内所有文件上传，最终如下图所示。
![](readmeres/09.png)

2.打开云开发控制台-存储管理页面，将/cloudasset里的内容资源，上传至云存储根目录中，最终如下图所示。
![](readmeres/10.png)

3.上传资源后，进入到image文件夹中，保存所有图片的http地址，一共4张，如图所示。（注意：要截取http地址?之前的内容，get参数之外不需要）
![](readmeres/11.png)

3.打开云开发控制台-数据库管理页面，创建集合user、token、image，其中image集合中，创建id为”SI“的文档，并在文档中设定img项目，填写上一步中保存的4个图片http地址，如图所示
![](readmeres/12.png)
![](readmeres/13.png)

## 步骤四：设置公众号，配置云函数

1.打开公众号的管理后台，找到公众号设置-功能设置-JS接口安全域名，点击设置，下载弹出框中的MP_verify验证文件，将其上传至云开发静态网站根目录，如下图所示。
![](readmeres/14.png)
![](readmeres/15.png)
![](readmeres/16.png)

2.打开云开发控制台-静态网站管理页，将域名信息下的域名保存，并设置到公众号管理后台中。
![](readmeres/17.png)
![](readmeres/18.png)
![](readmeres/19.png)

3.打开公众号的管理后台，基本配置-公众号开发者信息，将appid和appssecret保存（如果之前已经生成并正在使用，请用之前的，不要重置导致现网出问题）
![](readmeres/20.png)

4.打开项目目录/cloudfunction/init/config.json以及/cloudfunction/token/config.json，将appid和secret分别更新为上一步保存的信息。
![](readmeres/21.png)

5.在小程序开发者工具中，项目目录/cloudfunctions下，右键选择环境为步骤一新创建的环境（如果没有则重启项目再试）
![](readmeres/22.png)

6.将项目目录cloudfunctions文件夹下三个云函数，右键创建上传：云端部署依赖，如图所示
![](readmeres/23.png)

## 步骤五：配置匿名登录

1.访问[腾讯云官网](https://console.cloud.tencent.com/tcb),登录时使用微信公众账号授权登录，授权当前小程序，进入控制台。
![](readmeres/24.png)

2.选择步骤一新创建的云开发环境，进入环境-登录授权，开启匿名登录。
![](readmeres/25.png)

## 步骤六：访问项目

1.微信客户端打开静态网站域名后，即可访问应用（注意，暂不支持PC端微信浏览器，请直接使用手机端打开。

2.本项目只能自己体验，不可以对外用于自身活动。

3.在自己开发H5项目使用静态网站托管时，建议绑定自己的域名。

## 项目声明

本项目源自真实项目案例，开发耗时约1天。项目中前端源码大部分乃仓促开发，架构并不具有标杆意义，也并不是为了示例使用，仅用于成果展示，还请各位开发者理解。

如果你对本项目的部署过程有任何问题，欢迎提出issue！
