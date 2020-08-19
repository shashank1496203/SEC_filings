import json
import urllib.request
TOKEN = 'c4bf1aac2c15b6561c97babda467d939785f0bac399f872b445710efa1c3a697'
API = "https://api.sec-api.io?token=" + TOKEN
payload = {

  "query": { "query_string": { "query": "filedAt:{2019-01-01 TO 2019-12-31} AND (formType:\"10-K\")" } },

  "from": "0",

  "size": "20",

  "sort": [{ "filedAt": { "order": "desc" } }]

}
jsondata = json.dumps(payload)

jsondataasbytes = jsondata.encode('utf-8')
req = urllib.request.Request(API)
req.add_header('Content-Type', 'application/json; charset=utf-8')
