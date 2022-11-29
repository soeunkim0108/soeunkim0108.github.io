---
layout: post
title: "Google Analytics"
categories: jekyll update
comments: true
---

> 구글에서 무료로 제공하고 있는 웹분석 서비스

<br>

##### \# 웹 분석이란?
> 웹사이트 이용 현황을 이해하고 사용자 경험을 최적화하기 위해 웹 데이터를 측정, 수집, 분석 및 보고하는 것

쉽게 말하자면 어떤 사용자들이 우리 웹사이트를 방문하는지`(잠재고객에 관한 정보)`, 어떤 경로를 통해서 방문하는지`(유입출처에 관한 정보)`, 웹사이트에 도착한 후 어떤 행동을 보이는지`(방문형태에 관한 정보)`에 관한 데이터를 분석하여 마케팅 채널별 효과와 방문자의 웹사이트 경험을 개선하고 궁극적으로 비즈니스를 개선하는 데 활용하는 것

<br>

### Google Analytics 적용하기

1. [Google Analytics](https://analytics.google.com/) 접속 후 회원가입 및 로그인

2. 계정 설정
![account settings](/assets/gitbook/images/google-analytics-account.PNG)

3. 속성 설정
![property settings](/assets/gitbook/images/google-analytics-property.PNG)

4. 만들기
![create](/assets/gitbook/images/google-analytics-create.PNG)

5. 데이터 스트림 생성
![data stream create](/assets/gitbook/images/google-analytics-datastream.PNG)

6. 생성 후 측정ID 복사
![tracking ID](/assets/gitbook/images/google-analytics-trackingid.PNG)

7. _config.yml 파일에 복사한 측정ID 추가하기  
![_config.yml](/assets/gitbook/images/trackingID.PNG)

8. _includes/google-analytics.html 파일에 해당 코드 붙여넣기
![google-analytics.html](/assets/gitbook/images/google-analytics-html.PNG)


※ 본인은 _includes 아래에 google-analytics.html 파일이 있었지만 없으면 html 파일을 생성하면 됨.

※ 본인은 경로를 site.tracker.google_analytics로 설정하여<br>
_config.yml 파일에서 아래와 같이 추가하였음.
```python
tracker:
  google_analytics:     "복사한 측정ID"
```
<br>

### 결과
![result](/assets/gitbook/images/analytics.PNG)