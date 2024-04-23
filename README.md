<h1 align="center">
  <br>
  <a href="https://github.com/prath-10/BoltRun-Recon"><img src="https://github.com/prath-10/BoltRun-Recon/blob/main/images/banner.png" alt="BoltRun Recon"></a>
  <br>
  BoltRun Recon
  <br>
</h1>


<h3 align="center">Summary</h3>

**BoltRun Recon** automates the entire process of reconnaissance for you. It outperforms the work of subdomain enumeration along with various vulnerability checks and obtaining maximum information about your target.

BoltRun Recon uses a lot of techniques (passive, bruteforce, permutations, certificate transparency, source code scraping, analytics, DNS records...) for subdomain enumeration which helps you to get the maximum and the most interesting subdomains so that you be ahead of the competition.

It also performs various vulnerability checks like XSS, Open Redirects, SSRF, CRLF, LFI, SQLi, SSL tests, SSTI, DNS zone transfers, and much more. Along with these, it performs OSINT techniques, directory fuzzing, dorking, ports scanning, screenshots, nuclei scan on your target.

So, what are you waiting for? Go! Go! Go! :boom:



## 💿 Installation

## a) Using a PC/VPS/VM

```bash
git clone https://github.com/prath-10/BoltRun-Recon
cd BoltRun-Recon/
./install.sh
./reconftw.sh -d target.com -r
```


```yaml


# Usage


## TARGET OPTIONS

| Flag | Description |
|------|-------------|
| -d | Single Target domain *(example.com)*  |
| -l | List of targets *(one per line)* |
| -m | Multiple domain target *(companyName)*  |
| -x | Exclude subdomains list *(Out Of Scope)* |
| -i | Include subdomains list *(In Scope)* |

## MODE OPTIONS

| Flag | Description |
|------|-------------|
| -r | Recon - Full recon process (without attacks like sqli,ssrf,xss,ssti,lfi etc.) |
| -s | Subdomains - Perform only subdomain enumeration, web probing, subdomain takeovers |
| -p | Passive - Perform only passive steps |
| -a | All - Perform whole recon and all active attacks |
| -w | Web - Perform only vulnerability checks/attacks on particular target |
| -n | OSINT - Performs an OSINT scan (no subdomain enumeration and attacks) |
| -c | Custom - Launches specific function against target |
| -h | Help - Show this help menu |

## GENERAL OPTIONS

| Flag | Description |
|------|-------------|
| --deep | Deep scan (Enable some slow options for deeper scan, *vps intended mode*) |
| -f | Custom config file path |
| -o | Output directory |
| -v | Axiom distributed VPS |
| -q | Rate limit in requests per second |

## Example Usage

**NOTE: this is applicable when you've installed BoltRun Recon on the host (e.g. VM/VPS/cloud) and not in a Docker container.**

### To perform a full recon on single target

```bash
./reconftw.sh -d target.com -r
```

### To perform a full recon on a list of targets

```bash
./reconftw.sh -l sites.txt -r -o /output/directory/
```

### Perform full recon with more time intense tasks *(VPS intended only)*

```bash
./reconftw.sh -d target.com -r --deep -o /output/directory/
```

### Perform recon in a multi domain target

```bash
./reconftw.sh -m company -l domains_list.txt -r
```

### Perform recon with axiom integration

```bash
./reconftw.sh -d target.com -r -v
```

### Perform all steps (whole recon + all attacks) a.k.a. YOLO mode

```bash
./reconftw.sh -d target.com -a
```

### Show help section

```bash
./reconftw.sh -h
```


# Sample video

![Video](images/BoltRun Recon.gif)

# :fire: Features :fire:

## Osint

- Domain information ([whois](https://github.com/rfc1036/whois) and [amass](https://github.com/OWASP/Amass))
- Emails addresses and passwords leaks ([emailfinder](https://github.com/Josue87/EmailFinder) and [LeakSearch](https://github.com/JoelGMSec/LeakSearch))
- Metadata finder ([MetaFinder](https://github.com/Josue87/MetaFinder))
- API leaks search ([porch-pirate](https://github.com/MandConsultingGroup/porch-pirate) and [SwaggerSpy](https://github.com/UndeadSec/SwaggerSpy))
- Google Dorks ([dorks_hunter](https://github.com/six2dez/dorks_hunter))
- Github Dorks ([gitdorks_go](https://github.com/damit5/gitdorks_go))
- GitHub org analysis ([enumerepo](https://github.com/trickest/enumerepo), [trufflehog](https://github.com/trufflesecurity/trufflehog) and [gitleaks](https://github.com/gitleaks/gitleaks))

## Subdomains

- Passive ([amass](https://github.com/OWASP/Amass), [subfinder](https://github.com/projectdiscovery/subfinder) and [github-subdomains](https://github.com/gwen001/github-subdomains))
- Certificate transparency ([crt](https://github.com/cemulus/crt))
- NOERROR subdomain discovery ([dnsx](https://github.com/projectdiscovery/dnsx), more info [here](https://www.securesystems.de/blog/enhancing-subdomain-enumeration-ents-and-noerror/))
- Bruteforce ([puredns](https://github.com/d3mondev/puredns))
- Permutations ([Gotator](https://github.com/Josue87/gotator), [ripgen](https://github.com/resyncgg/ripgen) and [regulator](https://github.com/cramppet/regulator))
- JS files & Source Code Scraping ([katana](https://github.com/projectdiscovery/katana))
- DNS Records ([dnsx](https://github.com/projectdiscovery/dnsx))
- Google Analytics ID ([AnalyticsRelationships](https://github.com/Josue87/AnalyticsRelationships))
- TLS handshake ([tlsx](https://github.com/projectdiscovery/tlsx))
- Recursive search ([dsieve](https://github.com/trickest/dsieve)).
- Subdomains takeover ([nuclei](https://github.com/projectdiscovery/nuclei))
- DNS takeover ([dnstake](https://github.com/pwnesia/dnstake))
- DNS Zone Transfer ([dig](https://linux.die.net/man/1/dig))
- Cloud checkers ([S3Scanner](https://github.com/sa7mon/S3Scanner) and [cloud_enum](https://github.com/initstring/cloud_enum))

## Hosts

- IP info ([whoisxmlapi API](https://www.whoisxmlapi.com/))
- CDN checker ([ipcdn](https://github.com/six2dez/ipcdn))
- WAF checker ([wafw00f](https://github.com/EnableSecurity/wafw00f))
- Port Scanner (Active with [nmap](https://github.com/nmap/nmap) and passive with [smap](https://github.com/s0md3v/Smap))
- Port services vulnerability checks ([vulners](https://github.com/vulnersCom/nmap-vulners))
- Password spraying ([brutespray](https://github.com/x90skysn3k/brutespray))

## Webs

- Web Prober ([httpx](https://github.com/projectdiscovery/httpx))
- Web screenshoting ([nuclei](https://github.com/projectdiscovery/nuclei))
- Web templates scanner ([nuclei](https://github.com/projectdiscovery/nuclei) and [nuclei geeknik](https://github.com/geeknik/the-nuclei-templates.git))
- CMS Scanner ([CMSeeK](https://github.com/Tuhinshubhra/CMSeeK))
- Url extraction ([gau](https://github.com/lc/gau),[waymore](https://github.com/xnl-h4ck3r/waymore), [katana](https://github.com/projectdiscovery/katana), [github-endpoints](https://gist.github.com/six2dez/d1d516b606557526e9a78d7dd49cacd3) and [JSA](https://github.com/w9w/JSA))
- URL patterns Search and filtering ([urless](https://github.com/xnl-h4ck3r/urless), [gf](https://github.com/tomnomnom/gf) and [gf-patterns](https://github.com/1ndianl33t/Gf-Patterns))
- Favicon Real IP ([fav-up](https://github.com/pielco11/fav-up))
- Javascript analysis ([subjs](https://github.com/lc/subjs), [JSA](https://github.com/w9w/JSA), [xnLinkFinder](https://github.com/xnl-h4ck3r/xnLinkFinder), [getjswords](https://github.com/m4ll0k/BBTz), [mantra](https://github.com/MrEmpy/mantra))
- Fuzzing ([ffuf](https://github.com/ffuf/ffuf))
- URL sorting by extension
- Wordlist generation
- Passwords dictionary creation ([pydictor](https://github.com/LandGrey/pydictor))

## Vulnerability checks

- XSS ([dalfox](https://github.com/hahwul/dalfox))
- Open redirect ([Oralyzer](https://github.com/r0075h3ll/Oralyzer))
- SSRF (headers [interactsh](https://github.com/projectdiscovery/interactsh) and param values with [ffuf](https://github.com/ffuf/ffuf))
- CRLF ([crlfuzz](https://github.com/dwisiswant0/crlfuzz))
- Cors ([Corsy](https://github.com/s0md3v/Corsy))
- LFI Checks ([ffuf](https://github.com/ffuf/ffuf))
- SQLi Check ([SQLMap](https://github.com/sqlmapproject/sqlmap) and [ghauri](https://github.com/r0oth3x49/ghauri))
- SSTI ([ffuf](https://github.com/ffuf/ffuf))
- SSL tests ([testssl](https://github.com/drwetter/testssl.sh))
- Broken Links Checker ([katana](https://github.com/projectdiscovery/katana))
- Prototype Pollution ([ppmap](https://github.com/kleiton0x00/ppmap))
- Web Cache Vulnerabilities ([Web-Cache-Vulnerability-Scanner](https://github.com/Hackmanit/Web-Cache-Vulnerability-Scanner))
- 4XX Bypasser ([nomore403](https://github.com/devploit/nomore403))

## Extras

- Multithreading ([Interlace](https://github.com/codingo/Interlace))
- Custom resolvers generated list ([dnsvalidator](https://github.com/vortexau/dnsvalidator))
- Docker container included and [DockerHub](https://hub.docker.com/r/six2dez/reconftw) integration
- Ansible + Terraform deployment over AWS
- Allows IP/CIDR as target
- Resume the scan from last performed step
- Custom output folder option
- All in one installer/updater script compatible with most distros
- Diff support for continuous running (cron mode)
- Support for targets with multiple domains
- Raspberry Pi/ARM support
- 6 modes (recon, passive, subdomains, web, osint and all)
- Out of Scope Support + optional [inscope](https://github.com/tomnomnom/hacks/tree/master/inscope) support
- Notification system with Slack, Discord and Telegram ([notify](https://github.com/projectdiscovery/notify)) and sending zipped results support

## Mindmap/Workflow

![Mindmap](/images/mindmap_obsidian.png)
