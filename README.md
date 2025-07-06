# **CRICGO EVENTS JSON GENERATOR**  

### **📌 Overview**  
This script automatically scrapes live cricket streaming events from **[crichd.com.co](https://crichd.com.co)** and generates a structured JSON file (`cricgoevents.json`). The JSON is updated every **30 minutes** via a **cronjob** and uploaded to a **GitHub repository**.  

---

## **📂 JSON Structure**  
The generated JSON contains an array of cricket events with streaming links:  

```json
[
  {
    "title": "IND vs AUS - T20 World Cup",
    "link": "https://crichd.com.co/live/ind-vs-aus",
    "channels": [
      {
        "channel_name": "Star Sports 1 HD",
        "channel_link": "https://crichd.com.co/embed/star-sports-1",
        "iframe_url": "https://stream.crichd.com/player.php",
        "fid": "12345",
        "referer": "https://crichd.com.co",
        "logo_url": "https://crichd.com.co/logos/star-sports.png",
        "source_url": "http://localhost:8000?server=cricgo&fid=12345|Referer=https://crichd.com.co/&Origin=https://crichd.com.co"
      }
    ]
  }
]
```

### **🔹 Fields Explained**  
| Field | Description |
|--------|------------|
| `title` | Match/event title |
| `link` | URL of the event page |
| `channels` | Array of available streaming channels |
| `channel_name` | Name of the streaming channel |
| `channel_link` | Direct link to the channel |
| `iframe_url` | Embedded player URL |
| `fid` | Unique stream ID |
| `referer` | Required HTTP referer for streaming |
| `logo_url` | Channel logo image |
| `source_url` | Pre-formatted streaming URL (Replace with your own api) |

---

## **🌐 Website Source**  
- **Scraped from:** [https://crichd.com.co](https://crichd.com.co)  
- Extracts:  
  - Live matches  
  - Streaming links  
  - Channel metadata  

---

## **⏰ Cronjob Setup**  
The script runs every **30 minutes** to update the JSON file.  

### **🔧 Cronjob Command**  
```bash
*/30 * * * * /usr/bin/php /path/to/script.php
```

### **⚙️ Requirements**  
- PHP (with `DOM`, `libxml`, `cURL`)  
- GitHub Personal Access Token (for auto-upload)  
- Server with cron support  

---

## **📌 Notes**  
✅ **Automatic Updates** – JSON refreshes every 30 mins.  
🔒 **Secure** – Uses GitHub API for secure file uploads.  
📡 **Streaming-Ready** – Includes direct playable links.  

---

### **🔗 GitHub Repository**  
The JSON is stored in:  
`https://raw.githubusercontent.com/myselfhridoy/FreeHostingScript/refs/heads/main/cricgoevents.json`  

---

**🚀 Perfect for cricket streaming apps, IPTV services, or sports APIs!** 🏏
