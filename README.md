<div align="center">

<a href="https://github.com/0x109z3r0">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=500&size=22&duration=3200&pause=900&color=E5534B&center=true&vCenter=true&width=560&lines=%24+whoami;0x109z3r0;Web+Vulnerability+Assessment;Penetration+Testing" alt="whoami" />
</a>

**웹 취약점 진단 · 모의해킹**<br/>
<sub>Web Application Security · Offensive Security · Break to Defend</sub>

<br/>

<img src="https://img.shields.io/badge/focus-web%20application%20security-E5534B?style=flat-square" alt="focus"/>
<img src="https://img.shields.io/badge/method-OWASP%20WSTG-000000?style=flat-square&logo=owasp&logoColor=white" alt="method"/>
<img src="https://img.shields.io/badge/scope-authorized%20only-2EA043?style=flat-square" alt="scope"/>

</div>

---

```console
$ cat about.txt
```

공격자의 관점에서 웹 애플리케이션을 분석하고, 그 결과를 **개발자가 바로 고칠 수 있는 형태**로 전달하는 일을 합니다.
취약점을 "찾는 것"보다 **왜 생겼는지, 무엇을 바꿔야 다시 생기지 않는지**를 설명하는 데 더 많은 시간을 씁니다.

<sub>I look at web applications the way an attacker would, then hand the findings back in a form developers can act on immediately — root cause and fix, not just a list of bugs.</sub>

---

## Assessment Coverage

| 영역 / Area | 주요 점검 항목 / Typical checks | Reference |
|:--|:--|:--|
| **Access Control** | 수평·수직 권한 상승, IDOR, 강제 브라우징, CSRF | OWASP A01 · CWE-639, CWE-352 |
| **Injection** | SQL Injection, Stored/Reflected/DOM XSS, OS Command Injection | OWASP A03 · CWE-89, CWE-79, CWE-78 |
| **Authentication & Session** | 인증 우회, 세션 고정·재사용, 비밀번호 재설정 로직, JWT 검증 | OWASP A07 · CWE-287, CWE-384 |
| **Server-Side Request** | SSRF, 내부망·메타데이터 엔드포인트 접근 | OWASP A10 · CWE-918 |
| **File Handling** | 확장자·MIME 검증 우회, 웹셸 업로드, 경로 조작 | CWE-434, CWE-22 |
| **Information Exposure** | 에러 메시지·디버그 정보, 디렉터리 리스팅, 민감정보 응답 노출 | OWASP A05 · CWE-200, CWE-209 |

<sub>Reference: OWASP Top 10 (2021), MITRE CWE.</sub>

---

## Methodology

```text
 Recon ──▶ Mapping ──▶ Discovery ──▶ Exploitation ──▶ Reporting ──▶ Retest
   │          │            │              │               │            │
 자산·범위   기능·입력점    자동+수동       PoC로 영향도      재현 절차     조치 후
 식별        흐름 파악      교차 검증       실증              개선 방안     재점검
```

- **범위와 권한이 먼저.** 서면으로 합의된 대상·기간·방법 안에서만 진단합니다.
- **스캐너 결과는 가설일 뿐.** 모든 이슈는 수동으로 재현해 오탐을 걸러냅니다.
- **영향도는 근거로.** 실제 악용 시나리오와 CVSS 점수로 우선순위를 제시합니다.

<sub>Scope and authorization first · Scanner output is a hypothesis, not a finding · Severity backed by a working PoC and CVSS.</sub>

---

## Reporting

좋은 진단 결과는 좋은 리포트로 완성된다고 생각합니다. 모든 이슈는 아래 구조로 정리합니다.

| 항목 | 내용 |
|:--|:--|
| **Summary** | 비개발 직군도 이해할 수 있는 한 문단 요약 |
| **Severity** | CVSS 벡터와 점수, 비즈니스 영향 |
| **Reproduction** | 요청/응답 원문을 포함한 단계별 재현 절차 |
| **Root Cause** | 취약점이 발생한 코드·설계 수준의 원인 |
| **Remediation** | 즉시 조치(단기)와 구조적 개선(장기)을 분리해 제시 |

---

## Toolkit

<table>
  <tr>
    <td width="140"><b>Proxy &amp; Web</b></td>
    <td>
      <img src="https://img.shields.io/badge/Burp%20Suite-FF6633?style=flat-square&logo=burpsuite&logoColor=white" alt="Burp Suite"/>
      <img src="https://img.shields.io/badge/OWASP%20ZAP-00549E?style=flat-square&logo=owasp&logoColor=white" alt="OWASP ZAP"/>
    </td>
  </tr>
  <tr>
    <td><b>Network</b></td>
    <td>
      <img src="https://img.shields.io/badge/Nmap-4682B4?style=flat-square&logo=nmap&logoColor=white" alt="Nmap"/>
      <img src="https://img.shields.io/badge/Wireshark-1679A7?style=flat-square&logo=wireshark&logoColor=white" alt="Wireshark"/>
    </td>
  </tr>
  <tr>
    <td><b>Exploitation</b></td>
    <td>
      <img src="https://img.shields.io/badge/Metasploit-2A2A2A?style=flat-square&logo=metasploit&logoColor=white" alt="Metasploit"/>
    </td>
  </tr>
  <tr>
    <td><b>Scripting &amp; OS</b></td>
    <td>
      <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"/>
      <img src="https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white" alt="Bash"/>
      <img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black" alt="Linux"/>
    </td>
  </tr>
  <tr>
    <td><b>Learning</b></td>
    <td>
      <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker"/>
      <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white" alt="Kubernetes"/>
      <img src="https://img.shields.io/badge/Ghidra-C4302B?style=flat-square&logo=ghidra&logoColor=white" alt="Ghidra"/>
      <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript"/>
    </td>
  </tr>
</table>

<!--
## Writeups & Research

실제 작성한 글이 생기면 주석을 해제하고 채워 넣으세요. 빈 섹션은 없는 것보다 못합니다.

| Date | Title | Topic |
|:--|:--|:--|
| 2026-00 | [제목](링크) | SSRF |
-->

---

## Activity

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://streak-stats.demolab.com/?user=0x109z3r0&theme=github-dark-blue&hide_border=true&background=0D1117"/>
    <source media="(prefers-color-scheme: light)" srcset="https://streak-stats.demolab.com/?user=0x109z3r0&theme=default&hide_border=true"/>
    <img src="https://streak-stats.demolab.com/?user=0x109z3r0&hide_border=true" alt="GitHub streak"/>
  </picture>
</div>

---

## Contact

<a href="https://github.com/0x109z3r0"><img src="https://img.shields.io/badge/GitHub-0x109z3r0-181717?style=flat-square&logo=github&logoColor=white" alt="GitHub"/></a>
<!-- 준비되면 주석 해제
<a href="mailto:YOUR_EMAIL"><img src="https://img.shields.io/badge/Email-contact-EA4335?style=flat-square&logo=gmail&logoColor=white" alt="Email"/></a>
<a href="YOUR_BLOG_URL"><img src="https://img.shields.io/badge/Blog-writeups-000000?style=flat-square&logo=hashnode&logoColor=white" alt="Blog"/></a>
-->

---

<div align="center">
<sub>
모든 보안 연구와 테스트는 <b>사전에 서면 승인된 범위</b> 안에서만 수행합니다.<br/>
All research and testing is conducted <b>only within explicitly authorized scope</b>.
</sub>
</div>
