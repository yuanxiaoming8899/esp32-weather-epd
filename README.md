<div class="Box-sc-g0xbh4-0 bJMeLZ js-snippet-clipboard-copy-unpositioned" data-hpc="true"><article class="markdown-body entry-content container-lg" itemprop="text"><div class="markdown-heading" dir="auto"><h1 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ESP32 电子纸天气显示</font></font></h1><a id="user-content-esp32-e-paper-weather-display" class="anchor" aria-label="永久链接：ESP32 电子纸天气显示" href="#esp32-e-paper-weather-display"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">这是一款天气显示器，由支持 wifi 的 ESP32 微控制器和 7.5 英寸电子纸（又名电子墨水）显示器供电。当前和预测的天气数据是从 OpenWeatherMap API 获取的。传感器为显示屏提供准确的室内温度和湿度。</font></font></p>
<p dir="auto">
  <a target="_blank" rel="noopener noreferrer" href="/lmarzen/esp32-weather-epd/blob/main/showcase/assembled-demo-raleigh-front.jpg"><img src="/lmarzen/esp32-weather-epd/raw/main/showcase/assembled-demo-raleigh-front.jpg" style="max-width: 100%;"></a>
  <a target="_blank" rel="noopener noreferrer" href="/lmarzen/esp32-weather-epd/blob/main/showcase/assembled-demo-raleigh-side.jpg"><img src="/lmarzen/esp32-weather-epd/raw/main/showcase/assembled-demo-raleigh-side.jpg" width="49%" style="max-width: 100%;"></a>
  <a target="_blank" rel="noopener noreferrer" href="/lmarzen/esp32-weather-epd/blob/main/showcase/assembled-demo-raleigh-back.jpg"><img src="/lmarzen/esp32-weather-epd/raw/main/showcase/assembled-demo-raleigh-back.jpg" width="49%" style="max-width: 100%;"></a>
  <a target="_blank" rel="noopener noreferrer" href="/lmarzen/esp32-weather-epd/blob/main/showcase/assembled-demo-bottom-cover.jpg"><img src="/lmarzen/esp32-weather-epd/raw/main/showcase/assembled-demo-bottom-cover.jpg" width="49%" style="max-width: 100%;"></a>
  <a target="_blank" rel="noopener noreferrer" href="/lmarzen/esp32-weather-epd/blob/main/showcase/assembled-demo-bottom-cover-removed.jpg"><img src="/lmarzen/esp32-weather-epd/raw/main/showcase/assembled-demo-bottom-cover-removed.jpg" width="49%" style="max-width: 100%;"></a>
</p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该项目在睡眠时消耗约 14μA，在约 15 秒的清醒期间消耗平均约 83mA。可以将显示配置为根据需要频繁更新。当刷新间隔设置为 30 分钟时，设备单节 5000mAh 电池可运行超过 6 个月。该项目显示准确的电池寿命百分比，并且可以通过连接到墙壁适配器或计算机的 USB-C 电缆充电。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">从位置、时间/日期格式、单位和语言到空气质量指数范围和每小时展望图范围，所有内容都有配置选项。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">每小时展望图（右下）显示一条指示温度的线和指示降水概率（或可选的降水量）的阴影条。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以下是使用各种配置选项的两个示例：</font></font></p>
<p dir="auto">
  <a target="_blank" rel="noopener noreferrer" href="/lmarzen/esp32-weather-epd/blob/main/showcase/demo-new-york.jpg"><img src="/lmarzen/esp32-weather-epd/raw/main/showcase/demo-new-york.jpg" width="49%" style="max-width: 100%;"></a>
  <a target="_blank" rel="noopener noreferrer" href="/lmarzen/esp32-weather-epd/blob/main/showcase/demo-london.jpg"><img src="/lmarzen/esp32-weather-epd/raw/main/showcase/demo-london.jpg" width="49%" style="max-width: 100%;"></a>
</p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">内容</font></font></h2><a id="user-content-contents" class="anchor" aria-label="永久链接： 内容" href="#contents"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<ul dir="auto">
<li><a href="#setup-guide"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">设置指南</font></font></a>
<ul dir="auto">
<li><a href="#hardware"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">硬件</font></font></a></li>
<li><a href="#wiring"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">接线</font></font></a></li>
<li><a href="#configuration-compilation-and-upload"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">配置、编译、上传</font></font></a></li>
<li><a href="#openweathermap-api-key"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">OpenWeatherMap API 密钥</font></font></a></li>
</ul>
</li>
<li><a href="#error-messages-and-troubleshooting"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">错误消息和故障排除</font></font></a>
<ul dir="auto">
<li><a href="#low-battery"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">低电量</font></font></a></li>
<li><a href="#wifi-connection"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">无线网络连接</font></font></a></li>
<li><a href="#api-error"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">API错误</font></font></a></li>
<li><a href="#time-server-error"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">时间服务器错误</font></font></a></li>
</ul>
</li>
<li><a href="#licensing"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">许可</font></font></a></li>
</ul>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">设置指南</font></font></h2><a id="user-content-setup-guide" class="anchor" aria-label="永久链接：设置指南" href="#setup-guide"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">硬件</font></font></h3><a id="user-content-hardware" class="anchor" aria-label="永久链接：硬件" href="#hardware"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">7.5英寸(800×480)电子纸显示屏</font></font></p>
<ul dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">电子纸的优点</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">超低功耗 - 电子纸（又名电子墨水）显示器非常适合不需要频繁刷新显示器的低功耗应用。电子纸显示器仅在刷新显示器时消耗电力，并且没有背光。即使断电，图像仍会保留在屏幕上。</font></font></li>
</ul>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">电子纸的局限性：</font></font></p>
<ul dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">颜色 - 电子纸传统上仅限于黑白，但近年来，三色电子纸屏幕开始出现。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">刷新时间和重影 - 如果刷新太快，电子纸显示器很容易受到重影影响。为了避免这种情况，电子纸显示屏通常需要几秒钟的时间来刷新（本项目中使用的设备为 4 秒），并且会在黑白之间交替几次，这可能会分散注意力。</font></font></p>
</li>
</ul>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">面板支持：</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Waveshare 和 Good Display 生产同等的面板。任何一种变体都可以工作。</font></font></p>
<table>
<thead>
<tr>
<th><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">控制板</font></font></th>
<th><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">解决</font></font></th>
<th><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">颜色</font></font></th>
<th><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">笔记</font></font></th>
</tr>
</thead>
<tbody>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Waveshare 7.5英寸电子纸（v2）</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">800x480像素</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">黑，白</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可以</font></font><a href="https://www.waveshare.com/product/7.5inch-e-paper.htm" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在这里</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">找到。 （受到推崇的）</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">好显示7.5英寸电子纸(GDEY075T7)</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">800x480像素</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">黑，白</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可以</font></font><a href="https://www.aliexpress.com/item/3256802683908868.html" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在这里</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">找到。 （受到推崇的）</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Waveshare 7.5英寸电子纸(B)</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">800x480像素</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">红/黑/白</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可以</font></font><a href="https://www.waveshare.com/product/7.5inch-e-paper-b.htm" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在这里</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">找到。</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">好显示7.5英寸电子纸(GDEY075Z08)</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">800x480像素</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">红/黑/白</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可以</font></font><a href="https://www.aliexpress.com/item/3256803540460035.html" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在这里</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">找到。</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Waveshare 7.3英寸 ACeP 电子纸 (F)</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">800x480像素</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">7色</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可以</font></font><a href="https://www.waveshare.com/product/displays/e-paper/epaper-1/7.3inch-e-paper-f.htm" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在这里</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">找到。</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">好显示7.3英寸电子纸(GDEY073D46)</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">800x480像素</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">7色</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可以</font></font><a href="https://www.aliexpress.com/item/3256805485098421.html" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在这里</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">找到。</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Waveshare 7.5英寸电子纸（v1）</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">640x384像素</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">黑，白</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">支持有限。部分信息未显示，</font></font><a href="/lmarzen/esp32-weather-epd/blob/main/showcase/demo-waveshare75-version1.jpg"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">见图</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></td>
</tr>
<tr>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">好显示7.5英寸电子纸(GDEW075T8)</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">640x384像素</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">黑，白</font></font></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">支持有限。部分信息未显示，</font></font><a href="/lmarzen/esp32-weather-epd/blob/main/showcase/demo-waveshare75-version1.jpg"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">见图</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></td>
</tr>
</tbody>
</table>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该软件对强调色的支持有限。具有附加颜色的电子纸面板往往具有较长的刷新时间，这会缩短电池寿命。</font></font></p>
</li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">DESPI-C02 适配器板</font></font></p>
<ul dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">与 Waveshare HAT 相比，没有电平转换器，这使得它更适合 3.3V 处理器的低功耗使用。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Waveshare 开始发布其电子纸 HAT 的 2.3 版本。一些用户报告了此 HAT 的问题 ( </font></font><a href="https://github.com/lmarzen/esp32-weather-epd/issues/62" data-hovercard-type="issue" data-hovercard-url="/lmarzen/esp32-weather-epd/issues/62/hovercard"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">#62</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> )。</font></font></p>
</li>
<li>
<p dir="auto"><a href="https://www.e-paper-display.com/products_detail/productId=403.html" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">https://www.e-paper-display.com/products_detail/productId=403.html</font></font></a></p>
</li>
<li>
<p dir="auto"><a href="https://www.aliexpress.us/item/3256804446769469.html" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">https://www.aliexpress.us/item/3256804446769469.html</font></font></a></p>
</li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">FireBeetle 2 ESP32-E 微控制器</font></font></p>
<ul dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">为什么选择 ESP32？</font></font></p>
<ul dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">机载无线网络。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">520kB RAM和4MB FLASH，足以存储大量图标和字体。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">低功耗。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">体积小，有多种小型开发板可供选择。</font></font></p>
</li>
</ul>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">为什么选择 FireBeetle 2 ESP32-E</font></font></p>
<ul dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Drobot 的 FireBeetle ESP32 型号针对低功耗进行了优化 ( </font></font><a href="https://diyi0t.com/reduce-the-esp32-power-consumption/" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">https://diyi0t.com/reduce-the-esp32-power-conspiration/</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> )。 Drobot 的 FireBeetle 2 ESP32-E 变体提供 USB-C，但带有 Micro-USB 的旧版本主板也可以正常工作。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Firebeetle ESP32 型号包括用于 3.7v 锂离子 (LiPo) 电池的板载充电电路。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">FireBeetle ESP32 型号包括板载电路，用于监控连接到其 JST-PH2.0 连接器的电池的电池电压。</font></font></p>
</li>
</ul>
</li>
<li>
<p dir="auto"><a href="https://www.dfrobot.com/product-2195.html" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">https://www.dfrobot.com/product-2195.html</font></font></a></p>
</li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">BME280 - 压力、温度和湿度传感器</font></font></p>
<ul dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">提供准确的室内温度和湿度。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">比 DHT22 快得多，DHT22 需要等待 2 秒才能读取温度和湿度样本。</font></font></p>
</li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">3.7V 锂电池，带 2 针 JST 连接器</font></font></p>
<ul dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">大小由你决定。我使用了 5000mah 电池，因此设备一次充电可以运行超过 6 个月。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可以通过 USB-C 连接器将 FireBeetle ESP32 插入墙壁充电，同时将电池插入 ESP32 的 JST 连接器。</font></font></p>
<blockquote>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">警告</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
JST-PH2.0 连接器的极性未标准化！您可能需要交换连接器中电线的顺序。</font></font></p>
</blockquote>
</li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">支架/框架</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您需要一种很好的方式来展示您的项目。以下是一些流行的选择。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">DIY木制
</font></font><ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">我从底部掏空一块木头做了一个小支架。在背面，我使用了一根短的 USB 延长线，这样我就可以为电池充电，而无需从支架上拆下组件。我还连接了一个小的重置按钮来手动刷新显示。此外，我还用 3D 打印了底部的盖子，由磁铁固定。电子纸屏幕很薄，所以我用了一块薄的亚克力来支撑它。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">测量：
</font></font><ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">深度 = 63 毫米</font></font><br><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
高度 = 49 毫米</font></font><br><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
宽度 = 170.2 毫米（= 屏幕宽度）</font></font><br><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
屏幕角度 = 80 度</font></font><br><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
屏幕距离正面 15 毫米</font></font></li>
</ul>
</li>
</ul>
</li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可3D打印
</font></font><ul dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">这是社区设计的列表。</font></font></p>
<table>
<thead>
<tr>
<th><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">贡献者</font></font></th>
<th><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">关联</font></font></th>
</tr>
</thead>
<tbody>
<tr>
<td><a href="https://www.printables.com/@FrAllard_1585397" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">弗朗索瓦·阿拉德</font></font></a></td>
<td><a href="https://www.printables.com/model/791477-weather-station-using-a-esp32" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">印刷品</font></font></a></td>
</tr>
<tr>
<td><a href="https://www.printables.com/@3DNate_451157" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">3D 内特</font></font></a></td>
<td><a href="https://www.printables.com/model/661183-e-ink-weather-station-frame" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">印刷品</font></font></a></td>
</tr>
<tr>
<td><a href="https://github.com/Spanholz"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">斯文·F.</font></font></a></td>
<td><a href="https://www.printables.com/model/657756-case-for-esp32-weather-station" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">印刷品</font></font></a></td>
</tr>
<tr>
<td><a href="https://www.printables.com/@LayersStudio" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">图层工作室</font></font></a></td>
<td><a href="https://www.printables.com/model/655768-esp32-e-paper-weather-display-stand" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">印刷品</font></font></a></td>
</tr>
<tr>
<td><a href="https://www.printables.com/@PJVeltri_1590999" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PJ维尔特里</font></font></a></td>
<td><a href="https://www.printables.com/model/692944-base-and-display-holder-for-esp-32-e-paper-weather" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">印刷品</font></font></a></td>
</tr>
</tbody>
</table>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如果您想分享您自己的 3D 打印设计，我们非常鼓励并欢迎您做出贡献！</font></font></p>
</li>
</ul>
</li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">镜框</font></font></li>
</ul>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">接线</font></font></h3><a id="user-content-wiring" class="anchor" aria-label="永久链接：接线" href="#wiring"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"></font><a href="/lmarzen/esp32-weather-epd/blob/main/platformio/src/config.cpp"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">引脚连接在config.cpp</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">中定义</font><font style="vertical-align: inherit;">。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如果您使用的是 FireBeetle 2 ESP32-E，您可以使用我使用的连接或根据您的需要更改它们。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">我附上了 2 个接线图。一个用于 Waveshare HAT rev2.2，另一个使用推荐的 DESPI-C02。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">重要提示：Waveshare 电子纸驱动程序 HAT 有两个物理开关，必须正确设置才能使显示屏正常工作。</font></font></p>
<ul dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">显示配置：将开关设置至位置 B。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">接口配置：将开关设置到位置 0。</font></font></p>
</li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">重要信息：DESPI-C02 适配器有一个物理开关，必须正确设置该开关才能使显示器正常工作。</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">RESE：将开关设置到位置 0.47。</font></font></li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">剪掉低功耗垫以延长电池寿命。</font></font></p>
<ul dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">来自</font></font><a href="https://wiki.dfrobot.com/FireBeetle_Board_ESP32_E_SKU_DFR0654" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">https://wiki.dfrobot.com/FireBeetle_Board_ESP32_E_SKU_DFR0654</font></font></a></p>
<blockquote>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">低功耗垫：该垫专为低功耗而设计。默认情况下已连接。可以用小刀把中间的细线剪掉就可以断开了。断开后静态功耗可降低500μA。通过程序控制主控制器进入休眠模式后，功耗可降至13μA。注意：当板断开时，只能通过 USB 电源驱动 RGB LED 灯。</font></font></p>
</blockquote>
</li>
</ul>
<p dir="auto">
  <a target="_blank" rel="noopener noreferrer" href="/lmarzen/esp32-weather-epd/blob/main/showcase/wiring_diagram_despi-c02.png"><img src="/lmarzen/esp32-weather-epd/raw/main/showcase/wiring_diagram_despi-c02.png" width="49%" style="max-width: 100%;"></a>
  <a target="_blank" rel="noopener noreferrer" href="/lmarzen/esp32-weather-epd/blob/main/showcase/wiring_diagram_waveshare_rev22.png"><img src="/lmarzen/esp32-weather-epd/raw/main/showcase/wiring_diagram_waveshare_rev22.png" width="49%" style="max-width: 100%;"></a>
  <a target="_blank" rel="noopener noreferrer" href="/lmarzen/esp32-weather-epd/blob/main/showcase/demo-tucson.jpg"><img src="/lmarzen/esp32-weather-epd/raw/main/showcase/demo-tucson.jpg" width="32%" style="max-width: 100%;"></a>
</p>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">配置、编译、上传</font></font></h3><a id="user-content-configuration-compilation-and-upload" class="anchor" aria-label="永久链接：配置、编译和上传" href="#configuration-compilation-and-upload"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PlatformIO for VSCode 用于管理依赖项、代码编译和上传到 ESP32。</font></font></p>
<ol dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">克隆此存储库或下载并解压 .zip。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">安装 VSCode。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">按照以下说明安装 VSCode 的 PlatformIO 扩展：</font></font><a href="https://platformio.org/install/ide?install=vscode" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">https://platformio.org/install/ide? install=vscode</font></font></a></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在 VSCode 中打开项目。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">A。文件 &gt; 打开文件夹...</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">b.导航到该项目并选择名为“platformio”的文件夹。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">配置选项。</font></font></p>
<ul dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">大多数配置选项位于</font></font><a href="/lmarzen/esp32-weather-epd/blob/main/platformio/src/config.cpp"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">config.cpp</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">中，少数位于</font></font><a href="/lmarzen/esp32-weather-epd/blob/main/platformio/include/config.h"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">config.h</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">中。区域设置/语言选项也可以在 locales/locale_**.cpp 中找到。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在 config.cpp 中配置的重要设置：</font></font></p>
<ul dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">WiFi 凭证（ssid、密码）。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">打开天气图 API 密钥（它是免费的，请参阅下一节了解有关获取 API 密钥的重要说明）。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">纬度和经度。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">时间和日期格式。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">睡眠时长。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">电子纸 (SPI)、BME280 (I2C) 和电池电压 (ADC) 的引脚连接。</font></font></p>
</li>
</ul>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在 config.h 中配置的重要设置：</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">单位（公制或英制）。</font></font></li>
</ul>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">评论详细解释了每个选项。</font></font></p>
</li>
</ul>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">构建并上传代码。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">A。通过 USB 将 ESP32 连接到计算机。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">b.单击 VSCode 窗口底部的上传箭头。 （如果将鼠标悬停在其上方，应显示“PlatformIO：上传”。）</font></font></p>
<ul dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">PlatformIO会自动下载所需的第三方库，编译并上传代码。 :)</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">仅当您安装了 PlatformIO 扩展时您才会看到此内容。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如果您在上传过程中遇到错误，您可能需要安装驱动程序以允许您将代码上传到 ESP32。</font></font></p>
</li>
</ul>
</li>
</ol>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">OpenWeatherMap API 密钥</font></font></h3><a id="user-content-openweathermap-api-key" class="anchor" aria-label="永久链接：OpenWeatherMap API 密钥" href="#openweathermap-api-key"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在此注册以获取 API 密钥；免费。</font></font><a href="https://openweathermap.org/api" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">https://openweathermap.org/api</font></font></a></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该项目将调用 2 个不同的 API（“One Call”和“Air Pollution”）。</font></font></p>
<blockquote>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">注意</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
对于所有新的免费用户（2022 年夏季之后创建的帐户），OpenWeatherMap One Call 2.5 API 已弃用。幸运的是，您可以按照以下步骤免费每天对 One Call 3.0 API 进行 1,000 次调用。</font></font></p>
</blockquote>
<ul dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如果您在 2022 年夏季之前创建了帐户，则只需</font></font><code>OWM_ONECALL_VERSION = "2.5";</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在 config.cpp 中进行设置即可使用 One Call 2.5 API。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">否则，One Call API 3.0 仅包含在“One Call by Call”订阅中。此单独订阅包括每天 1,000 次免费调用，并且您只需为对该产品进行的 API 调用次数付费。</font></font></p>
</li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以下是如何订阅并避免任何信用卡更改的方法：</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">转到</font></font><a href="https://home.openweathermap.org/subscriptions/billing_info/onecall_30/base?key=base&amp;service=onecall_30" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">https://home.openweathermap.org/subscriptions/billing_info/onecall_30/base?key=base&amp;service=onecall_30</font></font></a></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">按照说明完成订阅。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">转到</font></font><a href="https://home.openweathermap.org/subscriptions" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">https://home.openweathermap.org/subscriptions</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">并将“每天调用次数（不超过）”设置为 1,000。这可以确保您永远不会超出免费通话的范围。</font></font></li>
</ul>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">错误消息和故障排除</font></font></h2><a id="user-content-error-messages-and-troubleshooting" class="anchor" aria-label="永久链接：错误消息和故障排除" href="#error-messages-and-troubleshooting"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">低电量</font></font></h3><a id="user-content-low-battery" class="anchor" aria-label="永久链接：电池电量低" href="#low-battery"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="/lmarzen/esp32-weather-epd/blob/main/showcase/demo-error-low-battery.jpg"><img src="/lmarzen/esp32-weather-epd/raw/main/showcase/demo-error-low-battery.jpg" align="left" width="25%" style="max-width: 100%;"></a></p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
一旦电池电压低于 LOW_BATTERY_VOLTAGE（默认 = 3.20v），就会出现此错误屏幕。在检测到电池电压高于 LOW_BATTERY_VOLTAGE 之前，显示屏不会再次刷新。当电池电压介于 LOW_BATTERY_VOLTAGE 和 VERY_LOW_BATTERY_VOLTAGE 之间（默认 = 3.10v）时，esp32 将深度睡眠 LOW_BATTERY_SLEEP_INTERVAL（默认 = 30 分钟），然后再次检查电池电压。如果电池电压落在 LOW_BATTERY_SLEEP_INTERVAL 和 CRIT_LOW_BATTERY_VOLTAGE 之间（默认 = 3.00v），则显示器将深度睡眠 VERY_LOW_BATTERY_SLEEP_INTERVAL 周期（默认 = 120 分钟）。如果电池电压低于 CRIT_LOW_BATTERY_VOLTAGE，则 esp32 将进入休眠模式，并且需要手动按下重置 (RST) 按钮才能再次开始更新。
</font></font><br clear="left">
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">无线网络连接</font></font></h3><a id="user-content-wifi-connection" class="anchor" aria-label="永久链接：WiFi 连接" href="#wifi-connection"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="/lmarzen/esp32-weather-epd/blob/main/showcase/demo-error-wifi.jpg"><img src="/lmarzen/esp32-weather-epd/raw/main/showcase/demo-error-wifi.jpg" align="left" width="25%" style="max-width: 100%;"></a></p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
当 ESP32 无法连接 WiFi 时，会出现此错误屏幕。如果消息显示“WiFi 连接失败”，则可能表示密码不正确。如果消息显示“SSID 不可用”，这可能表明您输错了 SSID 或者 esp32 超出了接入点的范围。 esp32 将在每个 SLEEP_DURATION 重试一次（默认 = 30 分钟）。
</font></font><br clear="left">
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">API错误</font></font></h3><a id="user-content-api-error" class="anchor" aria-label="永久链接：API 错误" href="#api-error"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="/lmarzen/esp32-weather-epd/blob/main/showcase/demo-error-api.jpg"><img src="/lmarzen/esp32-weather-epd/raw/main/showcase/demo-error-api.jpg" align="left" width="25%" style="max-width: 100%;"></a></p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
如果向 OpenWeatherMap 发出 API 请求时发生错误（客户端或服务器），则会出现此错误屏幕。第二行将给出错误代码，后跟描述符短语。正错误代码对应于 HTTP 响应状态代码，而错误代码 &lt;= 0 表示客户端（esp32）错误。 esp32 将在每个 SLEEP_DURATION 重试一次（默认 = 30 分钟）。
</font></font><br><br><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
在左侧所示的示例中，“401：未经授权”可能是由于 API 密钥不正确或您在未正确设置帐户的情况下尝试使用 One Call v3 API 造成的。
</font></font><br clear="left">
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">时间服务器错误</font></font></h3><a id="user-content-time-server-error" class="anchor" aria-label="永久链接：时间服务器错误" href="#time-server-error"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="/lmarzen/esp32-weather-epd/blob/main/showcase/demo-error-time.jpg"><img src="/lmarzen/esp32-weather-epd/raw/main/showcase/demo-error-time.jpg" align="left" width="25%" style="max-width: 100%;"></a></p><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
当 esp32 无法从 NTP_SERVER_1/NTP_SERVER_2 获取时间时，会出现此错误屏幕。有时上传到 esp32 后立即会出现此错误；在这种情况下，只需点击重置按钮或等待 SLEEP_DURATION（默认 = 30 分钟）和 esp32 自动重试。如果错误仍然存&ZeroWidthSpace;&ZeroWidthSpace;在，请尝试选择更近/延迟时间更低的服务器或增加 NTP_TIMEOUT。
</font></font><br clear="left">
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">许可</font></font></h2><a id="user-content-licensing" class="anchor" aria-label="永久链接：许可" href="#licensing"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"></font><a href="/lmarzen/esp32-weather-epd/blob/main/LICENSE"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">esp32-weather-epd 根据GNU 通用公共许可证 v3.0</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">获得许可，</font><font style="vertical-align: inherit;">其工具、字体和图标的许可证如下：</font></font></p>
<table>
<thead>
<tr>
<th><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">姓名</font></font></th>
<th><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">执照</font></font></th>
<th><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">描述</font></font></th>
</tr>
</thead>
<tbody>
<tr>
<td><a href="https://github.com/adafruit/Adafruit-GFX-Library/tree/master/fontconvert"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Adafruit-GFX-Library：字体转换</font></font></a></td>
<td><a href="/lmarzen/esp32-weather-epd/blob/main/fonts/fontconvert/license.txt"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">BSD 许可证</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">用于预处理字体的 CLI 工具，与 Adafruit_GFX Arduino 库一起使用。</font></font></td>
</tr>
<tr>
<td><a href="https://github.com/lmarzen/pollutant-concentration-to-aqi"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">污染物浓度换算成空气质量</font></font></a></td>
<td><a href="/lmarzen/esp32-weather-epd/blob/main/platformio/lib/pollutant-concentration-to-aqi/LICENSE"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">GNU 较宽松通用公共许可证 v2.1</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将污染物浓度转换为空气质量指数 (AQI) 的 C 库。</font></font></td>
</tr>
<tr>
<td><a href="https://www.gnu.org/software/freefont/" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">GNU 自由字体</font></font></a></td>
<td><a href="https://www.gnu.org/software/freefont/license.html" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">GNU 通用公共许可证 v3.0</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">字体系列</font></font></td>
</tr>
<tr>
<td><a href="https://fonts.google.com/specimen/Lato" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">拉托</font></font></a></td>
<td><a href="http://scripts.sil.org/OFL" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SIL OFL v1.1</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">字体系列</font></font></td>
</tr>
<tr>
<td><a href="https://fonts.google.com/specimen/Montserrat" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">蒙特塞拉特</font></font></a></td>
<td><a href="http://scripts.sil.org/OFL" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SIL OFL v1.1</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">字体系列</font></font></td>
</tr>
<tr>
<td><a href="https://fonts.google.com/specimen/Open+Sans" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">打开无字体</font></font></a></td>
<td><a href="http://scripts.sil.org/OFL" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SIL OFL v1.1</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">字体系列</font></font></td>
</tr>
<tr>
<td><a href="https://fonts.google.com/specimen/Poppins" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">波平斯</font></font></a></td>
<td><a href="http://scripts.sil.org/OFL" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SIL OFL v1.1</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">字体系列</font></font></td>
</tr>
<tr>
<td><a href="https://fonts.google.com/specimen/Quicksand" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">流沙</font></font></a></td>
<td><a href="http://scripts.sil.org/OFL" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SIL OFL v1.1</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">字体系列</font></font></td>
</tr>
<tr>
<td><a href="https://fonts.google.com/specimen/Raleway" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">铁路道</font></font></a></td>
<td><a href="http://scripts.sil.org/OFL" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SIL OFL v1.1</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">字体系列</font></font></td>
</tr>
<tr>
<td><a href="https://fonts.google.com/specimen/Roboto" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">罗博托</font></font></a></td>
<td><a href="https://www.apache.org/licenses/LICENSE-2.0" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Apache 许可证 v2.0</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">字体系列</font></font></td>
</tr>
<tr>
<td><a href="https://fonts.google.com/specimen/Roboto+Mono" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">机器人单声道</font></font></a></td>
<td><a href="https://www.apache.org/licenses/LICENSE-2.0" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Apache 许可证 v2.0</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">字体系列</font></font></td>
</tr>
<tr>
<td><a href="https://fonts.google.com/specimen/Roboto+Slab" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">机器人板</font></font></a></td>
<td><a href="https://www.apache.org/licenses/LICENSE-2.0" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Apache 许可证 v2.0</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">字体系列</font></font></td>
</tr>
<tr>
<td><a href="https://design.ubuntu.com/font" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Ubuntu字体</font></font></a></td>
<td><a href="https://ubuntu.com/legal/font-licence" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Ubuntu 字体许可证 v1.0</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">字体系列</font></font></td>
</tr>
<tr>
<td><a href="https://github.com/erikflowers/weather-icons"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">天气主题图标</font></font></a></td>
<td><a href="http://scripts.sil.org/OFL" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SIL OFL v1.1</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">(wi-**.svg) 天气图标系列，作者：Lukas Bischoff/Erik Flowers。</font></font></td>
</tr>
<tr>
<td><a href="https://fonts.google.com/icons" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">谷歌图标</font></font></a></td>
<td><a href="https://www.apache.org/licenses/LICENSE-2.0" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Apache 许可证 v2.0</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">（电池**.svg、visibility_icon.svg）来自 Google Icon 的电池和可见性图标。</font></font></td>
</tr>
<tr>
<td><a href="https://svgsilh.com/image/37775.html" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">生物危害符号</font></font></a></td>
<td><a href="https://en.wikipedia.org/wiki/Public_domain" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">CC0 v1.0</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">(biological_hazard_symbol.svg) 生物危害图标。</font></font></td>
</tr>
<tr>
<td><a href="https://seekicon.com/free-icon/house_16" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">房子图标</font></font></a></td>
<td><a href="http://opensource.org/licenses/mit-license.html" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">麻省理工学院许可证</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">(house.svg) 房子图标。</font></font></td>
</tr>
<tr>
<td><a href="/lmarzen/esp32-weather-epd/blob/main/icons/svg"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">室内温度/湿度图标</font></font></a></td>
<td><a href="http://scripts.sil.org/OFL" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SIL OFL v1.1</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">(house_**.svg) 室内温度/湿度图标。</font></font></td>
</tr>
<tr>
<td><a href="https://svgsilh.com/image/309911.html" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">电离辐射符号</font></font></a></td>
<td><a href="https://creativecommons.org/publicdomain/zero/1.0/" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">CC0 v1.0</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">(ionizing_radiation_symbol.svg) 电离辐射图标。</font></font></td>
</tr>
<tr>
<td><a href="https://github.com/phosphor-icons/homepage"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">荧光粉图标</font></font></a></td>
<td><a href="http://opensource.org/licenses/mit-license.html" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">麻省理工学院许可证</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">（wifi**.svg、warning_icon.svg、error_icon.svg）来自 Phosphor Icons 的 WiFi、警告和错误图标。</font></font></td>
</tr>
<tr>
<td><a href="https://www.onlinewebfonts.com/icon/251550" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">风向图标</font></font></a></td>
<td><a href="http://creativecommons.org/licenses/by/3.0" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">抄送v3.0</font></font></a></td>
<td><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">(meteorological_wind_direction_**deg.svg) 来自在线网络字体的气象风向图标。</font></font></td>
</tr>
</tbody>
</table>
</article></div>
