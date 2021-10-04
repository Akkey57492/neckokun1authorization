# neckokun API
neckokunAPIはexeAuthorization等の<br>
処理に使われているAPIです。<br>
専用のapikeyがあればユーザーでもアクセスできます。<br>
(専用apikeyは通常のユーザーには配布していません)

# GET /api/antisub
POST Header
```json
{
  "authorization": "{{APIKEY}}"
}
```
RESPONSE Json (Success)
```json
{
  "ips": [
    "ip",
    "ip",
    "ip"
  ],
  "status": "success"
}
```
RESPONSE Json (Failed)
```json
{
  "error": "Invalid Api Key",
  "status": "Invalid Api Key"
}
```

# POST /api/antisub

## 説明
使われたipをサーバーに記憶します。<br>
既に登録されているとエラーが返ってくるとサブと認定されてしまいます。
POST Header
```json
{
  "authorization": "{{APIKEY}}",
  "regip": "{{RegisterIP}}"
}
```
RESPONSE Json (Success)
```json
{
  "status": "success"
}
```
RESPONSE Json (Failed / APIKEY)
```json
{
  "status": "Invalid Api Key"
}
```
RESPONSE Json (Failed / ANTISUB)
```json
{
  "status": "Already IP Registered"
}
```
# DELETE /api/antisub
POST Header
```json
{
  "authorization": "{{APIKEY}}",
  "pincode": "{{PIN CODE}}"
}
```
RESPONSE Json (Success)
```json
{
  "status": "success"
}
```
RESPONSE Json (Failed / APIKEY)
```json
{
  "status": "Invalid Api Key"
}
```
RESPONSE Json (Failed / Unknown)
```json
{
  "status": "Unknown Error"
}
```
