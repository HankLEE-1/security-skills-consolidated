# 🛡️ 安全技能知识库 (Security Skills)

综合安全技能知识库，涵盖渗透测试、逆向工程、漏洞挖掘、恶意软件分析等15大领域。
每个文件夹为独立技能模块，包含完整知识、代码示例、工具命令和实战Payload。

---

## 📑 总目录

| # | 分类 | 描述 | 文件数 |
|---|------|------|--------|
| 01 | [信息收集与侦察](01-recon/) | 被动/主动侦察、资产收集、技术栈识别 | 1 |
| 02 | [漏洞发现与扫描](02-vuln-discovery/) | CVE匹配、Web漏洞扫描、配置缺陷检测 | 1 |
| 03 | [漏洞利用技术](03-exploitation/) | SQL注入、XSS、LFI/RCE、反序列化、XXE | 4 |
| 04 | [WAF绕过技术](04-waf-bypass/) | PHP/SQL/命令注入WAF绕过、CSP绕过 | 1 |
| 05 | [后渗透与横向移动](05-post-exploitation/) | 权限提升、凭据收集、横向移动、持久化 | 1 |
| 06 | [Web安全专项](06-web-security/) | SSRF、文件上传、JWT攻击、目录遍历 | 1 |
| 07 | [逆向工程](07-reverse-engineering/) | 工具链、APK逆向、JS逆向、固件渗透 | 1 |
| 08 | [移动安全](08-mobile-security/) | Android/iOS渗透、SSL Pinning绕过 | 1 |
| 09 | [AI/MCP安全](09-ai-mcp-security/) | Prompt注入、MCP风险、OWASP LLM Top 10 | 1 |
| 10 | [渗透测试流程](10-pentest-flow/) | 六阶段标准流程、HW攻击链、工具链 | 1 |
| 11 | [报告编写](11-reporting/) | 报告结构、CVSS评分、漏洞描述模板 | 1 |
| 12 | [CTF技能](12-ctf/) | Web/Pwn/Crypto/Reverse/Forensics | 1 |
| 13 | [供应链与API安全](13-supply-chain-api/) | SBOM/SCA、API 10阶段测试 | 1 |
| 14 | [恶意软件分析](14-malware-analysis/) | 静态/动态分析、YARA/Sigma规则 | 1 |
| 15 | [代码审计](15-code-audit/) | 55+漏洞类型、五阶段方法论、Semgrep/CodeQL | 1 |

---

## 📂 文件详细说明

### 01-recon（信息收集与侦察）

| 文件 | 章节 | 内容 |
|------|------|------|
| `SKILL.md` | 被动侦察 | HTTP响应头分析、HTML源码分析、WHOIS/DNS查询、证书透明度、搜索引擎 |
| | Google Dorking | 常用搜索语法（filetype、inurl、intitle、ext） |
| | 主动侦察 | 端口扫描(nmap/masscan)、目录枚举(ffuf/gobuster/dirsearch)、子域名发现(subfinder/amass)、指纹识别(wafw00f/whatweb)、敏感文件、API端点发现 |
| | 技术栈识别 | 前端框架(React/Vue/Angular)、后端框架(Django/Flask/Spring/PHP)、CMS(WordPress/Drupal)、数据库 |
| | 目标画像 | 输出模板示例 |
| | 资产收集自动化 | 完整自动化流程（subfinder→httpx→nmap→whatweb→ffuf→nuclei）及脚本 |

---

### 02-vuln-discovery（漏洞发现与扫描）

| 文件 | 章节 | 内容 |
|------|------|------|
| `SKILL.md` | CVE匹配 | 根据服务版本搜索CVE，优先Critical/High |
| | Web漏洞扫描清单 | SQL注入、XSS、SSRF、LFI/RFI、命令注入、文件上传、IDOR/BOLA 检测方法与工具 |
| | 配置缺陷检测 | 默认凭据、信息泄露(/actuator)、未授权访问、CORS配置、HTTPS配置、目录列表 |
| | SRC/众测方法论 | 5阶段：资产收集→攻击面映射→漏洞检测(305个payload)→WAF绕过(263个变体)→报告 |
| | 自动化扫描工具 | Nuclei、Nikto、WPScan 命令 |

---

### 03-exploitation（漏洞利用技术）

| 文件 | 章节 | 内容 |
|------|------|------|
| `SKILL.md` | PoC构造流程 | 5步：选择方法→最小化payload→WAF绕过→验证→生成脚本 |
| | 反序列化漏洞 | Java(ysoserial/JNDI)、PHP(phar://)、Python(pickle)、.NET(BinaryFormatter)，含完整利用代码 |
| | XXE注入 | 基础XXE、Blind XXE外带数据（含evil.dtd构造） |
| | N-day补丁差分 | 从补丁反推漏洞→二进制diff→PoC→武器化 |
| `sqli.md` | 10大测试场景 | 基础参数、POST注入、Cookie/Header注入、DBMS特定、数据库枚举、Union-Based、Error-Based、Boolean盲注、Time盲注、WAF绕过 |
| | 手动Payload | Error-Based(3种)、Union-Based(3种)、Time-Based(3种)、Boolean-Based(2种) 完整SQL语句 |
| | SQLMap速查 | 基础扫描、POST请求、Cookie注入、指定DBMS、枚举数据库、指定技术、tamper绕过、OS Shell、文件读取 |
| | 绕过技巧 | 大小写混合、内联注释、双重编码、等价函数、注释符变体、空格替代、双写 |
| | WAF tamper组合 | 安全狗、云锁、ModSecurity 专用tamper脚本组合 |
| `xss.md` | 17大场景 | 反射型、存储型、DOM XSS、盲注、上下文感知、CSP绕过、框架特定、SVG上传、mXSS、WebSocket、JSONP、Markdown、HTTP头注入、文件上传、PostMessage、Service Worker、WebAssembly |
| | 常用Payload | 基础标签、DOM XSS、属性逃逸、事件处理器、编码绕过、SVG、Angular/Vue/React/jQuery框架特定 Payload |
| | 工具对比 | XSStrike(DOM最佳)、Dalfox(最快)、XSpear(WAF绕过最佳) |
| | CSP绕过 | 15种技术详解（unsafe-inline/eval、data:URL、Angular模板注入、JSONP端点、子域名绕过等） |
| `lfi-rce.md` | 7大RCE方法 | 日志投毒(★★★★★)、/proc/self/environ(★★★★)、临时文件竞争(★★★)、图片马(★★★)、数据库文件(★★)、SSH密钥(★★)、PHP Session(★★) |
| | PHP伪协议 | php://filter、php://input、data://、expect://、zip://、phar:// 完整用法 |
| | 日志投毒RCE | Apache/Nginx/SSH日志投毒完整命令 |
| | 目录遍历绕过 | 12种绕过方式（../、双URL编码、UTF-8溢出等） |
| | 文件下载漏洞 | Linux/Windows敏感文件清单 |

---

### 04-waf-bypass（WAF绕过技术）

| 文件 | 章节 | 内容 |
|------|------|------|
| `SKILL.md` | PHP WAF绕过 | preg_replace双写、函数名混淆(Base64/字符串拼接/可变函数/回调函数/XOR异或/取反)、关键字绕过(路径拆分/注释/反转/大小写/双写) |
| | SQL注入WAF绕过 | 大小写、内联注释、双重编码、等价函数、注释符变体、空格替代(9种字符)、双写、十六进制、Chr函数 |
| | 命令注入WAF绕过 | 分隔符变体(8种)、命令混淆(单引号/双引号/空变量/通配符)、绕过长度限制(base64/hex/管道) |
| | XSS绕过 | 标签变体、事件处理器、HTML实体编码、Unicode编码、Base64编码、SVG、大小写、双写、协议、编码嵌套 |

---

### 05-post-exploitation（后渗透与横向移动）

| 文件 | 章节 | 内容 |
|------|------|------|
| `SKILL.md` | 环境确认 | 系统信息(uname/os-release)、网络信息(ip/arp/netstat)、用户信息(passwd/shadow/history) |
| | 内网信息收集 | 主机发现(ping扫描)、内网端口扫描(nc)、ARP扫描(arp-scan/nmap) |
| | 凭据收集 | Linux(shadow/ssh密钥/bash_history/mysql_history/conf文件)、Windows(Chrome密码/Mimikatz) |
| | 权限提升 | Linux(SUID/Sudo/内核漏洞/Cron)、Windows(服务权限/AlwaysInstallElevated) |
| | 横向移动 | Pass the Hash(evil-winrm)、PSRemoting、WMI、PsExec、域渗透(Kerberoasting/AS-REP Roasting/DCSync) |
| | 持久化 | Linux(Crontab后门/SSH公钥)、Windows(计划任务/注册表/服务) |

---

### 06-web-security（Web安全专项）

| 文件 | 章节 | 内容 |
|------|------|------|
| `SKILL.md` | SSRF利用 | 内网探测、协议利用(file/dict/gopher)、绕过技巧(16进制/10进制/8进制/IPv6)、DNS Rebinding |
| | SSRF到RCE | Redis写WebShell(gopher)、FastCGI、内网服务探测(Redis/Elasticsearch/MongoDB/Docker API) |
| | 反序列化 | Java/PHP/Python/.NET 各语言利用方式 |
| | XXE注入 | 基础XXE + Blind XXE |
| | 文件上传绕过 | 后缀名(php3/php4/phtml)、MIME类型、文件头(GIF89a)、.htaccess、双重后缀、空字节截断、竞争条件 |
| | JWT攻击 | 弱密钥爆破(hashcat/john)、算法混淆(RS256→HS256)、None算法、JKU/JWK注入 |
| | 目录遍历绕过 | 12种绕过方式 |

---

### 07-reverse-engineering（逆向工程）

| 文件 | 章节 | 内容 |
|------|------|------|
| `SKILL.md` | 工具链 | IDA Pro、Ghidra、radare2、GDB、Frida、angr、Unicorn、Qiling、Binary Ninja |
| | radare2命令 | 分析(aaa/afl/pdf)、信息查看(iI/iS/ii/iz)、调试(db/dc/ds/dr)、搜索(/x) |
| | IDA Pro操作 | 快捷键(Space/F5/X/N/Y/G)、常用窗口 |
| | Frida Hook | Java方法Hook、Native函数Hook、libc Hook 完整代码示例 |
| | APK逆向 | 5步：apktool解包→jadx反编译→smali修改→Frida Hook→重打包签名 |
| | JS逆向 | 5步：签名链路定位→加密参数分析→运行时采样→Node补环境→自动化 |
| | 固件渗透 | OWASP FSTM九阶段（固件获取→提取→文件系统→静态→动态→漏洞→AFL++→实机→报告） |
| | EDR绕过 | Direct Syscall / Hell's Gate / Call Stack Spoof |

---

### 08-mobile-security（移动安全）

| 文件 | 章节 | 内容 |
|------|------|------|
| `SKILL.md` | Android渗透 | runtime-first原则：确认设备→准备抓包→scrcpy驱动→检查抓包→Web测试→升级jadx/frida/ida |
| | 工具链 | adb、jadx、Burp Suite、Frida、scrcpy、Objection、Magisk |
| | ADB命令 | 设备连接、安装、包名、路径、拉取APK、当前Activity、日志监控 |
| | SSL Pinning绕过 | Frida自定义TrustManager + Objection `android sslpinning disable` |
| | Root检测绕过 | Frida Hook返回false、Magisk Hide/Shamiko、Runtime.exec拦截 |
| | iOS安全 | 越狱分析、Keychain提取、IPA逆向、签名机制分析 |

---

### 09-ai-mcp-security（AI/MCP安全）

| 文件 | 章节 | 内容 |
|------|------|------|
| `SKILL.md` | 应用层攻击 | 直接/间接Prompt注入、CoT干扰、Agent滥用、代码执行突破、Memory投毒 |
| | MCP与Agent风险 | 工具描述投毒、指令覆盖、隐藏指令注入、未授权资源访问、Skills供应链 |
| | 身份与授权 | 动作滥用、角色逃逸、权限漂移、云凭据滥用 |
| | 数据与隐私 | Prompt泄漏、敏感数据暴露、训练数据问题、模型逆推、API数据窃取 |
| | 基线与部署 | CI/CD缺陷、容器逃逸、向量数据库安全、沙箱失效、环境隔离 |
| | GAARM风险矩阵 | Governance、Authentication、Authorization、Risk Management 评估框架 |
| | OWASP LLM Top 10 | 10大风险详解 |
| | Prompt注入示例 | 直接注入、间接注入、编码绕过、角色扮演、多轮对话 |
| | MCP安全测试 | 工具描述审计、输入验证、权限检查、数据流追踪、供应链验证 |

---

### 10-pentest-flow（渗透测试流程）

| 文件 | 章节 | 内容 |
|------|------|------|
| `SKILL.md` | 六阶段标准流程 | 被动信息收集→主动信息收集→漏洞发现→漏洞利用→后渗透→报告生成 |
| | HW演练攻击链 | 外网突破(4步) + 内网渗透(4步)，含常用攻击路径图 |
| | 渗透工具链 | Nmap/Nuclei/SQLMap/FFUF/Hashcat/Burp/Metasploit/Hydra/Impacket/CrackMapExec，标注MCP支持 |
| | 注意事项 | 授权范围、数据保护、最小影响、记录完整、及时报告 |

---

### 11-reporting（报告编写）

| 文件 | 章节 | 内容 |
|------|------|------|
| `SKILL.md` | 报告结构 | 项目概述→执行摘要→详细发现→攻击路径→附件 |
| | 漏洞严重等级 | Critical(9.0-10.0)、High(7.0-8.9)、Medium(4.0-6.9)、Low(0.1-3.9)、Info(0.0)，含CVSS和示例 |
| | 漏洞描述模板 | 完整模板：等级、类型、URL、范围、描述、验证步骤、PoC、修复建议 |
| | CVSS评分计算 | CVSS:3.1 各维度说明(AV/AC/PR/UI/S/C/I/A) |
| | 自动化报告 | 逆向报告、渗透报告、CTF writeup模板，含Mermaid攻击路径图 |

---

### 12-ctf（CTF技能）

| 文件 | 章节 | 内容 |
|------|------|------|
| `SKILL.md` | CTF分类(40+) | Web/Pwn/Crypto/Reverse/Forensics/OSINT/Cloud/Container/AD/Mobile |
| | 常用CTF工具 | pwntools、z3、CyberChef、John the Ripper、Volatility、Wireshark、steghide/zsteg、hashcat、Ghidra、GDB+GEF/pwndbg |
| | Pwn工具链 | pwntools连接/构造payload/发送，完整Python代码 |
| | Crypto常见题型 | RSA分解、AES ECB、XOR加密、维吉尼亚密码，含代码 |
| | Forensics工具 | 流量分析(tshark/Wireshark)、内存取证(Volatility)、隐写(steghide/zsteg/stegsolve/binwalk) |

---

### 13-supply-chain-api（供应链与API安全）

| 文件 | 章节 | 内容 |
|------|------|------|
| `SKILL.md` | 供应链检查项 | SBOM(syft/cyclonedx)、SCA(snyk/grype/trivy)、容器安全(trivy)、CI/CD(checkov/tfsec)、构建完整性(cosign/sigstore) |
| | 依赖投毒防护 | 锁定版本、验证签名、typosquatting检测、私有镜像源 |
| | 常见供应链攻击 | Typosquatting、Dependency Confusion、Maintainer Takeover、恶意代码注入、构建管道篡改 |
| | API 10阶段 | API发现→认证→授权→输入验证→业务逻辑→速率限制→数据泄露→配置错误→日志监控→第三方集成 |
| | 常见API漏洞 | BOLA/IDOR、JWT攻击、OAuth滥用、GraphQL注入、WebSocket劫持、速率限制缺失、批量分配 |
| | API测试工具 | Burp Suite、Postman、Arjun、Kiterunner、jwt_tool、GraphQL内省查询/深度嵌套DoS |

---

### 14-malware-analysis（恶意软件分析）

| 文件 | 章节 | 内容 |
|------|------|------|
| `SKILL.md` | 静态分析 | file/strings/hexdump、pefile/lief/readelf、壳检测(DIE/PEiD)、反编译(IDA/Ghidra/r2)、YARA，含命令 |
| | 动态分析 | 沙箱(Cuckoo/ANY.RUN)、行为监控(ProcMon/strace)、网络分析(Wireshark/tcpdump)、内存分析(Volatility)、IOC提取 |
| | YARA规则 | 基础规则 + 进阶规则(mutex/c2/api/shellcode)，含完整代码 |
| | Sigma规则 | PowerShell执行检测、Mimikatz凭据转储检测，含完整YAML |
| | 反分析技术(94种) | 反调试(IsDebuggerPresent/NtQueryInformationProcess/CheckRemoteDebugger)、反虚拟机(VMware/VirtualBox)、反沙箱(SbieDll/进程数/分辨率/磁盘/运行时间)、时间延迟(Sleep/GetTickCount/高精度计时器) |

---

### 15-code-audit（代码审计）

| 文件 | 章节 | 内容 |
|------|------|------|
| `SKILL.md` | 代码审计分类 | Java审计、PHP审计、通用审计、安全审计、白盒审计、供应链投毒 |
| | 55+漏洞类型 | 注入类(SQL/NoSQL/命令/LDAP/XPath/SSTI/反序列化/XXE)、认证授权类(硬编码/弱密码/JWT/OAuth)、数据处理类(路径遍历/文件上传/SSRF/XXE/开放重定向) |
| | 框架特定 | Spring(SPEL/Actuator)、Django(模板注入/ORM)、Laravel(反序列化/Debug)、PHP(伪协议/变量覆盖)、Node.js(原型链污染/SSTI)、Python(SSTI/pickle/命令注入/SSRF) |
| | 五阶段方法论 | 架构分析→数据流分析→控制流分析→自动化扫描→人工验证 |
| | 危险函数清单 | PHP(命令执行/文件操作/反序列化/SQL/XSS)、Python(os.system/subprocess/pickle/yaml/SQL)、Java(Runtime.exec/ObjectInputStream/Statement.execute/SSTI) |
| | Semgrep规则 | SQL注入、命令注入、Django XSS 规则示例 |
| | CodeQL查询 | SQL注入查询示例 |
| | 微信小程序审计 | 7 Agent协作、4大维度(代码/数据/接口/业务)、5大特有风险(API密钥/接口未授权/越权/前端存储/重放) |

---

## 🎯 学习路径

| 阶段 | 路径 | 适合人群 |
|------|------|----------|
| 入门 | 01-recon → 02-vuln-discovery → 10-pentest-flow | 初学者 |
| Web安全 | 03-exploitation → 04-waf-bypass → 06-web-security | Web方向 |
| 进阶 | 05-post-exploitation → 07-reverse-engineering → 08-mobile-security | 有基础者 |
| 专项 | 09-ai-mcp-security → 13-supply-chain-api → 14-malware-analysis → 15-code-audit | 深度研究 |
