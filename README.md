# 🛡️ 安全技能知识库 (Security Skills)

综合安全技能知识库，涵盖渗透测试、逆向工程、漏洞挖掘、恶意软件分析等领域。

## 📑 目录

| # | 分类 | 描述 |
|---|------|------|
| 01 | [信息收集与侦察](01-recon/) | 被动/主动侦察、资产收集、技术栈识别 |
| 02 | [漏洞发现与扫描](02-vuln-discovery/) | CVE匹配、Web漏洞扫描、配置缺陷检测 |
| 03 | [漏洞利用技术](03-exploitation/) | SQL注入、XSS、LFI/RCE、反序列化、XXE |
| 04 | [WAF绕过技术](04-waf-bypass/) | PHP/SQL/命令注入WAF绕过、CSP绕过 |
| 05 | [后渗透与横向移动](05-post-exploitation/) | 权限提升、凭据收集、横向移动、持久化 |
| 06 | [Web安全专项](06-web-security/) | SSRF、文件上传、JWT攻击、目录遍历 |
| 07 | [逆向工程](07-reverse-engineering/) | 工具链、APK逆向、JS逆向、固件渗透 |
| 08 | [移动安全](08-mobile-security/) | Android/iOS渗透、SSL Pinning绕过 |
| 09 | [AI/MCP安全](09-ai-mcp-security/) | Prompt注入、MCP风险、OWASP LLM Top 10 |
| 10 | [渗透测试流程](10-pentest-flow/) | 六阶段标准流程、HW攻击链、工具链 |
| 11 | [报告编写](11-reporting/) | 报告结构、CVSS评分、漏洞描述模板 |
| 12 | [CTF技能](12-ctf/) | Web/Pwn/Crypto/Reverse/Forensics |
| 13 | [供应链与API安全](13-supply-chain-api/) | SBOM/SCA、API 10阶段测试 |
| 14 | [恶意软件分析](14-malware-analysis/) | 静态/动态分析、YARA/Sigma规则 |
| 15 | [代码审计](15-code-audit/) | 55+漏洞类型、五阶段方法论、Semgrep/CodeQL |

## 📂 详细子文件

### 03-漏洞利用技术

| 文件 | 内容 |
|------|------|
| `SKILL.md` | PoC构造流程、反序列化利用、XXE注入 |
| `sqli.md` | SQL注入10大测试场景、手动Payload示例、SQLMap命令速查、WAF绕过tamper脚本组合 |
| `xss.md` | XSS 17大场景、常用Payload(基础/DOM/属性逃逸/事件处理器/编码绕过/框架特定)、CSP绕过15种技术 |
| `lfi-rce.md` | 7大RCE方法(日志投毒/proc/environ/临时文件/图片马/数据库/SSH密钥/PHP Session)、PHP伪协议利用、目录遍历绕过 |

### 其他分类

每个分类文件夹均包含独立的 `SKILL.md` 文件，内含完整的技能知识、代码示例、工具命令和实战Payload。

## 🎯 使用说明

**学习路径建议：**
1. **入门**：01-recon → 02-vuln-discovery → 10-pentest-flow
2. **Web安全**：03-exploitation → 04-waf-bypass → 06-web-security
3. **进阶**：05-post-exploitation → 07-reverse-engineering → 08-mobile-security
4. **专项**：09-ai-mcp-security → 13-supply-chain-api → 14-malware-analysis → 15-code-audit
