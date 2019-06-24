---
title: 봇 개발자용 적응형 카드
author: matthidinger
ms.author: mahiding
ms.date: 05/30/2018
ms.topic: article
ms.openlocfilehash: 1acc30c0347ea5527de2af1fe74e605c7589cbc6
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2019
ms.locfileid: "59553285"
---
# <a name="adaptive-cards-for-bot-developers"></a>봇 개발자용 적응형 카드

적응형 카드는 봇에 매우 적합합니다. 카드를 한 번 작성한 후 Microsoft Teams와 같은 여러 앱, 자신의 웹 사이트 등에 멋지게 렌더링할 수 있습니다.

> [!NOTE]
> 현재 미리 보기에서는 Skype가 지원되지 않습니다. 최신 정보는 [파트너 상태](../resources/partners.md) 페이지를 참조하세요.

## <a name="try-it-out"></a>시도해보기

다음 링크를 클릭하고 [Scuba Bot과 이야기하세요](http://contososcubademo.azurewebsites.net/). `I'm looking for scuba`라고 말하면 꿈꾸던 스쿠버 여행을 예약하도록 도와줄 것입니다.  

모든 봇 응답은 적응형 카드를 사용하여 생성됩니다.

[![스쿠버 채팅 스크린샷](media/bots/scuba-chat.png)](http://contososcubademo.azurewebsites.net/)

**코드 확인**: 전체 [Contoso Scuba Bot 소스 코드](https://github.com/matthidinger/ContosoScubaBot
)는 GitHub에서 확인할 수 있습니다.


## <a name="bot-framework-integration"></a>Bot Framework 통합

[Bot Framework](https://dev.botframework.com/)를 사용하여 Skype, Microsoft Teams, Facebook Messenger 등과 같은 여러 "채널"을 통해 사용자와 채팅할 수 있는 단일 봇을 작성할 수 있습니다.

## <a name="walkthrough"></a>연습

봇에 적응형 카드를 추가하는 방법은 상당히 직관적입니다.

### <a name="step-0-start-with-a-basic-message"></a>0단계: 기본 메시지를 사용하여 시작

모든 채널에 제공하고 사용자에게 텍스트를 표시할 수 있는 표준 Bot Framework `message` 페이로드가 있습니다.

```json
{
   "type": "message",
   "text": "Plain text is ok, but sometimes I long for more..."
}
```

### <a name="step-1-add-an-adaptive-card-attachment"></a>1단계: 적응형 카드 `attachment` 추가

Bot Framework에는 텍스트 이외의 서식을 추가할 수 있는 `attachments`라는 개념이 있습니다. 

사용자 지정 텍스트를 표시하는 적응형 카드를 연결해 보겠습니다.

![기본 적응형 카드](media/bots/hello-adaptivecards.png)

```json
{
  "type": "message",
  "text": "Plain text is ok, but sometimes I long for more...",
  "attachments": [
    {
      "contentType": "application/vnd.microsoft.card.adaptive",
      "content": {
        "type": "AdaptiveCard",
        "version": "1.0",
        "body": [
          {
            "type": "TextBlock",
            "text": "Hello World!",
            "size": "large"
          },
          {
            "type": "TextBlock",
            "text": "*Sincerely yours,*"
          },
          {
            "type": "TextBlock",
            "text": "Adaptive Cards",
            "separation": "none"
          }
        ],
        "actions": [
          {
            "type": "Action.OpenUrl",
            "url": "http://adaptivecards.io",
            "title": "Learn More"
          }
        ]
      }
    }
  ]
}
```

### <a name="step-2-build-even-richer-cards"></a>2단계: 서식이 더 많은 카드 작성 

적응형 카드는 사용자 지정 가능한 텍스트보다 훨씬 더 많은 서식을 제공합니다. 

다음을 수행할 수 있습니다. 

* 카드에 `Images` 추가
* `Containers` 및 `Columns`를 사용하여 콘텐츠 구성
* 여러 유형의 `Actions` 추가
* 사용자로부터 `Input` 수집
* 한 카드에 `show another card` 명령
* [전체 스키마 탐색기를 확인해 보세요](http://adaptivecards.io/explorer/)! 

## <a name="platform-sdks"></a>플랫폼 SDK

봇이 .NET 또는 NodeJS를 사용하여 개발된 경우 라이브러리를 사용하여 적응형 카드를 훨씬 더 쉽게 작성할 수 있습니다.

플랫폼|설치|자세한 내용
--------|-------|----------
.NET | `Install-Package AdaptiveCards -IncludePrerelease` | [Bot Framework .NET 문서](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-add-rich-card-attachments)
NodeJS | `npm install adaptivecards` | [Bot Framework NodeJS 문서](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-send-rich-cards)


## <a name="channel-status"></a>채널 상태

Bot Framework를 사용하여 여러 채널에 봇을 게시할 수 있습니다. Microsoft는 적응형 카드에 대한 완벽한 지원을 제공하기 위해 다양한 채널과 협업하고 있습니다. 최신 정보는 [파트너 상태](../resources/partners.md) 페이지를 참조하세요.


## <a name="dive-in"></a>자세히 알아보세요.

이 자습서에서는 극히 일부만 다루었으므로 적응형 카드로 봇을 개선하는 더 많은 방법을 살펴보려면 아래의 링크를 확인하세요.

* 영감을 얻기 위해 [샘플 카드 찾아보기](http://adaptivecards.io/samples/)
* [스키마 탐색기](http://adaptivecards.io/explorer)를 사용하여 사용 가능한 요소 알아보기
* [대화형 비주얼라이저](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)를 사용하여 카드 작성
* 모든 피드백과 [연결 유지](http://adaptivecards.io/connect)
