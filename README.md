# 定制适合 [mihomo 内核](https://github.com/MetaCubeX/mihomo)和 [sing-box 内核](https://github.com/SagerNet/sing-box)的 ruleset&geodata 文件

---

# 一、 geodata 文件说明
## 1. 文件类型
① [mihomo](https://github.com/MetaCubeX/mihomo) geodata 文件，包括：geosite.dat、geoip.dat、Country.mmdb 和 geoip.metadb、ASN.mmdb（仅限 mihomo 内核）等  
② [sing-box](https://github.com/SagerNet/sing-box) geodata 文件，包括：geosite.db 和 geoip.db 等
## 2. 数据源
① 每天凌晨 3 点（北京时间 UTC+8）自动构建，根据 [Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat) 和 [Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip) 进行深度定制，可点击查看包含的[域名列表](https://github.com/DustinWin/domain-list-custom/tree/domains)和 [IP 段列表](https://github.com/DustinWin/geoip/tree/ips)  
② `geosite,fakeip-filter,📌 fakeip 过滤` 源采用 [ShellCrash/public/fake_ip_filter.list](https://github.com/juewuy/ShellCrash/blob/dev/public/fake_ip_filter.list)（搭载 mihomo 内核或 [sing-box PuerNya 版内核](https://github.com/PuerNya/sing-box/tree/building)时，可使该规则集内的域名走 realip）  
③ `geosite,fakeip-filter-lite,📌 fakeip 过滤` 源采用 [ShellCrash/public/fake_ip_filter.list](https://github.com/juewuy/ShellCrash/blob/dev/public/fake_ip_filter.list)，仅保留主要域名（推荐搭配 [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome) 且 DNS 配置 mix 混合模式时使用）  
④ `geosite,private,🔒 私有网络` 源采用 [v2fly/domain-list-community/private](https://github.com/v2fly/domain-list-community/blob/master/data/private) 和 [blackmatrix7/ios_rule_script/Lan](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Lan)（仅域名）组合，并添加主流 [Dashboard 在线面板](https://github.com/DustinWin/proxy-tools/releases/tag/Dashboard)域名（`yacd.haishan.me`、`yacd.metacubex.one`、`d.metacubex.one`、`metacubex.github.io`、`metacubexd.pages.dev` 和 `board.zash.run.place`）  
⑤ `geosite,ads,🛑 广告域名` 源采用 [privacy-protection-tools/anti-AD](https://github.com/privacy-protection-tools/anti-AD)  
⑥ `geosite,trackerslist,📋 Trackerslist` 源采用 [XIU2/TrackersListCollection](https://github.com/XIU2/TrackersListCollection/blob/master/all.txt)（仅域名）和 [ngosang/trackerslist](https://github.com/ngosang/trackerslist/blob/master/trackers_all.txt) 组合  
⑦ `geosite,microsoft-cn,🪟 微软服务` 源采用 [v2fly/domain-list-community/microsoft@cn](https://github.com/v2fly/domain-list-community/blob/master/data/microsoft)  
⑧ `geosite,apple-cn,🍎 苹果服务` 源采用 [v2fly/domain-list-community/apple@cn](https://github.com/v2fly/domain-list-community/blob/master/data/apple)  
⑨ `geosite,google-cn,🇬 谷歌服务` 源采用 [v2fly/domain-list-community/google@cn](https://github.com/v2fly/domain-list-community/blob/master/data/google)  
⑩ `geosite,games-cn,🎮 游戏服务` 源采用 [v2fly/domain-list-community/category-games@cn](https://github.com/v2fly/domain-list-community/blob/master/data/category-games)、[blackmatrix7/ios_rule_script/SteamCN](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/SteamCN) 和 [blackmatrix7/ios_rule_script/GameDownloadCN](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Game/GameDownloadCN) 组合  
⑪ `geosite,netflix,🎥 奈飞视频` 源采用 [blackmatrix7/ios_rule_script/Netflix](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Netflix)  
⑫ `geosite,disney,📽️ 迪士尼+` 源采用 [blackmatrix7/ios_rule_script/Disney](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Disney)  
⑬ `geosite,max,🎞️ Max` 源采用 [blackmatrix7/ios_rule_script/HBO](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/HBO)  
⑭ `geosite,primevideo,🎬 Prime Video` 源采用 [blackmatrix7/ios_rule_script/PrimeVideo](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/PrimeVideo)  
⑮ `geosite,appletv,🍎 Apple TV+` 源采用 [blackmatrix7/ios_rule_script/AppleTV](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/AppleTV)  
⑯ `geosite,youtube,📹 油管视频` 源采用 [blackmatrix7/ios_rule_script/YouTube](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/YouTube)  
⑰ `geosite,tiktok,🎵 TikTok` 源采用 [blackmatrix7/ios_rule_script/TikTok](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/TikTok)  
⑱ `geosite,bilibili,📺 哔哩哔哩` 源采用 [blackmatrix7/ios_rule_script/BiliBili](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/BiliBili)  
⑲ `geosite,ai,🤖 人工智能` 源采用 [blackmatrix7/ios_rule_script/OpenAI](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/OpenAI)、[blackmatrix7/ios_rule_script/Copilot](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Copilot)、[blackmatrix7/ios_rule_script/Gemini](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Gemini) 和 [blackmatrix7/ios_rule_script/Claude](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Claude) 组合  
⑳ `geosite,networktest,📈 网络测试` 源采用 [v2fly/domain-list-community/speedtest](https://github.com/v2fly/domain-list-community/blob/master/data/speedtest)、[blackmatrix7/ios_rule_script/Speedtest](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Speedtest) 和 IPv6 测试域名关键字（`keyword`，包括：`ipv6-test`、`test-ipv6`、`ipv6test` 和 `testipv6`）组合  
㉑ `geosite,tld-proxy,🧱 代理顶级域名` 源采用 [v2fly/domain-list-community/tld-!cn](https://github.com/v2fly/domain-list-community/blob/master/data/tld-!cn)  
㉒ `geosite,proxy,🧱 代理域名` 源采用 [v2fly/domain-list-community/geolocation-!cn](https://github.com/v2fly/domain-list-community/blob/master/data/geolocation-!cn)（删除了带有 `@cn` 和 `@ads` 的域名，并新增了 [v2fly/domain-list-community/cn](https://github.com/v2fly/domain-list-community/blob/master/data/cn) 中带有 `@!cn` 的域名）、[gfwlist](https://github.com/gfwlist/gfwlist) 和 [blackmatrix7/ios_rule_script/Global](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Global) 组合  
㉓ `geosite,tld-cn,🛡️ 直连顶级域名` 源采用 [v2fly/domain-list-community/tld-cn](https://github.com/v2fly/domain-list-community/blob/master/data/tld-cn)  
㉔ `geosite,cn,🛡️ 直连域名` 源采用 [v2fly/domain-list-community/cn](https://github.com/v2fly/domain-list-community/blob/master/data/cn)（删除了带有 `@!cn` 和 `@ads` 的域名，并新增了 v2fly/domain-list-community/geolocation-!cn 中带有 `@cn` 的域名）和 [blackmatrix7/ios_rule_script/ChinaMax](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/ChinaMax)（仅域名）组合  
㉕ `geoip,private,🔒 私有网络` 源采用 [DustinWin/geoip/config.json](https://github.com/DustinWin/geoip/blob/master/config.json) 中的 `input.type:private` 和 [TrackersList](https://github.com/XIU2/TrackersListCollection/blob/master/all.txt)（仅 IP）组合  
㉖ `geoip,cn,🀄️ 直连 IP` 源采用 [GeoLite2-Country-CSV/CN](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data)、[17mon/china_ip_list](https://github.com/17mon/china_ip_list)、[gaoyifan/china-operator-ip](https://github.com/gaoyifan/china-operator-ip)、[APNIC/CN](http://ftp.apnic.net/stats/apnic/delegated-apnic-latest) 和 [blackmatrix7/ios_rule_script/ChinaASN](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Surge/ChinaASN) 组合  
㉗ `geoip,netflix,🎥 奈飞视频` 源采用 [GeoLite2-ASN-CSV/Netflix](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data) 和 [blackmatrix7/ios_rule_script/Netflix](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Netflix)（Netflix_IP.txt）组合  
㉘ `geoip,telegram,📲 电报消息` 源采用 [GeoLite2-ASN-CSV/Telegram](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data) 和 [Telegram IP 段](https://core.telegram.org/resources/cidr.txt)组合
## 3. 文件下载
**规则集文件包含的规则和下载地址对应关系如下表：**
<table>
  <tr>
    <td><b>规则集文件名称</b></td>
    <td align="center"><b>包含规则</b></td>
    <td><b>GitHub 源</b></td>
    <td><b>jsDelivr 源</b></td>
    <td><b>GitHub Proxy 源</b></td>
  </tr>
  <tr>
    <td>geosite-all.dat</td>
    <td><code>fakeip-filter</code>、<code>fakeip-filter-lite</code>、<code>private</code>、<code>ads</code>、<code>trackerslist</code>、<code>microsoft-cn</code>、<code>apple-cn</code>、<code>google-cn</code>、<code>games-cn</code>、<code>netflix</code>、<code>disney</code>、<code>max</code>、<code>primevideo</code>、<code>appletv</code>、<code>youtube</code>、<code>tiktok</code>、<code>bilibili</code>、<code>ai</code>、<code>networktest</code>、<code>tld-proxy</code>、<code>proxy</code>、<code>tld-cn</code> 和 <code>cn</code></td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geosite-all.dat">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/geosite-all.dat">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geosite-all.dat">点此下载</a></td>
  </tr>
  <tr>
    <td>geosite-all.db</td>
    <td><code>fakeip-filter</code>、<code>fakeip-filter-lite</code>、<code>private</code>、<code>ads</code>、<code>trackerslist</code>、<code>microsoft-cn</code>、<code>apple-cn</code>、<code>google-cn</code>、<code>games-cn</code>、<code>netflix</code>、<code>disney</code>、<code>max</code>、<code>primevideo</code>、<code>appletv</code>、<code>youtube</code>、<code>tiktok</code>、<code>bilibili</code>、<code>ai</code>、<code>networktest</code>、<code>tld-proxy</code>、<code>proxy</code>、<code>tld-cn</code> 和 <code>cn</code></td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box/geosite-all.db">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@sing-box/geosite-all.db">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box/geosite-all.db">点此下载</a></td>
  </tr>
  <tr>
    <td>geosite-all-lite.dat</td>
    <td><code>fakeip-filter</code>、<code>fakeip-filter-lite</code>、<code>private</code>、<del><code>ads</code></del>、<code>trackerslist</code>、<code>microsoft-cn</code>、<code>apple-cn</code>、<code>google-cn</code>、<code>games-cn</code>、<code>netflix</code>、<code>disney</code>、<code>max</code>、<code>primevideo</code>、<code>appletv</code>、<code>youtube</code>、<code>tiktok</code>、<code>bilibili</code>、<code>ai</code>、<code>networktest</code>、<code>tld-proxy</code>、<code>proxy</code>、<code>tld-cn</code> 和 <code>cn</code></td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geosite-all-lite.dat">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/geosite-all-lite.dat">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geosite-all-lite.dat">点此下载</a></td>
  </tr>
  <tr>
    <td>geosite-all-lite.db</td>
    <td><code>fakeip-filter</code>、<code>fakeip-filter-lite</code>、<code>private</code>、<del><code>ads</code></del>、<code>trackerslist</code>、<code>microsoft-cn</code>、<code>apple-cn</code>、<code>google-cn</code>、<code>games-cn</code>、<code>netflix</code>、<code>disney</code>、<code>max</code>、<code>primevideo</code>、<code>appletv</code>、<code>youtube</code>、<code>tiktok</code>、<code>bilibili</code>、<code>ai</code>、<code>networktest</code>、<code>tld-proxy</code>、<code>proxy</code>、<code>tld-cn</code> 和 <code>cn</code></td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box/geosite-all-lite.db">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@sing-box/geosite-all-lite.db">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box/geosite-all-lite.db">点此下载</a></td>
  </tr>
  <tr>
    <td>geosite.dat</td>
    <td><code>fakeip-filter</code>、<code>fakeip-filter-lite</code>、<code>private</code>、<code>ads</code>、<code>trackerslist</code>、<code>microsoft-cn</code>、<code>apple-cn</code>、<code>google-cn</code>、<code>games-cn</code>、<code>ai</code>、<code>networktest</code>、<code>tld-proxy</code>、<code>proxy</code>、<code>tld-cn</code> 和 <code>cn</code></td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geosite.dat">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/geosite.dat">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geosite.dat">点此下载</a></td>
  </tr>
  <tr>
    <td>geosite.db</td>
    <td><code>fakeip-filter</code>、<code>fakeip-filter-lite</code>、<code>private</code>、<code>ads</code>、<code>trackerslist</code>、<code>microsoft-cn</code>、<code>apple-cn</code>、<code>google-cn</code>、<code>games-cn</code>、<code>ai</code>、<code>networktest</code>、<code>tld-proxy</code>、<code>proxy</code>、<code>tld-cn</code> 和 <code>cn</code></td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box/geosite.db">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@sing-box/geosite.db">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box/geosite.db">点此下载</a></td>
  </tr>
  <tr>
    <td>geosite-lite.dat</td>
    <td><code>fakeip-filter</code>、<code>fakeip-filter-lite</code>、<code>private</code>、<del><code>ads</code></del>、<code>trackerslist</code>、<code>microsoft-cn</code>、<code>apple-cn</code>、<code>google-cn</code>、<code>games-cn</code>、<code>ai</code>、<code>networktest</code>、<code>tld-proxy</code>、<code>proxy</code>、<code>tld-cn</code> 和 <code>cn</code></td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geosite-lite.dat">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/geosite-lite.dat">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geosite-lite.dat">点此下载</a></td>
  </tr>
  <tr>
    <td>geosite-lite.db</td>
    <td><code>fakeip-filter</code>、<code>fakeip-filter-lite</code>、<code>private</code>、<del><code>ads</code></del>、<code>trackerslist</code>、<code>microsoft-cn</code>、<code>apple-cn</code>、<code>google-cn</code>、<code>games-cn</code>、<code>ai</code>、<code>networktest</code>、<code>tld-proxy</code>、<code>proxy</code>、<code>tld-cn</code> 和 <code>cn</code></td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box/geosite-lite.db">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@sing-box/geosite-lite.db">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box/geosite-lite.db">点此下载</a></td>
  </tr>
  <tr>
    <td>geoip-all.dat</td>
    <td rowspan="4" align="center"><a href="https://github.com/Loyalsoldier/geoip/tree/release/text">点此查看</a></td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geoip-all.dat">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/geoip-all.dat">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geoip-all.dat">点此下载</a></td>
  </tr>
  <tr>
    <td>Country-all.mmdb</td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/Country-all.mmdb">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/Country-all.mmdb">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/Country-all.mmdb">点此下载</a></td>
  </tr>
  <tr>
    <td>geoip-all.metadb</td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geoip-all.metadb">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/geoip-all.metadb">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geoip-all.metadb">点此下载</a></td>
  </tr>
  <tr>
    <td>geoip-all.db</td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box/geoip-all.db">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@sing-box/geoip-all.db">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box/geoip-all.db">点此下载</a></td>
  </tr>
  <tr>
    <td>Country-ASN-all.mmdb</td>
    <td><code>cloudflare</code></del>、<code>cloudfront</code>、<code>facebook</code>、<code>fastly</code>、<code>google</code>、<code>netflix</code>、<code>telegram</code> 和 <code>twitter</code>，具体可<a href="https://github.com/Loyalsoldier/geoip/blob/master/asn.csv">点此查看</a></td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/Country-ASN-all.mmdb">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/Country-ASN-all.mmdb">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/Country-ASN-all.mmdb">点此下载</a></td>
  </tr>
  <tr>
    <td>geoip.dat</td>
    <td rowspan="4"><code>private</code>、<code>cn</code>、<code>netflix</code> 和 <code>telegram</code></td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geoip.dat">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/geoip.dat">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geoip.dat">点此下载</a></td>
  </tr>
  <tr>
    <td>Country.mmdb</td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/Country.mmdb">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/Country.mmdb">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/Country.mmdb">点此下载</a></td>
  </tr>
  <tr>
    <td>geoip.metadb</td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geoip.metadb">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/geoip.metadb">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geoip.metadb">点此下载</a></td>
  </tr>
  <tr>
    <td>geoip.db</td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box/geoip.db">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@sing-box/geoip.db">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box/geoip.db">点此下载</a></td>
  </tr>
  <tr>
    <td>geoip-lite.dat</td>
    <td rowspan="4"><code>private</code>、<code>cn</code>、<del><code>netflix</code></del> 和 <code>telegram</code></td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geoip-lite.dat">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/geoip-lite.dat">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geoip-lite.dat">点此下载</a></td>
  </tr>
  <tr>
    <td>Country-lite.mmdb</td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/Country-lite.mmdb">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/Country-lite.mmdb">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/Country-lite.mmdb">点此下载</a></td>
  </tr>
  <tr>
    <td>geoip-lite.metadb</td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geoip-lite.metadb">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/geoip-lite.metadb">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/geoip-lite.metadb">点此下载</a></td>
  </tr>
  <tr>
    <td>geoip-lite.db</td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box/geoip-lite.db">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@sing-box/geoip-lite.db">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box/geoip-lite.db">点此下载</a></td>
  </tr>
  <tr>
    <td>Country-ASN.mmdb</td>
    <td><del><code>private</code></del>、<del><code>cn</code></del>、<code>netflix</code> 和 <code>telegram</code>，具体可<a href="https://github.com/DustinWin/geoip/blob/master/asn.csv">点此查看</a></td>
    <td><a href="https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/Country-ASN.mmdb">点此下载</a></td>
    <td><a href="https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/Country-ASN.mmdb">点此下载</a></td>
    <td><a href="https://ghfast.top/https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo/Country-ASN.mmdb">点此下载</a></td>
  </tr>
</table>

## 4. 文件导入
<details>
<summary>① 导入到 Linux 端（以 <a href="https://github.com/juewuy/ShellCrash">ShellCrash</a> 导入 geosite.dat、geoip.dat、Country.mmdb、geoip.metadb、ASN.mmdb 和 geosite.db、geoip.db 为例）</summary>

连接 SSH 后执行如下命令：
```
# 适用于 mihomo 内核
curl -o $CRASHDIR/GeoSite.dat -L https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/geosite.dat
curl -o $CRASHDIR/GeoIP.dat -L https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/geoip.dat
curl -o $CRASHDIR/Country.mmdb -L https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/Country.mmdb
curl -o $CRASHDIR/geoip.metadb -L https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/geoip.metadb
curl -o $CRASHDIR/ASN.mmdb -L https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/Country-ASN.mmdb
# 适用于 sing-box 内核
curl -o $CRASHDIR/geosite.db -L https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@sing-box/geosite.db
curl -o $CRASHDIR/geoip.db -L https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@sing-box/geoip.db
$CRASHDIR/start.sh restart
```
</details>
<details>
<summary>② 导入到 Windows 端（以 <a href="https://github.com/clash-verge-rev/clash-verge-rev">Clash Verge</a> 导入 geosite.dat、geoip.dat、Country.mmdb、geoip.metadb 和 ASN.mmdb 为例）</summary>

以管理员身份运行 CMD 命令提示符，执行如下命令：
```
taskkill /f /t /im "Clash Verge*"
taskkill /f /t /im clash-verge*
taskkill /f /t /im verge-mihomo*
curl -o %APPDATA%\io.github.clash-verge-rev.clash-verge-rev\geosite.dat -L https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/geosite.dat
curl -o %APPDATA%\io.github.clash-verge-rev.clash-verge-rev\geoip.dat -L https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/geoip.dat
curl -o %APPDATA%\io.github.clash-verge-rev.clash-verge-rev\Country.mmdb -L https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/Country.mmdb
curl -o %APPDATA%\io.github.clash-verge-rev.clash-verge-rev\geoip.metadb -L https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/geoip.metadb
curl -o %APPDATA%\io.github.clash-verge-rev.clash-verge-rev\ASN.mmdb -L https://cdn.jsdelivr.net/gh/DustinWin/ruleset_geodata@mihomo/Country-ASN.mmdb
```
</details>

# 二、 ruleset 规则集文件说明
## 1. 文件类型
① [mihomo](https://github.com/MetaCubeX/mihomo) rule-set 规则集文件，格式为 `.yaml`（`format: yaml`）、`.list`（`format: text`） 和 `.mrs`（`format: mrs`）  
② [sing-box](https://github.com/SagerNet/sing-box) rule_set 规则集文件，格式有 `.srs`（`"format": "binary"`）和 `.json`（`"format": "source"`）
## 2. 数据源
① 每天凌晨 3 点（北京时间 UTC+8）自动构建，根据 [Loyalsoldier/clash-rules](https://github.com/Loyalsoldier/clash-rules) 和 [Loyalsoldier/geoip](https://github.com/Loyalsoldier/geoip) 进行深度定制，可点击查看包含的[域名列表](https://github.com/DustinWin/domain-list-custom/tree/domains)和 [IP 段列表](https://github.com/DustinWin/geoip/tree/ips)  
② `rule-set,fakeip-filter,📌 fakeip 过滤` 源采用 [ShellCrash/public/fake_ip_filter.list](https://github.com/juewuy/ShellCrash/blob/dev/public/fake_ip_filter.list)（搭载 mihomo 内核或 sing-box PuerNya 版内核时，可使该规则集内的域名走 realip）  
③ `rule-set,fakeip-filter-lite,📌 fakeip 过滤` 源采用 [ShellCrash/public/fake_ip_filter.list](https://github.com/juewuy/ShellCrash/blob/dev/public/fake_ip_filter.list)，仅保留主要域名（推荐搭配 [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome) 且 DNS 配置 mix 混合模式时使用）  
④ `rule-set,private,🔒 私有网络` 源采用 [v2fly/domain-list-community/private](https://github.com/v2fly/domain-list-community/blob/master/data/private) 和 [blackmatrix7/ios_rule_script/Lan](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Lan)（仅域名）组合，并添加主流 [Dashboard 在线面板](https://github.com/DustinWin/proxy-tools/releases/tag/Dashboard)域名（`yacd.haishan.me`、`yacd.metacubex.one`、`d.metacubex.one`、`metacubex.github.io`、`metacubexd.pages.dev`和 `board.zash.run.place`）  
⑤ `rule-set,ads,🛑 广告域名` 源采用 [privacy-protection-tools/anti-AD](https://github.com/privacy-protection-tools/anti-AD)  
⑥ `rule-set,trackerslist,📋 Trackerslist` 源采用 [XIU2/TrackersListCollection](https://github.com/XIU2/TrackersListCollection/blob/master/all.txt)（仅域名）和 [ngosang/trackerslist](https://github.com/ngosang/trackerslist/blob/master/trackers_all.txt) 组合  
⑦ `rule-set,applications,⬇️ 直连软件` 源采用 [blackmatrix7/ios_rule_script/Download](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Download) 和 [Loyalsoldier/clash-rules/applications.txt](https://github.com/Loyalsoldier/clash-rules/blob/release/applications.txt) 组合  
⑧ `rule-set,microsoft-cn,🪟 微软服务` 源采用 [v2fly/domain-list-community/microsoft@cn](https://github.com/v2fly/domain-list-community/blob/master/data/microsoft)  
⑨ `rule-set,apple-cn,🍎 苹果服务` 源采用 [v2fly/domain-list-community/apple@cn](https://github.com/v2fly/domain-list-community/blob/master/data/apple)  
⑩ `rule-set,google-cn,🇬 谷歌服务` 源采用 [v2fly/domain-list-community/google@cn](https://github.com/v2fly/domain-list-community/blob/master/data/google)  
⑪ `rule-set,games-cn,🎮 游戏服务` 源采用 [v2fly/domain-list-community/category-games@cn](https://github.com/v2fly/domain-list-community/blob/master/data/category-games)、[blackmatrix7/ios_rule_script/SteamCN](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/SteamCN) 和 [blackmatrix7/ios_rule_script/GameDownloadCN](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Game/GameDownloadCN) 组合  
⑫ `rule-set,netflix,🎥 奈飞视频` 源采用 [blackmatrix7/ios_rule_script/Netflix](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Netflix)（仅域名）  
⑬ `rule-set,disney,📽️ 迪士尼+` 源采用 [blackmatrix7/ios_rule_script/Disney](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Disney)  
⑭ `rule-set,max,🎞️ Max` 源采用 [blackmatrix7/ios_rule_script/HBO](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/HBO)  
⑮ `rule-set,primevideo,🎬 Prime Video` 源采用 [blackmatrix7/ios_rule_script/PrimeVideo](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/PrimeVideo)  
⑯ `rule-set,appletv,🍎 Apple TV+` 源采用 [blackmatrix7/ios_rule_script/AppleTV](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/AppleTV)  
⑰ `rule-set,youtube,📹 油管视频` 源采用 [blackmatrix7/ios_rule_script/YouTube](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/YouTube)  
⑱ `rule-set,tiktok,🎵 TikTok` 源采用 [blackmatrix7/ios_rule_script/TikTok](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/TikTok)  
⑲ `rule-set,bilibili,📺 哔哩哔哩` 源采用 [blackmatrix7/ios_rule_script/BiliBili](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/BiliBili)  
⑳ `rule-set,ai,🤖 人工智能` 源采用 [blackmatrix7/ios_rule_script/OpenAI](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/OpenAI)、[blackmatrix7/ios_rule_script/Copilot](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Copilot)、[blackmatrix7/ios_rule_script/Gemini](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Gemini) 和 [blackmatrix7/ios_rule_script/Claude](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Claude) 组合  
㉑ `rule-set,networktest,📈 网络测试` 源采用 [v2fly/domain-list-community/speedtest](https://github.com/v2fly/domain-list-community/blob/master/data/speedtest)、[blackmatrix7/ios_rule_script/Speedtest](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Speedtest) 和 IPv6 测试域名关键字（`keyword`，包括：`ipv6-test`、`test-ipv6`、`ipv6test` 和 `testipv6`）组合  
㉒ `rule-set,tld-proxy,🧱 代理顶级域名` 源采用 [v2fly/domain-list-community/tld-!cn](https://github.com/v2fly/domain-list-community/blob/master/data/tld-!cn)  
㉓ `rule-set,proxy,🧱 代理域名` 源采用 [v2fly/domain-list-community/geolocation-!cn](https://github.com/v2fly/domain-list-community/blob/master/data/geolocation-!cn)（删除了带有 `@cn` 和 `@ads` 的域名，并新增了 [v2fly/domain-list-community/cn](https://github.com/v2fly/domain-list-community/blob/master/data/cn) 中带有 `@!cn` 的域名）、[gfwlist](https://github.com/gfwlist/gfwlist) 和 [blackmatrix7/ios_rule_script/Global](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Global) 组合  
㉔ `rule-set,tld-cn,🛡️ 直连顶级域名` 源采用 [v2fly/domain-list-community/tld-cn](https://github.com/v2fly/domain-list-community/blob/master/data/tld-cn)  
㉕ `rule-set,cn,🛡️ 直连域名` 源采用 [v2fly/domain-list-community/cn](https://github.com/v2fly/domain-list-community/blob/master/data/cn)（删除了带有 `@!cn` 和 `@ads` 的域名，并新增了 v2fly/domain-list-community/geolocation-!cn 中带有 `@cn` 的域名）和 [blackmatrix7/ios_rule_script/ChinaMax](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/ChinaMax)（仅域名）组合  
㉖ `rule-set,privateip,🔒 私有网络` 源采用 [DustinWin/geoip/config.json](https://github.com/DustinWin/geoip/blob/master/config.json) 中的 `input.type:private` 和 [TrackersList](https://github.com/XIU2/TrackersListCollection/blob/master/all.txt)（仅 IP）组合  
㉗ `rule-set,cnip,🀄️ 直连 IP` 源采用 [GeoLite2-Country-CSV/CN](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data)、[17mon/china_ip_list](https://github.com/17mon/china_ip_list)、[gaoyifan/china-operator-ip](https://github.com/gaoyifan/china-operator-ip)、[APNIC/CN](http://ftp.apnic.net/stats/apnic/delegated-apnic-latest) 和 [blackmatrix7/ios_rule_script/ChinaASN](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Surge/ChinaASN) 组合  
㉘ `rule-set,netflixip,🎥 奈飞视频` 源采用 [GeoLite2-ASN-CSV/Netflix](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data) 和 [blackmatrix7/ios_rule_script/Netflix](https://github.com/blackmatrix7/ios_rule_script/tree/master/rule/Clash/Netflix)（Netflix_IP.txt）组合  
㉙ `rule-set,telegramip,📲 电报消息` 源采用 [GeoLite2-ASN-CSV/Telegram](https://dev.maxmind.com/geoip/geolite2-free-geolocation-data) 和 [Telegram IP 段](https://core.telegram.org/resources/cidr.txt)组合
## 3. 文件使用
<details>
<summary>① mihomo 内核</summary>

注：
- 1. 若不需要图标（也可使用[数据源](https://github.com/DustinWin/ruleset_geodata?tab=readme-ov-file#2-%E6%95%B0%E6%8D%AE%E6%BA%90-1)中的 emoji），请自行删除策略组 `proxy-groups` 中的 `icon` 配置项
- 2. 以下只是节选，请酌情套用

```
proxy-groups:
  - {name: 节点选择, type: select, proxies: [香港节点, 台湾节点, 日本节点, 韩国节点, 新加坡节点, 美国节点], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/proxy.png"}
  - {name: 网络测试, type: select, proxies: [全球直连, 香港节点, 台湾节点, 日本节点, 韩国节点, 新加坡节点, 美国节点], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/networktest.png"}
  - {name: 人工智能, type: select, proxies: [节点选择, 香港节点, 日本节点, 新加坡节点, 美国节点], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/ai.png"}
  - {name: Trackerslist, type: select, proxies: [全球直连, 节点选择], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/trackerslist.png"}
  - {name: 游戏服务, type: select, proxies: [全球直连, 节点选择], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/games-cn.png}
  - {name: 微软服务, type: select, proxies: [全球直连, 节点选择], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/microsoft-cn.png"}
  - {name: 谷歌服务, type: select, proxies: [全球直连, 节点选择], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/google-cn.png"}
  - {name: 苹果服务, type: select, proxies: [全球直连, 节点选择], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/apple-cn.png"}
  - {name: 奈飞视频, type: select, proxies: [节点选择, 香港节点, 日本节点, 新加坡节点], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/netflix.png"}
  - {name: 迪士尼+, type: select, proxies: [节点选择, 香港节点, 日本节点, 新加坡节点], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/disney.png"}
  - {name: Max, type: select, proxies: [节点选择, 香港节点, 日本节点, 新加坡节点], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/max.png"}
  - {name: Prime Video, type: select, proxies: [节点选择, 香港节点, 日本节点, 新加坡节点], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/primevideo.png"}
  - {name: Apple TV+, type: select, proxies: [节点选择, 香港节点, 日本节点, 新加坡节点], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/appletv.png"}
  - {name: 油管视频, type: select, proxies: [节点选择, 香港节点, 日本节点, 新加坡节点], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/youtube.png"}
  - {name: TikTok, type: select, proxies: [节点选择, 香港节点, 日本节点, 新加坡节点], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/tiktok.png"}
  - {name: 哔哩哔哩, type: select, proxies: [全球直连, 节点选择, 香港节点, 日本节点, 新加坡节点], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/bilibili.png"}
  - {name: 直连顶级域名, type: select, proxies: [全球直连, 节点选择], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/cn.png"}
  - {name: 直连域名, type: select, proxies: [全球直连, 节点选择], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/cn.png"}
  - {name: 直连 IP, type: select, proxies: [全球直连, 节点选择], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/cnip.png"}
  - {name: 代理顶级域名, type: select, proxies: [节点选择, 全球直连], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/global.png"}
  - {name: 代理域名, type: select, proxies: [节点选择, 全球直连], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/global.png"}
  - {name: 电报消息, type: select, proxies: [节点选择], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/telegram.png"}
  - {name: 直连软件, type: select, proxies: [全球直连], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/applications.png"}
  - {name: 私有网络, type: select, proxies: [全球直连], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/private.png"}
  - {name: 漏网之鱼, type: select, proxies: [节点选择, 全球直连], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/match.png"}
  - {name: 广告域名, type: select, proxies: [全球拦截, 全球绕过], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/ads.png"}
  - {name: 全球拦截, type: select, proxies: [REJECT], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/reject.png"}
  - {name: 全球绕过, type: select, proxies: [PASS], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/pass.png"}
  - {name: 全球直连, type: select, proxies: [DIRECT], icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/direct.png"}

  - {name: 香港节点, type: url-test, tolerance: 50, use: [🛫 机场订阅], filter: "(?i)(🇭🇰|港|hk|hongkong|hong kong)", icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/hongkong.png"}
  - {name: 台湾节点, type: url-test, tolerance: 50, use: [🛫 机场订阅], filter: "(?i)(🇹🇼|台|tw|taiwan|tai wan)", icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/taiwan.png"}
  - {name: 日本节点, type: url-test, tolerance: 50, use: [🛫 机场订阅], filter: "(?i)(🇯🇵|日|jp|japan)", icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/japan.png"}
  - {name: 新加坡节点, type: url-test, tolerance: 50, use: [🛫 机场订阅], filter: "(?i)(🇸🇬|新|sg|singapore)", icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/singapore.png"}
  - {name: 美国节点, type: url-test, tolerance: 50, use: [🛫 机场订阅], filter: "(?i)(🇺🇸|美|us|unitedstates|united states)", icon: "https://github.com/DustinWin/ruleset_geodata/releases/download/icon/unitedstates.png"}

rule-providers:
  # 任选一
  fakeip-filter:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/fakeip-filter.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/fakeip-filter.mrs"
    interval: 86400
  # 任选一
  fakeip-filter:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/fakeip-filter.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/fakeip-filter-lite.mrs"
    interval: 86400

  private:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/private.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/private.mrs"
    interval: 86400

  ads:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/ads.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/ads.mrs"
    interval: 86400

  trackerslist:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/trackerslist.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/trackerslist.mrs"
    interval: 86400

  applications:
    type: http
    behavior: classical
    format: text
    path: ./rules/applications.list
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/applications.list"
    interval: 86400

  microsoft-cn:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/microsoft-cn.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/microsoft-cn.mrs"
    interval: 86400

  apple-cn:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/apple-cn.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/apple-cn.mrs"
    interval: 86400

  google-cn:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/google-cn.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/google-cn.mrs"
    interval: 86400

  games-cn:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/games-cn.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/games-cn.mrs"
    interval: 86400

  netflix:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/netflix.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/netflix.mrs"
    interval: 86400

  disney:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/disney.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/disney.mrs"
    interval: 86400

  max:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/max.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/max.mrs"
    interval: 86400

  primevideo:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/primevideo.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/primevideo.mrs"
    interval: 86400

  appletv:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/appletv.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/appletv.mrs"
    interval: 86400

  youtube:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/youtube.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/youtube.mrs"
    interval: 86400

  tiktok:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/tiktok.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/tiktok.mrs"
    interval: 86400

  bilibili:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/bilibili.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/bilibili.mrs"
    interval: 86400

  ai:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/ai.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/ai.mrs"
    interval: 86400

  networktest:
    type: http
    behavior: classical
    format: text
    path: ./rules/networktest.list
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/networktest.list"
    interval: 86400

  tld-proxy:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/tld-proxy.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/tld-proxy.mrs"
    interval: 86400

  proxy:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/proxy.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/proxy.mrs"
    interval: 86400

  tld-cn:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/tld-cn.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/tld-cn.mrs"
    interval: 86400

  cn:
    type: http
    behavior: domain
    format: mrs
    path: ./rules/cn.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/cn.mrs"
    interval: 86400

  privateip:
    type: http
    behavior: ipcidr
    format: mrs
    path: ./rules/privateip.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/privateip.mrs"
    interval: 86400

  cnip:
    type: http
    behavior: ipcidr
    format: mrs
    path: ./rules/cnip.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/cnip.mrs"
    interval: 86400

  netflixip:
    type: http
    behavior: ipcidr
    format: mrs
    path: ./rules/netflixip.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/netflixip.mrs"
    interval: 86400

  telegramip:
    type: http
    behavior: ipcidr
    format: mrs
    path: ./rules/telegramip.mrs
    url: "https://github.com/DustinWin/ruleset_geodata/releases/download/mihomo-ruleset/telegramip.mrs"
    interval: 86400

rules:
  - RULE-SET,private,私有网络
  - RULE-SET,ads,广告域名
  - RULE-SET,trackerslist,Trackerslist
  - RULE-SET,applications,直连软件
  - RULE-SET,microsoft-cn,微软服务
  - RULE-SET,apple-cn,苹果服务
  - RULE-SET,google-cn,谷歌服务
  - RULE-SET,games-cn,游戏服务
  - RULE-SET,netflix,奈飞视频
  - RULE-SET,disney,迪士尼+
  - RULE-SET,max,Max
  - RULE-SET,primevideo,Prime Video
  - RULE-SET,appletv,Apple TV+
  - RULE-SET,youtube,油管视频
  - RULE-SET,tiktok,TikTok
  - RULE-SET,bilibili,哔哩哔哩
  - RULE-SET,ai,人工智能
  - RULE-SET,networktest,网络测试
  - RULE-SET,tld-proxy,代理顶级域名
  - RULE-SET,proxy,代理域名
  - RULE-SET,tld-cn,直连顶级域名
  - RULE-SET,cn,直连域名
  - RULE-SET,privateip,私有网络,no-resolve
  - RULE-SET,cnip,直连 IP
  - RULE-SET,netflixip,奈飞视频,no-resolve
  - RULE-SET,telegramip,电报消息,no-resolve
```
</details>
<details>
<summary>② sing-box 内核</summary>

注：
- 1. [sing-box-ruleset](https://github.com/DustinWin/ruleset_geodata/releases/tag/sing-box-ruleset) 规则集文件的源文件格式始终保持最新版；[sing-box-ruleset-compatible](https://github.com/DustinWin/ruleset_geodata/releases/tag/sing-box-ruleset-compatible) 规则集文件的源文件格式始终为当前最新版的上一个版本。详见：[sing-box 源文件格式](https://sing-box.sagernet.org/zh/configuration/rule-set/source-format/)
- 2. 须手动新建“*ruleset*”文件夹，否则规则集文件不会保存在本地。如导入 [ShellCrash](https://github.com/juewuy/ShellCrash)，可先连接 SSH 后执行命令 `mkdir -p $CRASHDIR/ruleset/`
- 3. 以下只是节选，请酌情套用

```
{
  "outbounds": [
    { "tag": "🚀 节点选择", "type": "selector", "outbounds": [ "🇭🇰 香港节点", "🇹🇼 台湾节点", "🇯🇵 日本节点", "🇰🇷 韩国节点", "🇸🇬 新加坡节点", "🇺🇸 美国节点" ] },
    { "tag": "📈 网络测试", "type": "selector", "outbounds": [ "🎯 全球直连", "🇭🇰 香港节点", "🇹🇼 台湾节点", "🇯🇵 日本节点", "🇰🇷 韩国节点", "🇸🇬 新加坡节点", "🇺🇸 美国节点" ] },
    { "tag": "🤖 人工智能", "type": "selector", "outbounds": [ "🚀 节点选择", "🇭🇰 香港节点", "🇯🇵 日本节点", "🇸🇬 新加坡节点", "🇺🇸 美国节点" ] },
    { "tag": "📋 Trackerslist", "type": "selector", "outbounds": [ "🎯 全球直连", "🚀 节点选择" ] },
    { "tag": "🎮 游戏服务", "type": "selector", "outbounds": [ "🎯 全球直连", "🚀 节点选择" ] },
    { "tag": "🪟 微软服务", "type": "selector", "outbounds": [ "🎯 全球直连", "🚀 节点选择" ] },
    { "tag": "🇬 谷歌服务", "type": "selector", "outbounds": [ "🎯 全球直连", "🚀 节点选择" ] },
    { "tag": "🍎 苹果服务", "type": "selector", "outbounds": [ "🎯 全球直连", "🚀 节点选择" ] },
    { "tag": "🎥 奈飞视频", "type": "selector", "outbounds": [ "🚀 节点选择", "🇭🇰 香港节点", "🇯🇵 日本节点", "🇸🇬 新加坡节点" ] },
    { "tag": "📽️ 迪士尼+", "type": "selector", "outbounds": [ "🚀 节点选择", "🇭🇰 香港节点", "🇯🇵 日本节点", "🇸🇬 新加坡节点" ] },
    { "tag": "🎞️ Max", "type": "selector", "outbounds": [ "🚀 节点选择", "🇭🇰 香港节点", "🇯🇵 日本节点", "🇸🇬 新加坡节点" ] },
    { "tag": "🎬 Prime Video", "type": "selector", "outbounds": [ "🚀 节点选择", "🇭🇰 香港节点", "🇯🇵 日本节点", "🇸🇬 新加坡节点" ] },
    { "tag": "🍎 Apple TV+", "type": "selector", "outbounds": [ "🚀 节点选择", "🇭🇰 香港节点", "🇯🇵 日本节点", "🇸🇬 新加坡节点" ] },
    { "tag": "📹 油管视频", "type": "selector", "outbounds": [ "🚀 节点选择", "🇭🇰 香港节点", "🇯🇵 日本节点", "🇸🇬 新加坡节点" ] },
    { "tag": "🎵 TikTok", "type": "selector", "outbounds": [ "🚀 节点选择", "🇭🇰 香港节点", "🇯🇵 日本节点", "🇸🇬 新加坡节点" ] },
    { "tag": "📺 哔哩哔哩", "type": "selector", "outbounds": [ "🎯 全球直连", "🚀 节点选择", "🇭🇰 香港节点", "🇯🇵 日本节点", "🇸🇬 新加坡节点" ] },
    { "tag": "🛡️ 直连顶级域名", "type": "selector", "outbounds": [ "🎯 全球直连", "🚀 节点选择" ] },
    { "tag": "🛡️ 直连域名", "type": "selector", "outbounds": [ "🎯 全球直连", "🚀 节点选择" ] },
    { "tag": "🀄️ 直连 IP", "type": "selector", "outbounds": [ "🎯 全球直连", "🚀 节点选择" ] },
    { "tag": "🧱 代理顶级域名", "type": "selector", "outbounds": [ "🚀 节点选择", "🎯 全球直连" ] },
    { "tag": "🧱 代理域名", "type": "selector", "outbounds": [ "🚀 节点选择", "🎯 全球直连" ] },
    { "tag": "📲 电报消息", "type": "selector", "outbounds": ["🚀 节点选择"] },
    { "tag": "⬇️ 直连软件", "type": "selector", "outbounds": ["🎯 全球直连"] },
    { "tag": "🔒 私有网络", "type": "selector", "outbounds": ["🎯 全球直连"] },
    { "tag": "🐟 漏网之鱼", "type": "selector", "outbounds": [ "🚀 节点选择", "🎯 全球直连" ] },
    { "tag": "🛑 广告域名", "type": "selector", "outbounds": [ "🔴 全球拦截", "🎯 全球直连" ] },
    { "tag": "🔴 全球拦截", "type": "selector", "outbounds": [ "REJECT" ] },
    { "tag": "🎯 全球直连", "type": "selector", "outbounds": [ "DIRECT"] },
    { "tag": "REJECT", "type": "block" },
    { "tag": "DIRECT", "type": "direct" },
    { "tag": "GLOBAL", "type": "selector", "outbounds": [ "DIRECT", "REJECT", "🇭🇰 香港节点", "🇹🇼 台湾节点", "🇯🇵 日本节点", "🇰🇷 韩国节点", "🇸🇬 新加坡节点", "🇺🇸 美国节点" ] },
  ],
  "route": {
    "rules": [
      { "rule_set": [ "private" ], "outbound": "🔒 私有网络" },
      { "rule_set": [ "ads" ], "outbound": "🛑 广告域名" },
      { "rule_set": [ "trackerslist" ], "outbound": "📋 Trackerslist" },
      { "rule_set": [ "applications" ], "outbound": "⬇️ 直连软件" },
      { "rule_set": [ "microsoft-cn" ], "outbound": "🪟 微软服务" },
      { "rule_set": [ "apple-cn" ], "outbound": "🍎 苹果服务" },
      { "rule_set": [ "google-cn" ], "outbound": "🇬 谷歌服务" },
      { "rule_set": [ "games-cn" ], "outbound": "🎮 游戏服务" },
      { "rule_set": [ "netflix" ], "outbound": "🎥 奈飞视频" },
      { "rule_set": [ "disney" ], "outbound": "📽️ 迪士尼+" },
      { "rule_set": [ "max" ], "outbound": "🎞️ Max" },
      { "rule_set": [ "primevideo" ], "outbound": "🎬 Prime Video" },
      { "rule_set": [ "appletv" ], "outbound": "🍎 Apple TV+" },
      { "rule_set": [ "youtube" ], "outbound": "📹 油管视频" },
      { "rule_set": [ "tiktok" ], "outbound": "🎵 TikTok" },
      { "rule_set": [ "bilibili" ], "outbound": "📺 哔哩哔哩" },
      { "rule_set": [ "ai" ], "outbound": "🤖 人工智能" },
      { "rule_set": [ "networktest" ], "outbound": "📈 网络测试" },
      { "rule_set": [ "tld-proxy" ], "outbound": "🧱 代理顶级域名" },
      { "rule_set": [ "proxy" ], "outbound": "🧱 代理域名" },
      { "rule_set": [ "tld-cn" ], "outbound": "🛡️ 直连顶级域名" },
      { "rule_set": [ "cn" ], "outbound": "🛡️ 直连域名" },
      { "rule_set": [ "privateip" ], "outbound": "🔒 私有网络", "skip_resolve": true },
      { "rule_set": [ "cnip" ], "outbound": "🀄️ 直连 IP" },
      { "rule_set": [ "netflixip" ], "outbound": "🎥 奈飞视频", "skip_resolve": true },
      { "rule_set": [ "telegramip" ], "outbound": "📲 电报消息", "skip_resolve": true }
    ],
    "rule_set": [
      // 任选一
      {
        "tag": "fakeip-filter",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/fakeip-filter.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/fakeip-filter.srs"
      },
      // 任选一
      {
        "tag": "fakeip-filter",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/fakeip-filter.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/fakeip-filter-lite.srs"
      },
      {
        "tag": "private",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/private.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/private.srs"
      },
      {
        "tag": "ads",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/ads.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/ads.srs"
      },
      {
        "tag": "trackerslist",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/trackerslist.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/trackerslist.srs"
      },
      {
        "tag": "applications",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/applications.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/applications.srs"
      },
      {
        "tag": "microsoft-cn",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/microsoft-cn.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/microsoft-cn.srs"
      },
      {
        "tag": "apple-cn",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/apple-cn.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/apple-cn.srs"
      },
      {
        "tag": "google-cn",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/google-cn.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/google-cn.srs"
      },
      {
        "tag": "games-cn",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/games-cn.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/games-cn.srs"
      },
      {
        "tag": "netflix",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/netflix.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/netflix.srs"
      },
      {
        "tag": "disney",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/disney.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/disney.srs"
      },
      {
        "tag": "max",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/max.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/max.srs"
      },
      {
        "tag": "primevideo",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/primevideo.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/primevideo.srs"
      },
      {
        "tag": "appletv",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/appletv.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/appletv.srs"
      },
      {
        "tag": "youtube",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/youtube.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/youtube.srs"
      },
      {
        "tag": "tiktok",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/tiktok.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/tiktok.srs"
      },
      {
        "tag": "bilibili",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/bilibili.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/bilibili.srs"
      },
      {
        "tag": "ai",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/ai.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/ai.srs"
      },
      {
        "tag": "networktest",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/networktest.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/networktest.srs"
      },
      {
        "tag": "tld-proxy",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/tld-proxy.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/tld-proxy.srs"
      },
      {
        "tag": "proxy",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/proxy.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/proxy.srs"
      },
      {
        "tag": "tld-cn",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/tld-cn.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/tld-cn.srs"
      },
      {
        "tag": "cn",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/cn.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/cn.srs"
      },
      {
        "tag": "privateip",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/privateip.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/privateip.srs"
      },
      {
        "tag": "cnip",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/cnip.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/cnip.srs"
      },
      {
        "tag": "netflixip",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/netflixip.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/netflixip.srs"
      },
      {
        "tag": "telegramip",
        "type": "remote",
        "format": "binary",
        "path": "./ruleset/telegramip.srs",
        "url": "https://github.com/DustinWin/ruleset_geodata/releases/download/sing-box-ruleset/telegramip.srs"
      }
    ]
  }
}
```
</details>
