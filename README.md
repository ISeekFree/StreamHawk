# 流鹰(StreamHawk)

#### 软件定义：全平台弹幕采集助手！

#### 软件下载：[https://iseekfree.com/](https://iseekfree.com/)

#### 小白教程：[https://space.bilibili.com/3546817335658933](https://www.bilibili.com/video/BV1Kb31znEKC/?spm_id_from=333.1387.homepage.video_card.click&vd_source=be2dd15e00c3435df9861a8cb59b48aa) （参见《10分钟！3步搞定AI互动数字人直播间，开播零门槛！》）

#### 弹幕集成：参见“弹幕推送”设置部分，通过API与您的系统深度集成！
#### 注意事项：在开启弹幕采集过程中，切勿开启“VPN”(如果开启了VPN，请关闭VPN并重启“流鹰”软件；

### 一、流鹰简介

#### 1、🎯 产品定位
「产品定义」：一键汇聚，自家精彩！—— 您的专属弹幕智能助手!
「使用场景」：在直播电商、游戏互动、数字人驱动、娱乐媒体等直播环节中，实时弹幕是连接观众与品牌的核心纽带！我们推出Mac、Windows端全平台弹幕采集软件，专为注重数据合规与高效互动的您量身定制！

#### 2、🔥 核心功能
「一键抓取」：将陆续支持主流直播平台（如抖音、快手、B站、淘宝、Tiktok、视频号、小红书、京东、拼多多等），自动聚合弹幕至统一界面，告别繁琐切换。
「系统集成」：弹幕实时推送至您所设置的服务器，高效稳定！

#### 3、⚖️ 合规底线
「自家数据」保护模式：仅支持绑定您自有账号或授权直播间的弹幕采集，从源头杜绝数据盗用风险，合法合规更安心。
「隐私呼吁」只聚自家烟火，不摘他人星辰

#### 4、⚡ 为什么选择我们？
「极简操作」：一键启动，自动同步，即使非技术背景也能轻松上手。
「低延迟」：弹幕实时采集，秒级推送！
「隐私承诺」：弹幕数据仅限采集流转，本地不存储，不上传不共享，您的数据您绝对自主。

### 二、弹幕推送

**特别提醒：如果想排查弹幕推送到您的服务器或软件问题，可按：ctrl + shift + i 打开开发者工具**

**推送格式：‘流鹰’会将采集好的弹幕推送至您的服务器(您需要按以下格式接收推送请求和响应请求):**

```HTML
curl https://${your_servername}/${your_api_path} \
-H 'Content-Type: application/json' \
-d '{
    "platform": "douyin",
    "messages": [
      {
        "type":"text",
        "userName":"饭饭",
        "userId":"xxx",
        "content":"This streamer is awesome!"
      }
    ]
}'
```

同时请保持以下格式的响应(JSON)
```HTML
{
  "code":0,//0成功，非0失败
  "msg":'',//用于推送弹幕的错误提示
}
```
platform支持列表:
<table style="border-collapse: collapse;">
  <thead>
    <tr>
      <th style="border: 1px solid #ccc; padding: 8px;">平台标识</th>
      <th style="border: 1px solid #ccc; padding: 8px;">平台名称</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">douyin</td>
      <td style="border: 1px solid #ccc; padding: 8px;">抖音</td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">kuaishou</td>
      <td style="border: 1px solid #ccc; padding: 8px;">快手</td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">wemedia</td>
      <td style="border: 1px solid #ccc; padding: 8px;">视频号</td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">bilibili</td>
      <td style="border: 1px solid #ccc; padding: 8px;">B站</td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">tiktok</td>
      <td style="border: 1px solid #ccc; padding: 8px;">TikTok</td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">rednote</td>
      <td style="border: 1px solid #ccc; padding: 8px;">小红书</td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">taobao</td>
      <td style="border: 1px solid #ccc; padding: 8px;">淘宝</td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">jd</td>
      <td style="border: 1px solid #ccc; padding: 8px;">京东</td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">pdd</td>
      <td style="border: 1px solid #ccc; padding: 8px;">拼多多</td>
    </tr>
  </tbody>
</table>

弹幕类型支持列表：
<table style="border-collapse: collapse;">
  <thead>
    <tr>
      <th style="border: 1px solid #ccc; padding: 8px;">类型标识</th>
      <th style="border: 1px solid #ccc; padding: 8px;">类型名称</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">text</td>
      <td style="border: 1px solid #ccc; padding: 8px;">文本消息</td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">gift</td>
      <td style="border: 1px solid #ccc; padding: 8px;">送礼消息</td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">entrance</td>
      <td style="border: 1px solid #ccc; padding: 8px;">进场消息</td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">like</td>
      <td style="border: 1px solid #ccc; padding: 8px;">点赞消息</td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">streamer</td>
      <td style="border: 1px solid #ccc; padding: 8px;">主播讲话(在弹幕采集页，需手动开启语音识别)</td>
    </tr>
  </tbody>
</table>


### 三、房间创建

#### 0、弹幕地址

<table style="border-collapse: collapse;">
  <thead>
    <tr>
      <th style="border: 1px solid #ccc; padding: 8px;">弹幕平台</th>
      <th style="border: 1px solid #ccc; padding: 8px;">地址格式</th>
      <th style="border: 1px solid #ccc; padding: 8px;">备注说明</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">抖音</td>
      <td style="border: 1px solid #ccc; padding: 8px;">地址格式：https://live.douying.com/${roomId}</td>
      <td style="border: 1px solid #ccc; padding: 8px;">1、在PC中打开https://douyin.com ，进入个人直播页；<br/>2、进入直播页即可看到对应直播间地址(?后参数不需要)；<br/><span style="color:red;">3、弹幕采集过程中，记得登陆任意抖音账号(若有划动验证条需要您手动验证)</span></td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">快手</td>
      <td style="border: 1px solid #ccc; padding: 8px;">地址格式：https://live.kuaishou.com/u/${userId}</td>
      <td style="border: 1px solid #ccc; padding: 8px;">1、在PC中打开https://kuaishou.com ，进入自己的主页；<br/>2、在浏览器地址中即可看到当前用户userId，拼接直播地址即可；<br/><span style="color:red;">3、弹幕采集过程中，记得登陆任意快手账号(若有划动验证条需要您手动验证)</span></td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">B站</td>
      <td style="border: 1px solid #ccc; padding: 8px;">地址格式：https://live.bilibili.com/${roomId}</td>
      <td style="border: 1px solid #ccc; padding: 8px;">1、在PC中打开https://bilibili.com ；<br/>2、进入自己的直播间，获取直播地址(?后参数不需要)；<br/><span style="color:red;">3、弹幕采集过程中，务必登陆任意B站账号(若有划动验证条需要您手动验证,这样才能拿到弹幕用户昵称)；</span></td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">TikTok</td>
      <td style="border: 1px solid #ccc; padding: 8px;">地址格式：https://www.tiktok.com/@${profileId}/live</td>
      <td style="border: 1px solid #ccc; padding: 8px;">1、在浏览器中打开https://tiktok.com；<br/>2、进入自己的直播间，获取直播地址；<br/><span style="color:red;">3、弹幕采集过程中，务必登陆任意TikTok账号(若有划动验证条需要您手动验证)；</span></td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">视频号</td>
      <td style="border: 1px solid #ccc; padding: 8px;">地址格式：使用官方默认</td>
      <td style="border: 1px solid #ccc; padding: 8px;">1、视频号直播间无需用户单独创建，使用软件默认添加的直播间即可；<br/><span style="color:red;">2、扫码登陆后点击'进入直播间'即可；</span><br/>3、特别注意：目前视频号只采集文本、Emoji弹幕、进入房间消息；            <br/></td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">小红书</td>
      <td style="border: 1px solid #ccc; padding: 8px;"></td>
      <td style="border: 1px solid #ccc; padding: 8px;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">淘宝</td>
      <td style="border: 1px solid #ccc; padding: 8px;"></td>
      <td style="border: 1px solid #ccc; padding: 8px;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">京东</td>
      <td style="border: 1px solid #ccc; padding: 8px;"></td>
      <td style="border: 1px solid #ccc; padding: 8px;"></td>
    </tr>
    <tr>
      <td style="border: 1px solid #ccc; padding: 8px;">拼多多</td>
      <td style="border: 1px solid #ccc; padding: 8px;"></td>
      <td style="border: 1px solid #ccc; padding: 8px;"></td>
    </tr>
  </tbody>
</table>

#### 1、创建弹幕间
<img src="https://cdn.iseekfree.com/hawk/guides/add_room.png"  width="800"></img>
#### 2、编辑和删除
<img src="https://cdn.iseekfree.com/hawk/guides/edit_room.png"  width="800"></img>

#### 3、运行弹幕间
特别注意：在开启弹幕采集过程中，切勿开启“VPN”(如果开启了VPN，请关闭VPN并重启“流鹰”软件；
<img src="https://cdn.iseekfree.com/hawk/guides/run_room.png"  width="800"></img>

### 四、互动插件
**1、自定义插件**
自定义插件功能能用来做什么呢？
1.1、基于弹幕数据进行游戏控制，比如大家可以基于弹幕和主播讲话数据，驱动游戏人物走动、打怪；
1.2、基于弹幕数据控制机器人行走；
1.3、基于弹幕数据、主播讲话做电商直播带货能力的分析，做一个专业的主播带货分析能力的Agent；
1.4、基于弹幕数据，通过控制电机信号做互动射击；
1.5、基于弹幕数据和主播讲话，进入抽奖大转盘，进行现场抽奖；
1.6、......
<img src="https://cdn.iseekfree.com/hawk/guides/add_plugin.jpg"  width="800"></img>

**2、插件集成**
2.1、插件市场或自定义插件最终以网页嵌入在直播间弹幕采集页面中。
2.2、然后插件页面中需实现以下代码用于从父窗口中接收实时的弹幕、主播讲话内容等数据：
```HTML
window.addEventListener('message', (event) => {
    //检查来源以确保安全
    //if(event.origin !== 'xxx'){
    //  return;
    //}
    
    if(event.data.type === 'StreamInit'){
      //插件页面初始化
      var roomId = event.data.data.roomId;
      console.log('当前房间Id',roomId);
    }else if(event.data.type === 'StreamHawk'){
      //弹幕消息、主播讲话消息
      var data = event.data.data;
      if(data.type === 'text'){
        //文本消息
      }else if(data.type === 'gift'){
        //礼物消息
      }else if(data.type === 'entrance'){
        //进入房间消息
      }else if(data.type === 'like'){
        //点赞消息
      }else if(data.type === 'streamer'){
        //主播讲话内容
      }
    }
})
```

**3、启用插件**
在弹幕采集和主播讲解过程中，大家可根据自己的需求随时切换到任意一款插件。
<img src="https://cdn.iseekfree.com/hawk/guides/plugin_enable.jpg"  width="800"></img>



### 五、常见问题

#### 1、审核事项
「审核时间」：由于数据源隐私和所属权验证，在创建弹幕直播间后会进入审核。通常审核时间2个工作日，节假日顺延。当然通常审核时间会很快！
「审核资料」：在创建直播弹幕间时，需要填写联系方式和审核资料，请务必认证填写，如果有疑问，我们会发起电话咨询，以确保资料有效性！

#### 2、运行事项
「直播窗口」：运行弹幕间时，会打开用户设定直播地址，此时软件会新开弹幕子窗口用于弹幕采集！请勿关闭，如不小心关闭，请返回重新运行！
「推送频率」：弹幕推送往往会在1-2s内向您的服务器地址进行推送，如果直播间弹幕量较大，请务必保证您的服务器性能足够，避免造成推送阻塞！

#### 3、退款问题
「能否退款」：除非本软件问题导致不可用，可按剩余日期/付款时长比例同比退款！其它原因会按照服务协议规定处理！

#### 4、无法采集
  特别注意：在开启弹幕采集过程中，切勿开启“VPN”(如果开启了VPN，请关闭VPN并重启“流鹰”软件；


### 六、联系我们
如果你有更多问题想要解答，请通过以下二维码联系我们：

<img src="https://cdn.iseekfree.com/share/contact/wechat_qrcode_geekbruce.jpg" width="400"></img>

