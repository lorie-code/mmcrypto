# MMCRYPTO 英文个人品牌网站 · Neutral v3 完整源码

这是 MMCrypto（Christopher Jaszczyński）的英文个人品牌网站，内容包括个人经历、持续的市场观点、公开评论、健康生活与交易所合作入口。网站使用 HTML、CSS 和原生 JavaScript，无需安装框架、npm 依赖或执行构建命令。

## 本版内容与视觉

2026-10-14 的 Neutral v3 采用暖白、深炭色与柔和金色的编辑式排版。顶部以 MMCrypto 个人品牌为主，不展示 WEEX 联名标志。公开页面包括首屏、人物故事、市场内容库、健康生活、交易所合作与社媒入口；登录演示后可进入独立的 Member Hub。

人物故事保留五个章节：德国学生与出租车司机、2017 年转向、最初一年的坚持、内容与社区、健康与生活。Story5 将五章收纳在同一个固定高度的展示区域，一次展示一章；渐变、文字和对应照片融合在同一画面内，不再分为独立左右模块或向下平铺。可通过顶部章节标签、上一章／下一章按钮、键盘方向键或原生横向滑动切换，切换后更新章节进度。窄屏或放大文字时，每章正文可以在区域内纵向滚动，确保完整阅读。支持减少动态效果设置和暂停动效，不自动轮播，也不拦截页面纵向滚轮；打印时展开全部章节。两张故事照片来自官方 Instagram：2026 年 7 月的录制对话场景，以及 2026 年 8 月与腊肠犬 Mila 的生活瞬间。它们是有明确日期的近期照片，不作为 2017 年或出租车司机时期的历史影像。主肖像、故事照片与训练照片分别使用，不重复同一人物照片。

内容库共 11 项：6 个已核实来源的视频、3 条公开 X 评论和 2 篇本站原创学习笔记。视频覆盖市场展望、周期分析、技术分析、交易心理、跨市场观察，以及一个标明 2019 年的存档对话。五个近期视频使用各自的原始预览图，存档视频使用文字排版，不使用带币种符号的访谈照片。

- 筛选为 All / Videos / Commentary / Reading room / Members，数量分别为 11 / 6 / 3 / 2 / 1。
- 默认显示 6 项，Show more 每次增加最多 6 项；切换筛选后重新显示该筛选的前 6 项。
- 登录状态变化会更新会员入口文案，但不会收起读者已经展开的内容。
- 展示标题与简介是本站编辑对原始内容的主题概括；原始日期和来源链接随卡片保留。
- X 内容明确标记 Public commentary，属于简短公开帖子，不被包装成长篇文章。
- 两篇 Reading room 笔记明确为网站原创编辑内容，不是 Chris 本人撰写。
- 原有健康短视频 `u1I9lzSNtzA` 移至健康模块的文字入口，不再作为市场内容库中的大幅精选视频。

合作区和 Member Hub 采用多个交易所卡片。WEEX 为当前合作；Binance 与 Bybit 仅为明确标注的示例展示，尚未确认合作关系、专属注册链接或邀请码。内容数量与公开平台数据不代表投资表现。

## 文件说明

```text
index.html          页面结构和英文文案
styles.css          基础配色、布局、动效和移动端样式
player.css          视频播放器、加载与后备状态
frontend.css        导航、内容库、注册弹窗和会员中心基础样式
journey.css         固定高度故事滑动区、章节控制、渐变与照片融合
neutral.css         Neutral v3 的品牌、内容库和合作模块视觉覆盖
config.js           官方社媒、合作配置、注册链接与演示模式
app.js              导航、故事联动、视频播放和动效交互
members.js          演示注册/登录、会员中心和三步交易所关联
content.js          内容筛选、分页、学习笔记与会员访问演示
assets/             本地人物照片、视频预览图和品牌素材
assets/sources.json 已核实素材、视频、评论与内容来源记录
package_site.py     可选打包工具，仅使用 Python 标准库
README.md           本说明
```

请保留目录结构；`assets` 文件夹与 `index.html` 同级。页面使用系统无衬线字体与 Georgia，无需外部字体请求。

## 在电脑上预览

解压后双击 `index.html` 可查看排版。直接以文件方式打开时，视频链接前往 YouTube，这是正常行为。

测试站内视频弹窗和完整交互时，在源码目录打开终端运行：

```sh
python3 -m http.server 4173
```

打开 `http://localhost:4173/`。端口被占用时，可改为 `4174` 并访问对应地址。按 `Control + C` 停止服务器。

视频由 YouTube 提供，源码不包含视频源文件。在线播放需要联网，是否能够嵌入还取决于浏览器、地区与平台限制。无法播放时可使用弹窗内的原始 YouTube 链接。来源核实包括公开标题、日期、描述和章节信息，不表示对全部视频完成了完整观看。

## 上传或更新 GitHub Pages

1. **先解压 ZIP，不要直接上传 ZIP 文件。**
2. 打开部署网站的 GitHub 仓库，进入根目录，选择 **Add file → Upload files**。
3. 上传解压得到的全部文件及 `assets` 文件夹。`index.html` 应直接位于仓库根目录，不要再包一层 `mmcrypto` 文件夹。
4. 更新时覆盖所有同名文件并点击 **Commit changes**。本版必须同时包含 `neutral.css`、更新后的 JavaScript 和新增图片；只替换 HTML 可能造成新旧版本混用。
5. 首次部署进入 **Settings → Pages**，选择 **Deploy from a branch**，分支 **main**，目录 **/ (root)**，点击 **Save**。
6. 在 **Actions** 核对最新提交的 Pages 部署任务，等待绿色成功后访问 Pages 提供的网址。

如果仍显示旧版，可以在网址后加新的版本参数，如 `?v=20261014-neutral3`。请核对部署时间和提交记录，避免把历史任务的成功状态当成本次部署结果。

普通项目网址通常为 `https://你的用户名.github.io/仓库名/`。本站使用相对资源路径，可以部署在仓库子路径下。GitHub Pages 可以托管这些前台文件，不能独立运行真实认证、邮件发送或交易所校验服务。

## 网站会员演示

主导航为 Home / About Me / Content / Brand Collaborations / Social Media / Sign In。完成演示登录后可以通过 Member Hub 返回会员中心。

1. 点击 Join free，输入虚构的网站会员邮箱，例如 `reader@example.com`。
2. 阅读并勾选演示说明；Terms / Privacy 在当前版本中是说明弹窗，不是正式发布的法律文件。
3. 点击 Continue，使用弹窗直接显示的六位演示验证码。系统不会发送邮件。
4. 输入验证码进入 Member Hub。默认验证码有效期为五分钟，重新生成间隔为三十秒。
5. 退出后可使用同一示例邮箱通过 Sign In 再次演示登录。退出清除当前登录和账户关联，示例账户列表仅在本标签页内保留用于重复注册检查。

演示数据保存在当前标签页的 `sessionStorage`。浏览器不允许存储时退回内存，刷新可能丢失状态。当前版本没有真实用户数据库、邮件服务或 Discord OAuth；Discord 入口说明该服务尚未接入。前端会员笔记的全文仍在源码中，演示访问控制不能保护真正的付费内容。

## 三步交易所关联

网站会员邮箱与交易所账户邮箱是两个独立字段，二者可以不同。关联界面不会用网站会员邮箱代替交易所邮箱。

1. **Registration：注册后返回。** 选择交易所，查看指定注册链接与邀请码状态。在真实流程中应通过已确认的 MMCrypto 指定链接前往交易所注册，再返回本站。当前演示只要求勾选“模拟完成注册并返回”，不需要创建真实交易所账户。
2. **Details：填写交易所资料。** 输入该交易所账户的邮箱和数字 UID。UID 最长 20 位；格式正确本身不表示账户存在，也不表示邀请关系成立。
3. **Result：检查邀请归属。** 预览模式展示固定演示结果。未来真实服务须在服务端确认账户与预期邀请关系，再返回匹配、邀请不符、未找到或服务不可用状态。

目前没有提供任何交易所的 MMCrypto 专属注册链接或邀请码。一般官网和通用注册页被明确标为通用入口，不会被当作指定邀请链接。Binance / Bybit 的列表和流程始终带有示例标识，不能据此宣称合作。

### 可重复试用的样例

先登录网站会员演示并完成模拟注册步骤。交易所邮箱统一使用 `exchange.demo@example.com`，可点击界面中的样例按钮填入下列 UID：

| 示例 UID | 返回状态 | 演示意义 |
| --- | --- | --- |
| `10000001` | `matched` | 模拟账户找到且邀请关系匹配；保存当前标签页的演示关联 |
| `10000002` | `invitation_mismatch` | 模拟账户存在，但邀请关系不符 |
| `10000003` | `not_found` | 模拟未找到账户 |
| `10000004` | `unavailable` | 模拟校验服务不可用，可重试 |

其他邮箱或 UID 组合返回演示 `not_found`。演示不联系交易所，不核实真实账户，不产生推荐归因、奖励或 VIP 资格。失败或不可用结果不会保存关联。

## 配置与未来服务接入

`config.js` 中有两个独立模式：

```js
membership: {
  mode: 'preview',
  otpTtlSeconds: 300,
  resendSeconds: 30,
  termsUrl: null,
  privacyUrl: null,
  discordUrl: null
},
exchangeVerification: { mode: 'preview' }
```

仅修改 `membership.mode` 为 `live` 不会启用真实登录，而会停止现有演示认证。生产环境还需要真实认证、会话数据库、邮箱验证、正式用户协议与隐私政策；Discord 登录需要另行接入 OAuth。真正受限的内容应由服务端验证身份和访问权限。

每个现有交易所的可配置字段位于 `exchanges`：`id`、`name`、`relationship`、`homeUrl`、`registrationUrl`、`inviteCode`、`description`。`relationship: 'partner'` 只能在合作已确认后使用；`example` 表示示例。当前代码支持 WEEX / Binance / Bybit 三个入口，新增其他交易所还需同步页面与 `members.js` 的列表。

- `registrationUrl` 是经确认的完整 MMCrypto 专属注册链接；为空时显示通用入口与待提供状态。
- WEEX 还可使用 `partner.referralUrl` 作为专属注册链接的后备配置。它不是每个网站会员自己的独立推荐码。
- `inviteCode` 仅用于展示已确认的信息。预期邀请归属规则必须由可信服务端掌握，不能相信浏览器提交或展示的代码。
- 即使将官方首页或不带推荐参数的普通 `/register`、`/signup` 页面填入推荐配置，当前流程仍会把它视为通用地址。
- `partner.tutorialUrl` 和 `partner.rewardTitle` 保留为可选配置；不要填入未确认的教学链接或权益承诺。

未来交易所校验适配器的接口为：

```js
window.MM_EXCHANGE_PROVIDER = {
  async verifyReferral({ exchangeId, email, uid }) {
    // 调用可信后端；后端检查账户及由服务端保存的预期邀请关系。
    // 返回状态之一：matched / invitation_mismatch / not_found / unavailable。
    return { status: 'unavailable' };
  }
};
```

这是接入接口示意，不是已完成的后端。当前预览模式完全跳过此适配器。将 `exchangeVerification.mode` 配为 `live` 后，前台还要求该交易所是已确认合作、具有指定注册链接且适配器存在，才会调用 `verifyReferral({ exchangeId, email, uid })`。浏览器不发送“预期邀请码”；服务端自行确定规则。调用超时 15 秒、异常或无效状态会显示 `unavailable`。不要把交易所密钥或其他服务端秘密放入前端。

上述适配器钩子与网站会员生产认证是不同工作；接上校验函数并不自动完成真实会员系统。即使真实服务返回匹配，奖励与 VIP 资格仍取决于另外公布的有效条款。

## WEEX、活动与 VIP 链接

当前 `links.weexRegister` 为 `https://www.weex.com/register`，`links.weexHome` 为 `https://www.weex.com/`。`campaign` 和 `vip` 仍为 `null`，相应说明保留官方首页后备链接，没有活动金额、期限或 VIP 条件承诺。

BD 提供专属注册链接后，优先更新 WEEX 对应的 `exchanges[].registrationUrl`，并按需要同步 `partner.referralUrl`、仍在使用的通用链接及 HTML 默认链接。活动或 VIP 链接只能使用已确认的完整 HTTPS 地址，并同步页面上的参与条件。不要复制其他创作者的邀请码、活动条款或奖励数字。

## 官方社媒与内容维护

| 入口 | 地址 |
| --- | --- |
| YouTube | https://www.youtube.com/@mmcryptotube |
| X | https://x.com/mmcrypto |
| Instagram | https://www.instagram.com/chrismmcrypto/ |
| Chris MMHealth | https://www.instagram.com/chrismmhealth/ |
| Telegram | https://t.me/MMCrypto |

修改官方入口时，同步 `config.js` 和静态 HTML 后备链接。Telegram 保留用户提供的德语社区。替换视频时需同步观看地址、`data-video`、`data-video-title`、日期、预览图与来源记录。原始来源标题保存在 `assets/sources.json`，页面用经过核实的主题概括，不能据标题推断未核实的研究结论。

人物介绍以提供的 BD 资料为基础；照片、视频和公开帖子记录在 `assets/sources.json`。公开平台数量是特定采集日期的快照，不是实时数据。本站没有伪造实时行情、收益、奖项、活动倒计时或用户证言。健康内容呈现个人生活与习惯，不提供诊断或治疗建议。素材来源记录说明出处，不单独构成使用权证明。

## 完整源码与单文件打包

- **完整源码版**保留 HTML、全部 CSS / JavaScript、`assets` 与文档，适合继续维护。
- **单文件版**（若同时交付）把本站 CSS、脚本和本地图片合并到 `index.html`，可只上传该 HTML。YouTube 和外部链接仍需要网络。

不要把完整源码中的 `index.html` 当作单文件版独立上传。修改源码后，在源码目录运行：

```sh
python3 package_site.py
```

脚本会在源码目录的上一级生成 `mmcrypto-complete-source.zip`、`mmcrypto-single-file.zip` 和 `mmcrypto-single-file/`。ZIP 的页面入口位于根目录。只需完整源码包时可运行 `python3 package_site.py --full-only`。打包工具使用 Python 标准库，不是网站运行依赖。

## 域名说明

期望地址 `https://pro.weex.com/mmcrypto` 属于 WEEX 域名，须由该域名的网站管理团队配置路径、托管或反向代理。上传到个人 GitHub 不会自动启用该地址，也不要把含路径的地址填入 GitHub Pages 的 Custom domain 字段。

可先用 GitHub Pages 预览，再把完整源码交给负责正式域名的团队。
