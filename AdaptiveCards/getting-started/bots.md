---
title: 봇 개발자를 위한 adaptive Card
author: matthidinger
ms.author: mahiding
ms.date: 05/30/2018
ms.topic: article
ms.openlocfilehash: 1acc30c0347ea5527de2af1fe74e605c7589cbc6
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553285"
---
# <a name="adaptive-cards-for-bot-developers"></a>봇 개발자를 위한 adaptive Card

Adaptive Card는 봇 위한 매우 적합 합니다. 해당 카드를 한 번 작성 하 고 Microsoft Teams, 고유한 웹 사이트 등과 같은 여러 앱 내에서 원활 하 게 렌더링 되 게 있습니다.

> [!NOTE]
> Skype는 현재 미리 보기에서는 지원 되지 않습니다. 참조 된 [파트너 상태](../resources/partners.md) 최신 페이지입니다.

## <a name="try-it-out"></a>시도해보기

다음 링크를 클릭 하 고 [우리의 스쿠버 Bot 연결할](http://contososcubademo.azurewebsites.net/)합니다. 예를 들어 `I'm looking for scuba` 및 꿈꿔의 스쿠버 여행 예약 하는 데 도움이 됩니다.  

Adaptive Card를 사용 하 여 봇의 응답의 모든 만들어집니다.

[![스쿠버 채팅 스크린 샷](media/bots/scuba-chat.png)](http://contososcubademo.azurewebsites.net/)

**코드 가져오기**: 전체 [Contoso 스쿠버 봇 소스 코드](https://github.com/matthidinger/ContosoScubaBot
) GitHub에서 확인할 수 있습니다.


## <a name="bot-framework-integration"></a>Bot Framework 통합

사용 하 여 합니다 [Bot Framework](https://dev.botframework.com/) Skype, Microsoft Teams, Facebook Messenger 등과 같은 여러 "채널"을 통해 사용자와 채팅 수 있는 단일 봇을 작성할 수 있습니다.

## <a name="walkthrough"></a>연습

봇을 Adaptive Card를 추가할 보다시피 상당히 됩니다.

### <a name="step-0-start-with-a-basic-message"></a>0 단계: 기본 메시지를 사용 하 여 시작

여기에 표준 봇 프레임 워크 `message` 모든 채널을 제공할 수 있습니다 하 고 사용자에 게 텍스트를 표시 하는 페이로드입니다.

```json
{
   "type": "message",
   "text": "Plain text is ok, but sometimes I long for more..."
}
```

### <a name="step-1-add-an-adaptive-card-attachment"></a>1단계: Adaptive Card를 추가 합니다. `attachment`

Bot Framework에는 개념이 텍스트 이외의 일부 다양 한 기능을 추가 하려면 `attachments`합니다. 

사용자 지정 텍스트를 표시 하는 Adaptive Card를 연결 해 보겠습니다.

![기본 적응 카드](media/bots/hello-adaptivecards.png)

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

### <a name="step-2-build-even-richer-cards"></a>2단계: 풍부한 카드 빌드 

Adaptive Card 보다 훨씬 더 방금 사용자 지정 가능한 텍스트를 제공합니다. 

다음 작업을 수행할 수 있습니다. 

* 추가 `Images` 카드로
* 사용 하 여 콘텐츠를 구성 `Containers` 및 `Columns`
* 여러 유형의 추가 `Actions`
* 수집 `Input` 사용자의
* 카드가 두 개 `show another card`
* [전체 스키마 탐색기를 확인해](http://adaptivecards.io/explorer/)! 

## <a name="platform-sdks"></a>플랫폼 Sdk

.NET 또는 NodeJS를 사용 하 여 봇을 개발 하는 경우 라이브러리도 쉽게 적응 카드를 만들 수 있도록 했습니다.

플랫폼|Install|자세한 내용
--------|-------|----------
.NET | `Install-Package AdaptiveCards -IncludePrerelease` | [Bot Framework.NET 설명서](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-add-rich-card-attachments)
NodeJS | `npm install adaptivecards` | [Bot Framework NodeJS Docs](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-send-rich-cards)


## <a name="channel-status"></a>채널 상태

Bot Framework를 사용 하면 여러 채널에서 봇을 게시할 수 있습니다. 적응 카드에 대 한 전체 지원을 제공 하기 위해 다양 한 채널을 사용 하는 것입니다. 참조 된 [파트너 상태](../resources/partners.md) 최신 페이지입니다.


## <a name="dive-in"></a>시작 해 보겠습니다!

에서는 했습니다 기초적이 자습서에서는 따라서 하세요 다양 한 방법을 알아볼 Adaptive Card 봇의 향상 시킬 수는 아래와 같은 링크를 살펴보십시오.

* [샘플 카드 찾아보기](http://adaptivecards.io/samples/) 영감
* 사용 된 [스키마 탐색기](http://adaptivecards.io/explorer) 사용 가능한 요소를 알아보려면
* 카드를 통해 빌드를 [대화형 시각화 도우미](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)
* [연락](http://adaptivecards.io/connect) 피드백을 사용 하 여
