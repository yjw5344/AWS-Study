# AWS S3

## S3 생성하기
- AWS Console로 이동합니다.
- S3 서비스로 이동합니다.
![스크린샷 1](./images/screenshot-2018-02-18-PM-10.17.26.png)
- `버킷 만들기` 클릭합니다.
![스크린샷 2](./images/screenshot-2018-02-18-PM-10.17.30.png)
- 팝업 창이 뜨면, `버킷 이름`에 **고유한 이름(중복불가)** 을 입력합니다.
- 싱가포르 리전을 선택합니다.
![스크린샷 3](./images/3-1.png)
- 모든 설정을 기본 설정 값으로 두고 `다음`을 클릭합니다. (두 번)
- `버킷 만들기` 클릭
![스크린샷 4](./images/4-1.png)
- 만든 버킷을 클릭합니다
![스크린샷 5](./images/screenshot-2018-02-18-PM-10.19.22.png)
- `권한` 클릭
- `버킷 정책` 클릭
- 아래의 값을 복사, 붙여넣기 해주신 후 버킷 생성시 입력한 이름을 `버킷이름입력`에 넣어주세요

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": [
        "s3:GetObject"
        ],
      "Resource": "arn:aws:s3:::버킷이름입력/*"
    }
  ]
}
```

- `저장`을 클릭합니다.
![스크린샷 6](./images/6.png)  
- `CORS 구성` 클릭
- 아래의 값을 복사, 붙여넣기 해주세요.

```json  
<?xml version="1.0" encoding="UTF-8"?>
<CORSConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/">
<CORSRule>
    <AllowedOrigin>*</AllowedOrigin>
    <AllowedMethod>GET</AllowedMethod>
    <AllowedMethod>POST</AllowedMethod>
    <AllowedMethod>PUT</AllowedMethod>
    <MaxAgeSeconds>3000</MaxAgeSeconds>
</CORSRule>
</CORSConfiguration>
```

![스크린샷 6](./images/7.png)

축하드립니다! 실습이 완료셨다면, 다음 모듈인 [3. AWS RDS](../3_RDS) 으로 이동하세요.