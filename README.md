# 마음을 읽는 AI 우울감 자가진단 서비스, 마인드디텍터
![최종](https://user-images.githubusercontent.com/76239801/102711571-14060f80-42fe-11eb-9088-54fa0f3e5fb6.jpg)
  
#### 코로나19가 전 세계를 휩쓴 2020년, 대한민국 안녕하신가요? 
#### 범국민적 '마음 방역'의 시작을 위해 AI 우울감 자가진단 서비스를 새롭게 선보입니다.

:globe_with_meridians: [웹사이트 방문](http://minddetector.me/)

:movie_camera: [시연 영상](https://www.youtube.com/watch?v=tsU0ktw2vV4&feature=youtu.be)
- - -
### :pushpin: 마인드 디텍터의 핵심 역할

:one: '진짜' 사용자의 이야기를 토대로 우울감 자가 진단

:two: AI 감성 분석 기술과 공공데이터로 사용자의 우울감 검진

:three: 맞춤 상담센터 정보제공

:four: 사용자 데이터 축적을 통한 대국민 우울 지수 현황 파악
- - -
### :book: 사용법

:one: 마인드디텍터 웹사이트에 접속해 시작하기를 눌러주세요.

:two: 간단한 개인 정보를 입력해 주세요.

:three: 나의 감정을 담아 마인드디텍터가 준비한 총 10가지 질문에 답해주세요.

:four: AI 모델와 공공데이터의 정보가 대신 우울 지수를 측정합니다.

4 단계를 완료하면 우울감이 높은 유저의 경우 따뜻한 위로 글귀와 노랫말로 온기를 받을 수 있으며 근처 상담센터의 정보 또한 추가로 제공 전문의와의 상담을 권유합니다.

- - -
### :eyes: 제안이유
#### 국민 ‘마음 방역’의 필요성

코로나 19 국민 정신건강실태조사에 따르면 우울감 지수는 2018년 2.34점에서 2020년 9월 5.86점으로 오르는 큰 상승 폭을 보였습니다. 국민 10명 중 4명은 코로나로 인한 우울감을 경험했다고 답했습니다. 이처럼 사회적 거리 두기로 인한 실내 생활, 심리적 불안감과 고립감에서 오는 우울감 등으로 ‘코로나 우울’ 문제가 심각한 상황입니다. 

#### 나의 우울감, 조금 덜 아프게 마주할 수는 없을까?

현재 온라인상에서도 쉽고 빠르게 우울감을 측정할 수 있도록 다양한 자가 검진표가 공개되어 있습니다. 이는 개인의 정신건강 상태를 객관적으로 보여주는 척도를 기반으로 하고 있습니다. ‘마음이 슬프다’에 대한 답변으로 ‘그렇다’, ‘ 그렇지 않다’ 혹은 1점에서 5점까지 빈도로 점수를 매기는 검진표는 왠지 차갑게 느껴지기도 합니다.

#### 누군가가 나의 이야기를 읽고 마음을 알아준다면...

빅데이터 시대가 도래하면서 다양한 비정형 데이터를 토대로 ‘감성 분석’이 가능한 세상이 왔습니다. 2016년 미국 대선 당시, 언론이나 리서치 회사가 예측하지 못했던 도널드 트럼프의 당선을 트위터 기반 감성 분석 기술이 예측해내기도 했습니다.

이에 저희는 시대의 흐름과 기술의 발전에 발맞춰, 감성 분석기술을 기반으로 한 우울감 자가진단 서비스를 제안하고자 합니다. **표준 우울증 진단 문항 CES-D**를 기반으로 문항을 제작하였고, 그에 대한 유저의 답변을 토대로 그날의 우울 지수를 제공하도록 하였습니다. 이후 단계에 맞춘 마음 방역을 제안, 근처 상담센터에 대한 위치정보를 제공합니다. 차갑고 딱딱한 기존의 검진표가 아닌 일상적 상황에 대한 유저의 진실한 감정을 바탕으로 하여 우울감 자가진단에 대한 진입장벽을 낮춥니다. 전 국민이 상시로 마음을 돌볼 수 있도록 하여 국민 정신건강 증진을 목표로 합니다.
- - -
### :musical_note: 적용 기술

### Architecture

<img src ="https://user-images.githubusercontent.com/46865281/102685064-15add580-4221-11eb-8562-5f59a23eb6a2.png" width="700px" height="430px">

#### 감성 분석 모델 학습 데이터셋

[5가지 감정(기쁨, 중립, 슬픔, 화남, 두려움) 분류 데이터셋](https://github.com/lukasgarbas/nlp-text-emotion)

#### 번역 API
Google NMT API

#### 감성 분석 모델

[깃허브](https://github.com/wansook0316/emotion_analysis)(참조: [SKT Brain KoBert](https://github.com/SKTBrain/KoBERT))

![모델 결과](https://user-images.githubusercontent.com/44315967/102755839-525d0680-43b2-11eb-920d-0af875240553.png)


#### 우울감 척도 설정
① 감정 분석의 모델 결과를 문항별 답변에 적용하여 해당 문항에 대해 어떠한 감정을 느끼는지 파악   
② 5가지 감정 중 ‘두려움, 슬픔, 그리고 분노’와 같은 부정적 감정과 이와 반대되는 ‘기쁨과 ’ 긍정적 감정에 해당하는 답변의 값들을 분리하여 저장  
③ 문항에 답변한 사용자의 10가지 답변에 대한 ②번 감정의 개수를 기반으로 사용자의 우울감을 확률로 나타냄   
④ 사용자의 정보를 근간으로 성별, 거주지, 나이, 직업에 대한 자살률 정보를 공공데이터로부터 가져옴   
⑤ ④번에서 가져온 카테고리별 자살률을 기반으로 사용자가 우울증 취약계층에 속하는지 판단   
⑥ 최종 우울 지수는 ③감정 분석 모델의 결과와 ⑤자살 현황 공공데이터 분석 결과를 조합하여 계산   
우울 지수 = (부정적 감정 지수), (1-긍정적 감정 지수)*공공데이터를 기반으로 한 자살률 종합 확률의 9:1 가중 평균   

#### 웹개발

front: [깃허브](https://github.com/seung-00/mind-detector-front)

 * React, Redux, Redux-Saga, styled-components, typescript

back: [깃허브1](https://github.com/penguin234/mind-detector-utils), [깃허브2](https://github.com/penguin234/mind-detector-operation)

* PostgreSQL, flask, express, Docker, kubernetes, nginx

#### 공공데이터 분석

[지역별, 연령별, 성별, 직업별 자살률 공공데이터](http://kostat.go.kr/portal/korea/index.action)를 참고하여 우울증 취약계층을 파악한 후 이를 우울 지수 계산에 반영

[정신건강복지센터 설치운영 현황](http://www.mohw.go.kr/upload/viewer/skin/doc.html?fn=1560908774347_20190619104614.hwp&rs=/upload/viewer/result/202012/) 자료를 토대로 상담 센터 정보 

#### Notion 을 활용한 협업

[workspace](https://www.notion.so/00data/)

- - -
### :high_brightness: 기대 효과
우울감 자가진단 서비스에 대한 진입장벽을 낮추고, 전 국민이 상시로 마음을 돌볼 수 있도록 하여 국민 정신건강 증진이 가능하도록 합니다.
- - -
### :clipboard: 향후 계획
#### 음성 서비스 지원을 통한 '소외되는 국민 없는' 온라인 우울감 자가검진 서비스

저희 서비스는 추후에 음성을 텍스트로 변환해주는 api를 활용하여 음성 서비스를 지원할 예정입니다. 이를 통해 시각장애인과 글을 읽고 쓰지 못하는 국민들이 소외되지 않고, 자유롭게 마인드디텍터 서비스를 누릴 수 있을 것입니다.
- - -
### :paperclip: 활용 데이터 및 참고 문헌
#### 적용 데이터
[우울증 진단 문항 CES-D](https://www.midss.org/content/center-epidemiologic-studies-depression-scale-ces-d)

[Emotion Classification in Short Messages](https://github.com/lukasgarbas/nlp-text-emotion)

[한국생명의전화](https://lifeline.or.kr/business/board.php?page=1&gubun=public&keyfield=&keyword=&keyCate=)

#### 공공데이터
[자살률 현황](http://kostat.go.kr/portal/korea/index.action)

[정신건강복지센터 설치운영 현황](http://www.mohw.go.kr/upload/viewer/skin/doc.html?fn=1560908774347_20190619104614.hwp&rs=/upload/viewer/result/202012/)


#### 참고 문헌
[1] 이수정 외 3, 2020.3, 우리나라 성인 자살 관련 외상 경험과 자살태도, 우울, 자기효능감, 사회적 지지와의 관계

[2] 남미희 외 6, 2011.4, 우울증, 자살 그리고 한국사회

[3] 김범진, 2018.11, 트럼프 당선 측했던 그 분석 인간의 언어에서 감정을 읽어내

[4] 남미희 외 6, 2011.4, 우울증, 자살 그리고 한국사회

[5] 이하은, 2020.11, 한국대학신문, 코로나19로 자살시도 급증…정부, 전 국민 대상으로 대책 마련
