# MMCRYPTO × WEEX 独立站 · 完整源码

这是 MMCRYPTO（Christopher Jaszczyński）的英文个人品牌网站。页面围绕市场观点、个人成长经历、健康生活习惯与 WEEX 导流展开。采用 HTML、CSS 和原生 JavaScript，无需安装框架、npm 依赖或执行构建命令。

## 视觉与布局

2026-10-13 版本采用暖白、深炭色与香槟金的编辑式排版，使用系统无衬线字体与 Georgia 衬线字体，无需外部字体请求。页面依次为人物首屏、品牌数据、互动故事、精选视频、健康生活、WEEX 与社媒入口。

人物主图、训练照片和视频封面来自三个不同来源，各展示一次。故事区以文字与阶段切换呈现，不再复用人物照片。WEEX 标志在导航与专属模块各展示一次。

## 文件说明

```text
index.html          页面结构和英文文案
styles.css          配色、布局、动效和移动端样式
player.css          视频播放器和加载后备状态
config.js           社媒、WEEX 注册、活动和 VIP 链接
app.js              导航、内容切换、视频播放和动效交互
assets/             本地人物照片、视频封面、品牌素材
assets/sources.json 素材与公开内容的来源记录
package_site.py     可选打包工具（无需第三方 Python 依赖）
README.md           本说明
```

请保留目录结构；`assets` 文件夹要与 `index.html` 放在同一级。

## 先在电脑上预览

解压后，双击 `index.html` 即可查看页面排版。直接用文件方式打开时，视频会跳转到 YouTube 观看，这是正常行为。

需要测试站内视频弹窗时，建议使用本地网页服务器。在源码所在文件夹打开终端，运行：

```sh
python3 -m http.server 4173
```

然后打开 `http://localhost:4173/`。若提示端口被占用，可将 `4173` 改为 `4174`，并打开对应端口的地址。终端按 `Control + C` 可以停止服务器。

YouTube 在线播放需要联网，并取决于浏览器、所在地区和视频作者是否允许嵌入。若嵌入不可用，请使用弹窗内的 YouTube 链接。网站不包含视频源文件。

## 上传或更新 GitHub Pages

1. **先解压 ZIP。不要把 ZIP 文件直接上传到仓库。**
2. 打开用于部署本网站的 GitHub 仓库，进入根目录，点击 **Add file → Upload files**。
3. 上传解压得到的 **全部文件和 `assets` 文件夹**。`index.html` 应直接显示在仓库根目录，不能再包在一层 `mmcrypto` 文件夹里。
4. 更新已有网站时，覆盖全部同名文件，点击 **Commit changes**。只上传新的 `index.html`，却保留旧的 CSS / JavaScript，可能造成新版与旧版混在一起。
5. 首次部署时进入 **Settings → Pages**，选择 **Deploy from a branch**，分支选 **main**，目录选 **/ (root)**，再点击 **Save**。
6. 在 **Actions** 等待对应最新提交的 Pages 部署完成并显示绿色成功，再打开 Pages 提供的网址。

如果部署成功后仍看到旧版，可以在网址后加一个新的版本参数，例如 `?v=20261013`。页面右侧显示的历史部署成功状态，不一定属于刚刚上传的最新提交，请核对时间和提交记录。

普通 GitHub Pages 项目的网址通常为 `https://你的用户名.github.io/仓库名/`。本网站使用相对文件路径，支持放在仓库子路径下。

## WEEX 注册、活动与 VIP 链接

统一在 `config.js` 中修改：

```js
weexRegister: 'https://www.weex.com/register',
weexHome: 'https://www.weex.com/',
campaign: null,
vip: null
```

- `weexRegister`：目前使用 WEEX 官方注册入口。BD 提供 MMCRYPTO 专属注册链接后，再替换为完整 URL；当前链接不包含其他 KOL 的邀请码。
- `weexHome`：WEEX 官方首页。
- `campaign`：MMCRYPTO 专属活动链接，待 BD 提供后替换 `null`。
- `vip`：经确认的 VIP 页面链接，待 BD 提供后替换 `null`。

`null` 不是坏链接；它表示暂未配置，页面保留对应的信息说明，并将按钮接到 WEEX 官方首页。请不要随意填入其他 KOL 的活动链接、奖励金额、VIP 门槛、倒计时或未确认权益。活动确定后，也要同步更新页面文案与参加条件。

例：将 `campaign: null` 改为 `campaign: 'https://经确认的完整活动网址'`。保留引号、逗号和 JavaScript 语法。更新配置后，把新的 `config.js` 上传覆盖即可；如果页面文案也有修改，对应 HTML / CSS / JS 文件也应一起上传。

## 社媒链接

以下链接已放入 `config.js`，需要更新时修改配置，同时同步 `index.html` 中的默认链接，以支持禁用 JavaScript 时的跳转：

| 入口 | 地址 |
| --- | --- |
| YouTube | https://www.youtube.com/@mmcryptotube |
| X | https://x.com/mmcrypto |
| Instagram | https://www.instagram.com/chrismmcrypto/ |
| Chris MMHealth | https://www.instagram.com/chrismmhealth/ |
| Telegram | https://t.me/MMCrypto |

精选视频使用已核实的 MMCrypto × MMHealth 健康主题短视频。YouTube、X、Instagram 和 Telegram 入口集中展示在页面下方。换视频时，需同时核对观看链接、`data-video`、标题、封面和来源记录。本站不提供实时行情或收益数据。

## 域名说明

问卷中的期望地址是 `pro.weex.com/mmcrypto`。这个地址属于 WEEX 域名，必须由 **WEEX 域名 / 网站管理团队**配置路径、托管或反向代理。只把源码上传到个人 GitHub，无法自行启用该地址，也不应把 `pro.weex.com/mmcrypto` 直接填入 GitHub Pages 的 Custom domain 字段（该字段不接受路径）。

可以先用 GitHub Pages 链接预览，正式上线时把这份完整源码交给 WEEX 网站团队。

## 完整源码版与单文件版

- **完整源码版**：适合继续编辑与长期维护。请同时保留 HTML、CSS、JavaScript 和 `assets`。
- **单文件版**（若同时交付）：本站样式、脚本和本地图片已经合并到 `index.html`，上传这个文件即可。YouTube 视频和外链仍需要网络。

两种版本都可以静态部署。请不要把源码版的 `index.html` 当成单文件版独立上传；文件名一样，但内容不同。

修改完整源码后，应重新生成单文件版。在完整源码所在目录执行 `python3 package_site.py`，即可在上一级目录生成完整源码 ZIP 与单文件 ZIP。该脚本是交付辅助工具，不是网站运行依赖。

## 内容与素材维护

人物介绍依据 BD 提供的信息；公开照片、视频与品牌素材的来源记录在 `assets/sources.json`。平台订阅数属于采集时点的公开快照，可能变化；视频原始标题保存在来源记录中，网页上可能使用便于阅读的编辑概括标题。

网站未编造收益、实时价格、活动奖金、VIP 条件或用户证言。健康模块呈现个人生活习惯，不提供诊断或治疗建议。风险说明保留在页面底部；正式活动权益以 WEEX 当时公布的条款为准。
