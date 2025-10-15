EXPLOIT/CODE FOUND AND MADE BY @ntxin on discord 





## Status:  Fixed ✅

### website: https://ikonpass.com
#### Vulnibity: XSS Reflected 
#### Danger P5

**What can this exploit do?**

- lets attackers inject images into chat

**Where?**
In support chat. Victim will send the payload in the chat and image will show up

**xss injection**
```html
<img src="YOUR SOURCE"/>
```

