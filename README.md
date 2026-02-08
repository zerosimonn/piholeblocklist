# piholeblocklist
Centralized repository for my personal DNS filtering rules. These Pi-hole configuration lists that are updated based on browsing experience.

## 🚀 Quick Links
To use these in Pi-hole, right-click the "Raw Link" and copy it into your Pi-hole dashboard. Warning when using regular expressions: too broad rules can disable your internet. 

| List Type | Description | Raw Link |
| :--- | :--- | :--- |
| **Blocklist** | Exact domains to block | [Raw Link](https://raw.githubusercontent.com/zerosimonn/piholeblocklist/main/blocklist.txt) |
| **Whitelist** | Domains that must be allowed | [Raw Link](https://raw.githubusercontent.com/zerosimonn/piholeblocklist/main/whitelist.txt) |
| **RegEx** | Pattern-based blocking | [Raw Link](https://raw.githubusercontent.com/zerosimonn/piholeblocklist/main/regex.txt) |

---

## 🛠 Installation Instructions

### 1. Adding the Blocklist or Whitelist respectively (WebUI)
1. Copy the **Raw Link** above.
2. Log into Pi-hole WebUI > **Lists**.
3. Paste the URL and click **Add bloclist** or **Add allowlist**, respectively.
4. Update Gravity: `Tools > Update Gravity` (or run `pihole -g` in SSH).

### 2. Adding RegEx Patterns (SSH)
1. If needed, adjust cmd to match your GitHub username.
2. Run this command to import all patterns from the `regex.txt` file:
```bash
curl -s [https://raw.githubusercontent.com/zerosimonn/piholeblocklist/main/regex.txt](https://raw.githubusercontent.com/zerosimonn/piholeblocklist/main/regex.txt) | grep -v '^#' | xargs -I {} pihole --regex {}
```
3. Run Pi-hole Regex debudding mode. 

## 📝References
https://docs.pi-hole.net/regex/tutorial/

https://gitmoji.dev/
