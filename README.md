
# Chrome 浏览器 131 版本新特性


## 一、Chrome 浏览器 131 版本新特性


### 1\. 在 iOS 上使用 Google Lens 搜索


自 Chrome 126 版本以来，用户可以通过 Google Lens 搜索屏幕上看到的任何图片或文字。


要使用此功能，请访问网站，并点击聚焦时出现在地址栏的 Google Lens 搜索按钮，或者点击桌面右键菜单、桌面和移动端的三点菜单。用户可以在屏幕上任意点击、选中或拖动以搜索内容，并通过在搜索框中添加关键词或问题来优化搜索。


管理员可以通过名为 LensOverlaySettings 的策略控制此功能。进行搜索时，屏幕截图会被发送到 Google 服务器，但不会关联任何 ID 或账户，且不会被任何人查看，内容信息也不会被记录。我们已在 iOS 的 Chrome 131 版本中开始逐步推出此功能，并计划在 Chrome 132 版本中全面推出。


#### 1\.1\. 适用版本：


* **Chrome 126** (适用于 ChromeOS、Linux、macOS、Windows)：在 1% 的稳定版中发布该功能
* **Chrome 127** (适用于 ChromeOS、Linux、macOS、Windows)：在 100% 的稳定版中发布该功能
* **Chrome 131** (适用于 iOS)：开始推出该功能
* **Chrome 132** (适用于 iOS)：在 100% 的稳定版中发布该功能


### 2\. iOS 上的异步实时安全浏览检查


目前，安全浏览检查是在页面加载的阻塞路径上进行的，这意味着用户在检查完成之前无法看到页面。为了提升 Chrome 的加载速度，在 Chrome 122 版本（iOS 上为 Chrome 131 版本）之后，实时安全浏览检查将不再阻塞页面加载。


#### 2\.1\. 适用版本：


* Chrome 122：Android、ChromeOS、Linux、macOS、Windows
* Chrome 131：iOS


### 3\. 适用于 macOS 的 PWA Shim 临时代码签名


在 macOS 上安装渐进式 Web 应用程序（PWA）时创建的应用程序 Shim 的代码签名将更改为在应用程序安装时生成的临时代码签名。


代码签名由 macOS 用于标识应用程序。这些临时签名会让每个 PWA 应用 Shim 在 macOS 上拥有唯一的身份。


可以使用 chrome://flags/\#use\-adhoc\-signing\-for\-web\-app\-shims 标志开启该功能进行测试。


如果该功能与现有的安全策略不兼容，可以使用 AdHocCodeSigningForPWAsEnabled 策略禁用该功能，以便管理员部署更新的端点安全策略。


#### 3\.1\. 适用版本：


* **Chrome 129 on macOS**：此功能可以通过标志（chrome://flags/\#use\-adhoc\-signing\-for\-web\-app\-shims）开启。
* **Chrome 131 on macOS**：该功能开始逐步向稳定版推出，初始推出率为 1%。


### 4\. 从 Google Drive 中选择文件


从 Chrome 131 开始，iOS 版 Chrome 用户可以直接从 Google Drive 将文件上传到网页，而无需先将其下载到设备上。


### 5\. Chrome PDF 查看器 OCR 功能


Chrome 桌面版现在使扫描的 PDF 更加易于访问。通过设备上的光学字符识别（OCR）技术来确保隐私（不会将内容发送到 Google），Chrome 自动转换扫描的 PDF，让用户可以选择文本、使用 Ctrl\+F 搜索、复制和粘贴。该功能不会绕过受保护的 PDF，仅对用户有访问权限的 PDF 使用 OCR。


* **Chrome 131** 适用于 ChromeOS、Linux、macOS 和 Windows。


### 6\. 桌面端新标签页的 iOS 版 Chrome 推广


桌面端的新标签页中将显示 iOS 版 Chrome 的推广信息。此推广旨在提高用户对 iOS 版 Chrome 的认知，并提供简单的安装方式。


可以使用现有的 PromotionsEnabled 和 NTPMiddleSlotAnnouncementVisible 策略来控制此功能。


### 7\. 跨配置文件的密码重用检测


之前，公司凭证的密码重用检测只能在公司配置文件中检测到。现在，在受管理的浏览器上，密码重用检测可以在所有非隐身模式的配置文件中检测公司凭证的重用。


更新了跨配置文件密码重用检测的标准，以更准确地反映受管理的企业账户。


### 8\. Android 版 Chrome 现已支持第三方自动填充和密码管理服务


此前，Android 版 Chrome 中的第三方自动填充和密码管理服务是通过辅助功能 API 实现的。


在 Chrome M131 版本中，增加了对 Android 自动填充的直接支持，这意味着这些第三方服务可以在不依赖辅助功能 API 的情况下与 Android 版 Chrome 配合使用，从而提升 Chrome 和第三方自动填充服务的性能。


要使用此功能，用户需要在 Android 设置中配置好第三方提供商。然后，在 Chrome 中访问设置 \-\> 自动填充服务，并选择“使用其他服务进行自动填充”。


如果用户未更改这两个设置，Chrome 将继续使用 Google 的服务来自动填充密码、支付和地址信息。是否允许用户使用第三方自动填充服务可由新的策略 ThirdPartyPasswordManagersAllowed 控制。


### 9\. 弃用安全浏览扩展报告功能


Chrome 正在弃用安全浏览扩展报告功能，该功能曾通过收集参与用户的遥测信息来增强所有用户的安全性，并用于 Google 安全浏览保护。收集的数据包括访问网页的 URL、有限的系统信息和部分页面内容。


此功能现已被增强保护模式取代。建议用户切换到增强保护模式，以便在启用 Chrome 最强安全性功能的同时，继续提供对所有用户的安全保护。


![image](https://img2024.cnblogs.com/blog/3373677/202411/3373677-20241120100555738-791665458.png)



### 10\. 不再信任 Entrust 证书


由于 Entrust 持续存在合规问题，Chrome 将在 Chrome 131 及更高版本的 Windows、macOS、ChromeOS、Android 和 Linux 中默认更改对 Entrust 颁发的公开信任 TLS 服务器认证（网站）证书的信任方式。iOS 的政策不允许在 iOS 版 Chrome 中使用 Chrome 根存储。


具体而言，通过 Entrust 根 CA 证书验证并存储于 Chrome 根存储中的 TLS 证书，如果：


* **签发日期为 2024 年 11 月 11 日之后**，将不再被默认信任。
* **签发日期为 2024 年 11 月 11 日或之前**，则不受此更改的影响。
* **Chrome 131 on Android、ChromeOS、Linux、macOS、Windows**：所有依赖 Chrome 根存储的 Chrome 131 及更高版本将执行该阻止操作，但阻止仅适用于 2024 年 11 月 11 日后签发的证书。


### 11\. iOS 上的不安全表单警告


自 Chrome 125 起，Chrome 浏览器在 iOS 上会阻止从安全页面提交到不安全页面的表单。当 Chrome 检测到不安全的表单提交时，会显示一个警告，要求用户确认提交。此举的目的是防止在没有用户明确批准的情况下，通过明文传输泄露表单数据。提供了一个名为 InsecureFormsWarningsEnabled 的策略，用于控制此功能。


* **Chrome 125 在 iOS 上**：此功能开始推出。
* **Chrome 131 在 iOS 上**：InsecureFormsWarningsEnabled 策略将被移除。


### 12\. **具有高级检查的 PartitionAlloc (PA/AC)**


PartitionAlloc (PA) 及其相关的内存安全项目包含一系列高级保护措施，这些措施默认情况下被禁用（或仅在调试版本中启用），因为它们可能会对性能产生影响。尽管立即为所有用户启用该功能可能不可行，但仍然有机会在特定的有限条件下部分启用它。


### 13\. **简化的登录和同步体验**


从 Chrome 131 开始，启用 Chrome 同步的现有用户将体验到简化和整合的登录与同步流程。


Chrome 同步不再作为设置中的独立功能显示，也不再单独列出。相反，用户只需登录 Chrome，即可在 Google 帐户中使用和保存信息，如密码、书签等，前提是遵循相关的企业政策。


与之前一样，保存和访问 Chrome 数据到 Google 帐户的功能仍然可以通过 SyncTypesListDisabled 进行控制。登录 Chrome 的功能仍然可以通过 BrowserSignin 来关闭，如同以前一样。


需要注意的是，这些更改不会影响用户在 Web 上登录 Google 服务（如 Gmail）的能力，即使他们未登录 Chrome，也不会影响他们保持 Chrome 未登录状态的能力，或者控制与 Google 帐户同步的信息。


### 14\. **能源节省模式下的标签冻结**


当启用能源节省模式时，Chrome 会冻结那些已隐藏且静默超过 5 分钟并且占用大量 CPU 的标签，除非：


* 该标签提供音频或视频会议功能，通过麦克风、摄像头、屏幕、窗口或标签捕获，或者有一个 RTCPeerConnection 正在使用打开的 RTCDataChannel 或一个活跃的 MediaStreamTrack。
* 该标签控制一个外部设备，通过 Web USB、Web Bluetooth、Web HID 或 Web Serial 被检测到。


此功能通过减少 CPU 使用，延长电池寿命并加速 Chrome 浏览器的运行。


该功能将在 Chrome 131 中开始向 1% 的稳定版用户逐步推出，随后会逐渐扩展到 100% 的稳定版用户。


### 15\. **更新 Google Play 服务以修复设备上的密码问题**


使用旧版 Google Play 服务的用户将会在设备上的密码功能上遇到功能减少的问题，并且密码管理器可能很快完全无法使用。这些用户需要更新 Google Play 服务，或者根据他们的状态，系统将引导他们通过其他故障排除方法进行解决。这是一个正在进行的迁移过程，仅影响使用 Google 密码管理器的 Android 用户。


### 16\. **用于 TLS 的 X25519Kyber768 密钥封装机制**


从 Chrome 124 开始，Chrome 在所有桌面平台上默认启用了基于 NIST 标准（ML\-KEM）的新后量子安全 TLS 密钥封装机制 X25519Kyber768。该机制旨在保护 Chrome 与支持 ML\-KEM 的服务器之间的网络流量，防止未来量子计算机解密。这一变更对于服务器运营商应当是透明的。此密码算法将用于 TLS 1\.3 和 QUIC 连接。


### 17\. **CSS 锚点定位属性** inset\-area **的废弃**


CSS 工作组（CSSWG）决定将 inset\-area 属性重命名为 position\-area。


通过此次功能更新，position\-area 属性作为 inset\-area 的同义词发布，标志着 inset\-area 属性的废弃和移除。


这一变更将影响使用 inset\-area 属性的开发者，未来应该使用新的 position\-area 属性来替代旧的名称。


### 18\. **改进**  **和**  **元素的样式结构**


为  和  元素提供更多的 CSS 样式支持，使这些元素可以在更多构建披露小部件或手风琴小部件的网页中使用。


这项更改移除了以前限制设置这些元素的 display 属性的限制，并新增了 ::details\-content 伪元素，用于样式化用于扩展和折叠的部分容器。


### 19\. **键盘锁定和指针锁定权限**


当网站请求使用键盘锁定或指针锁定时，浏览器可能会向用户显示权限提示，并将用户的偏好设置保存为内容设置。这些设置可以通过权限 API 进行查询。此措施有助于减少对这些 API 的滥用。


### 20\. **移除非标准的** GPUAdapterrequestAdapterInfo() **方法**


WebGPU 工作组（WG）决定，requestAdapterInfo() 方法触发权限提示的方式不切实际，因此他们移除了该选项，并用 GPUAdapter 的 info 属性替代。这样，网页开发者可以同步地获取相同的 GPUAdapterInfo 值。


### 21\.  **解析器放宽**


此更改使 HTML 解析器在  元素中允许更多的标签，除了 、 和 

---

。


这项更改是为了支持可自定义的  功能，但由于它可以单独实现并且风险较小，因此首先推出。


此功能受临时策略 SelectParserRelaxationEnabled 控制。该策略将在 Chrome 136 版本中停止生效。


### 22\. **支持外部 SVG 资源用于** clip\-path**、**fill**、**stroke **和** marker\-\* **属性**


此更改允许在 clip\-path、fill、stroke 和 marker\-\* 属性中使用外部 SVG 资源的引用。例如，可以使用如下语法：



```
clip-path: url("resources.svg#myPath");

```

可以在 CSS 中直接引用外部 SVG 文件中的路径、标记或填充/描边服务器，从而使图形元素的样式更加灵活和可重用。


### 23\. **支持非特殊方案 URL**


Chrome 130 开始支持非特殊方案的 URL，例如 git://example.com/path。之前，Chromium 的 URL 解析器不支持非特殊 URL，且解析非特殊 URL 时会将路径视为不透明的，这与 URL 标准不一致。现在，Chromium 的 URL 解析器已正确解析非特殊 URL，遵循 URL 标准。


#### 23\.1\. 适用版本：


* **Chrome 130** 在 Windows、macOS、Linux、Android 上支持非特殊方案的 URL。
* **Chrome 131** 在 Windows、macOS、Linux、Android 上继续支持。
* **Chrome 134** 在 Windows、macOS、Linux、Android 上将移除此功能标志。


### 24\. **翻译功能与 Google Lens 搜索结合**


增强现实（AR）翻译功能正在被集成到 Google Lens 搜索功能中。


### 25\. **Chrome 浏览器中的新策略**




| **策略名称** | **描述** |
| --- | --- |
| DownloadRestrictions | 允许设置下载限制。 |
| CAPlatformIntegrationEnabled | 使用用户添加的 TLS 证书来自平台信任存储进行服务器身份验证。 |
| SelectParserRelaxationEnabled | 控制是否启用  元素的新 HTML 解析器行为。 |
| EnterpriseProfileBadgeToolbarSettings | 控制工具栏中企业配置文件徽章的可见性。 |
| WebAudioOutputBufferingEnabled | 启用 Web 音频的自适应缓冲。 |


### 26\. Chrome 浏览器移除的策略




| **策略名称** | **描述** |
| --- | --- |
| ProfileLabel | 控制用于标识已登录配置文件的标签。该标签将显示在多个位置，帮助用户识别配置文件，例如在工具栏的配置文件图标旁边。 |
| ToolbarAvatarLabelSettings | 管理工具栏头像标签设置。 |


## 二、Chrome 131 版本更新日期


### 1\. Chrome 131


#### 1\.1\. Beta 版


2024 年 10 月 16 日，星期三


#### 1\.2\. 稳定版本


2024 年 11 月 5 日，星期二


### 参考资料


* [Chrome Enterprise and Education release notes](https://github.com)


 本博客参考[飞数机场](https://ze16.com)。转载请注明出处！
