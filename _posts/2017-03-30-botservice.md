---
layout: post
title:  "Bot Service Intro"
date:   2017-03-30 19:00:11 +0900
categories: Bot service
---

###Bot..! Bot Service!

봇! 봇은 여러 가지 의미를 가지고 있습니다. 로봇, 챗봇.. 하지만, Microsoft Azure의 Bot service는 봇 중에서도 요즘 가장 화두가 되는 **챗봇(채팅봇)**을 의미합니다!

그럼 챗봇은 무엇일까요? 챗봇은 AI(artificial intelligence)와 메신저를 결합시킨 용어라고 볼 수 있습니다.

특히 요즘 인공지능이 대세인 만큼, 챗봇도 굉장한 관심을 받고 있습니다. 페이스북의 CEO 마크 주커버그도 챗봇에 주목하고 있다고 언급한 적도 있습니다.

챗봇의 예로는 아이폰을 쓰시는 분이라면 다들 아시는 siri와, 갤럭시를 이용하시는 분이라면 다들 아시는 S보이스가 있습니다! 우리가 분명 일상 생활에서 자주 사용해 본 기능이지만, 지금 당장 챗봇을 하나 만들어봐라! 하면 우리는 과연 챗봇을 만들 수 있을까요?
챗봇이 아래의 코드처럼 간단하게 짜여졌다면 가능하겠지만..

```
if (input = “7시에 깨워줘”) {
	setAlarm(7);
	print("7시에 알람을 맞췄습니다.“);
}
```

만약 이런식으로 코드를 짠다면, 우리는 코드를 아주 길게 짜야하고, 코드로 짜지 않은 기능은 사용할 수 없습니다. 이 방법은 굉장히 비효율적일 뿐더러, 정말 코드를 끝까지 다 짤 수 있을지 의문마저 듭니다. 특히, 챗봇의 내부를 구현하는 것은 아마추어가 하기엔 쉽지 않을거예요.

그래서! Microsoft Azure 팀이, 우리를 위해 intelligence분야의 bot service를 만들었습니다. 우리는 Bot service로 짜여진 툴을 통해 좀 더 쉽게 우리만의 Bot을 만들 수 있습니다.

지금부터 Azure로 우리만의 Bot을 만들어 보도록 하겠습니다.

1. Microsoft azure portal에 접속합니다. (https://portal.azure.com)
2. + (새로만들기)를 클릭하여, Intelligence + analytics 그룹의 Bot service를 선택합니다.
3. 앱 이름을 짓습니다. (앱 이름은 맨 앞 글자가 영어 대문자여야 합니다.)
4. 구독, 리소스 그룹, 위치를 작성한 뒤 만들기를 클릭합니다.
5. 모든 리소스를 누르시면, 방금 만든 앱 이름으로 bot service가 등록되어 있을 것입니다.
6. 앱 이름을 누르면 “Create a Microsoft App ID” 라는 부분이 나타납니다.

7. 파란 버튼을 클릭하여 MS 계정으로 로그인 합니다.
8. 앱 이름을 입력하고 “계속하려면 앱 암호 생성” 버튼을 통해 앱 ID를 생성합니다.
9. 그러면 앱 암호가 나타나는데, 회색 칸 안을 복사하고, 앱ID를 다시 Azure로 돌아가서 작성합니다.
10. 그리고 language를 선택해야 하는데, 저는 C#을 선택하였습니다.
11. 그럼 5개의 템플릿이 나타납니다.

템플릿은 각각 이런식으로 구성되어 있습니다.

___
1. Basic : A bot with a single dialog that echoes back the user input.
2. Form : A bot that shows how to collect input from a user using a guided conversation using FormFlow.
3. Proactive : A bot that shows how to use Azure Functions to trigger events in Azure bots.
4. Language understanding : A bot that shows how to handle natural language using the Cognitive Services LUIS API.
5. Question and Answer : A bot that distills information into conversational, easy-to-navigate answers.
___

우리는 먼저 가장 간단한 1번 basic template를 사용해보도록 합시다.
12. 모든 선택을 마치면, "Create Bot“ 버튼으로 봇을 생성합니다.

봇을 생성하는데 약 5분~10분 정도의 시간이 소요됩니다.
