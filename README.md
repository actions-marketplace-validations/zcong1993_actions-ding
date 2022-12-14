# DingDing Notify Action [![Test](https://github.com/zcong1993/actions-ding/actions/workflows/test.yml/badge.svg)](https://github.com/zcong1993/actions-ding/actions/workflows/test.yml)

Send dingding simple notify message.

## Usage

| option      | required | description                                                                                                         |
| ----------- | -------- | ------------------------------------------------------------------------------------------------------------------- |
| dingToken   | true     | DingDing bot access_token                                                                                           |
| body        | true     | any kind of message body [dingding](https://ding-doc.dingtalk.com/doc#/serverapi2/qf2nxq) support into `body` field |
| secret      | false    | if secret set, action will call API with sign                                                                       |
| ignoreError | false    | if set true, will not fail action when API call failed                                                              |

## Examples

```yaml
- name: Send dingding notify
  uses: zcong1993/actions-ding@master
  with:
    dingToken: ${{ secrets.DING_TOKEN }}
    body: |
      {
        "msgtype": "link",
        "link": {
            "text": "这个即将发布的新版本，创始人陈航（花名“无招”）称它为“红树林”。而在此之前，每当面临重大升级，产品经理们都会取一个应景的代号，这一次，为什么是“红树林”？",
            "title": "时代的火车向前开",
            "picUrl": "",
            "messageUrl": "https://www.dingtalk.com/s?__biz=MzA4NjMwMTA2Ng==&mid=2650316842&idx=1&sn=60da3ea2b29f1dcc43a7c8e4a7c97a16&scene=2&srcid=09189AnRJEdIiWVaKltFzNTw&from=timeline&isappinstalled=0&key=&ascene=2&uin=&devicetype=android-23&version=26031933&nettype=WIFI"
        }
      }
```

### with sign

```yaml
- name: Send dingding notify
  uses: zcong1993/actions-ding@master
  with:
    dingToken: ${{ secrets.DING_TOKEN }}
    secret: ${{ secrets.DING_SECRET }} # if secret set, action will call API with sign
    body: |
      {
        "msgtype": "link",
        "link": {
            "text": "这个即将发布的新版本，创始人陈航（花名“无招”）称它为“红树林”。而在此之前，每当面临重大升级，产品经理们都会取一个应景的代号，这一次，为什么是“红树林”？",
            "title": "时代的火车向前开",
            "picUrl": "",
            "messageUrl": "https://www.dingtalk.com/s?__biz=MzA4NjMwMTA2Ng==&mid=2650316842&idx=1&sn=60da3ea2b29f1dcc43a7c8e4a7c97a16&scene=2&srcid=09189AnRJEdIiWVaKltFzNTw&from=timeline&isappinstalled=0&key=&ascene=2&uin=&devicetype=android-23&version=26031933&nettype=WIFI"
        }
      }
```

put any kind of message body [dingding](https://ding-doc.dingtalk.com/doc#/serverapi2/qf2nxq) support into `body` field.
