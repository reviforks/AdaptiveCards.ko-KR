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
# <a name="adaptive-cards-for-bot-developers"></a><span data-ttu-id="45c31-102">봇 개발자를 위한 adaptive Card</span><span class="sxs-lookup"><span data-stu-id="45c31-102">Adaptive Cards for Bot Developers</span></span>

<span data-ttu-id="45c31-103">Adaptive Card는 봇 위한 매우 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-103">Adaptive Cards are a great fit for Bots.</span></span> <span data-ttu-id="45c31-104">해당 카드를 한 번 작성 하 고 Microsoft Teams, 고유한 웹 사이트 등과 같은 여러 앱 내에서 원활 하 게 렌더링 되 게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-104">They let you author a card once and have it render beautifully inside multiple apps, like  Microsoft Teams, your own website, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="45c31-105">Skype는 현재 미리 보기에서는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-105">Skype is not supported in the current preview.</span></span> <span data-ttu-id="45c31-106">참조 된 [파트너 상태](../resources/partners.md) 최신 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-106">See the [Partner Status](../resources/partners.md) page for the latest.</span></span>

## <a name="try-it-out"></a><span data-ttu-id="45c31-107">시도해보기</span><span class="sxs-lookup"><span data-stu-id="45c31-107">Try it out</span></span>

<span data-ttu-id="45c31-108">다음 링크를 클릭 하 고 [우리의 스쿠버 Bot 연결할](http://contososcubademo.azurewebsites.net/)합니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-108">Click the following link and [talk to our Scuba Bot](http://contososcubademo.azurewebsites.net/).</span></span> <span data-ttu-id="45c31-109">예를 들어 `I'm looking for scuba` 및 꿈꿔의 스쿠버 여행 예약 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-109">Say `I'm looking for scuba` and it'll help you book the scuba trip of your dreams.</span></span>  

<span data-ttu-id="45c31-110">Adaptive Card를 사용 하 여 봇의 응답의 모든 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-110">All of the bot's responses are created with Adaptive Cards.</span></span>

<span data-ttu-id="45c31-111">[![스쿠버 채팅 스크린 샷](media/bots/scuba-chat.png)](http://contososcubademo.azurewebsites.net/)</span><span class="sxs-lookup"><span data-stu-id="45c31-111">[![Scuba chat screenshot](media/bots/scuba-chat.png)](http://contososcubademo.azurewebsites.net/)</span></span>

<span data-ttu-id="45c31-112">**코드 가져오기**: 전체 [Contoso 스쿠버 봇 소스 코드](https://github.com/matthidinger/ContosoScubaBot
) GitHub에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-112">**Get the code**: the full [Contoso Scuba Bot source code](https://github.com/matthidinger/ContosoScubaBot
) can be found on GitHub.</span></span>


## <a name="bot-framework-integration"></a><span data-ttu-id="45c31-113">Bot Framework 통합</span><span class="sxs-lookup"><span data-stu-id="45c31-113">Bot Framework Integration</span></span>

<span data-ttu-id="45c31-114">사용 하 여 합니다 [Bot Framework](https://dev.botframework.com/) Skype, Microsoft Teams, Facebook Messenger 등과 같은 여러 "채널"을 통해 사용자와 채팅 수 있는 단일 봇을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-114">With the [Bot Framework](https://dev.botframework.com/) you can write a single bot that is able to chat with users across multiple "channels", like Skype, Microsoft Teams, Facebook Messenger, etc.</span></span>

## <a name="walkthrough"></a><span data-ttu-id="45c31-115">연습</span><span class="sxs-lookup"><span data-stu-id="45c31-115">Walkthrough</span></span>

<span data-ttu-id="45c31-116">봇을 Adaptive Card를 추가할 보다시피 상당히 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-116">It's pretty straight forward to add an Adaptive Card to your bot.</span></span>

### <a name="step-0-start-with-a-basic-message"></a><span data-ttu-id="45c31-117">0 단계: 기본 메시지를 사용 하 여 시작</span><span class="sxs-lookup"><span data-stu-id="45c31-117">Step 0: Start with a basic message</span></span>

<span data-ttu-id="45c31-118">여기에 표준 봇 프레임 워크 `message` 모든 채널을 제공할 수 있습니다 하 고 사용자에 게 텍스트를 표시 하는 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-118">Here's a standard Bot Framework `message` payload that can be delivered to any channel and display text to the user.</span></span>

```json
{
   "type": "message",
   "text": "Plain text is ok, but sometimes I long for more..."
}
```

### <a name="step-1-add-an-adaptive-card-attachment"></a><span data-ttu-id="45c31-119">1단계: Adaptive Card를 추가 합니다. `attachment`</span><span class="sxs-lookup"><span data-stu-id="45c31-119">Step 1: Add an Adaptive Card `attachment`</span></span>

<span data-ttu-id="45c31-120">Bot Framework에는 개념이 텍스트 이외의 일부 다양 한 기능을 추가 하려면 `attachments`합니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-120">To add some richness beyond just text, the Bot Framework has a concept of `attachments`.</span></span> 

<span data-ttu-id="45c31-121">사용자 지정 텍스트를 표시 하는 Adaptive Card를 연결 해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-121">Let's attach an Adaptive Card that displays custom text.</span></span>

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

### <a name="step-2-build-even-richer-cards"></a><span data-ttu-id="45c31-123">2단계: 풍부한 카드 빌드</span><span class="sxs-lookup"><span data-stu-id="45c31-123">Step 2: Build even richer cards</span></span> 

<span data-ttu-id="45c31-124">Adaptive Card 보다 훨씬 더 방금 사용자 지정 가능한 텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-124">Adaptive Cards offer much more than just customizable text.</span></span> 

<span data-ttu-id="45c31-125">다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-125">You can:</span></span> 

* <span data-ttu-id="45c31-126">추가 `Images` 카드로</span><span class="sxs-lookup"><span data-stu-id="45c31-126">Add `Images` to your card</span></span>
* <span data-ttu-id="45c31-127">사용 하 여 콘텐츠를 구성 `Containers` 및 `Columns`</span><span class="sxs-lookup"><span data-stu-id="45c31-127">Organize your content with `Containers` and `Columns`</span></span>
* <span data-ttu-id="45c31-128">여러 유형의 추가 `Actions`</span><span class="sxs-lookup"><span data-stu-id="45c31-128">Add multiple types of `Actions`</span></span>
* <span data-ttu-id="45c31-129">수집 `Input` 사용자의</span><span class="sxs-lookup"><span data-stu-id="45c31-129">Collect `Input` from your users</span></span>
* <span data-ttu-id="45c31-130">카드가 두 개 `show another card`</span><span class="sxs-lookup"><span data-stu-id="45c31-130">Have one card `show another card`</span></span>
* <span data-ttu-id="45c31-131">[전체 스키마 탐색기를 확인해](http://adaptivecards.io/explorer/)!</span><span class="sxs-lookup"><span data-stu-id="45c31-131">[Check out the full schema explorer](http://adaptivecards.io/explorer/)!</span></span> 

## <a name="platform-sdks"></a><span data-ttu-id="45c31-132">플랫폼 Sdk</span><span class="sxs-lookup"><span data-stu-id="45c31-132">Platform SDKs</span></span>

<span data-ttu-id="45c31-133">.NET 또는 NodeJS를 사용 하 여 봇을 개발 하는 경우 라이브러리도 쉽게 적응 카드를 만들 수 있도록 했습니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-133">If your bot is developed using .NET or NodeJS we have libraries to make building Adaptive Cards even easier.</span></span>

<span data-ttu-id="45c31-134">플랫폼</span><span class="sxs-lookup"><span data-stu-id="45c31-134">Platform</span></span>|<span data-ttu-id="45c31-135">Install</span><span class="sxs-lookup"><span data-stu-id="45c31-135">Install</span></span>|<span data-ttu-id="45c31-136">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="45c31-136">Learn more</span></span>
--------|-------|----------
<span data-ttu-id="45c31-137">.NET</span><span class="sxs-lookup"><span data-stu-id="45c31-137">.NET</span></span> | `Install-Package AdaptiveCards -IncludePrerelease` | [<span data-ttu-id="45c31-138">Bot Framework.NET 설명서</span><span class="sxs-lookup"><span data-stu-id="45c31-138">Bot Framework .NET Docs</span></span>](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-add-rich-card-attachments)
<span data-ttu-id="45c31-139">NodeJS</span><span class="sxs-lookup"><span data-stu-id="45c31-139">NodeJS</span></span> | `npm install adaptivecards` | [<span data-ttu-id="45c31-140">Bot Framework NodeJS Docs</span><span class="sxs-lookup"><span data-stu-id="45c31-140">Bot Framework NodeJS Docs</span></span>](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-send-rich-cards)


## <a name="channel-status"></a><span data-ttu-id="45c31-141">채널 상태</span><span class="sxs-lookup"><span data-stu-id="45c31-141">Channel status</span></span>

<span data-ttu-id="45c31-142">Bot Framework를 사용 하면 여러 채널에서 봇을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-142">The Bot Framework lets you publish your bot to multiple channels.</span></span> <span data-ttu-id="45c31-143">적응 카드에 대 한 전체 지원을 제공 하기 위해 다양 한 채널을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-143">We're working with various channels to provide full support for Adaptive Cards.</span></span> <span data-ttu-id="45c31-144">참조 된 [파트너 상태](../resources/partners.md) 최신 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="45c31-144">See the [Partner Status](../resources/partners.md) page for the latest.</span></span>


## <a name="dive-in"></a><span data-ttu-id="45c31-145">시작 해 보겠습니다!</span><span class="sxs-lookup"><span data-stu-id="45c31-145">Dive in!</span></span>

<span data-ttu-id="45c31-146">에서는 했습니다 기초적이 자습서에서는 따라서 하세요 다양 한 방법을 알아볼 Adaptive Card 봇의 향상 시킬 수는 아래와 같은 링크를 살펴보십시오.</span><span class="sxs-lookup"><span data-stu-id="45c31-146">We've just scratched the surface in this tutorial, so please take a look at the links below to explore more ways that Adaptive Cards can enhance your bot.</span></span>

* <span data-ttu-id="45c31-147">[샘플 카드 찾아보기](http://adaptivecards.io/samples/) 영감</span><span class="sxs-lookup"><span data-stu-id="45c31-147">[Browse Sample cards](http://adaptivecards.io/samples/) for inspiration</span></span>
* <span data-ttu-id="45c31-148">사용 된 [스키마 탐색기](http://adaptivecards.io/explorer) 사용 가능한 요소를 알아보려면</span><span class="sxs-lookup"><span data-stu-id="45c31-148">Use the [Schema Explorer](http://adaptivecards.io/explorer) to learn the available elements</span></span>
* <span data-ttu-id="45c31-149">카드를 통해 빌드를 [대화형 시각화 도우미](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)</span><span class="sxs-lookup"><span data-stu-id="45c31-149">Build a card using the [Interactive Visualizer](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)</span></span>
* <span data-ttu-id="45c31-150">[연락](http://adaptivecards.io/connect) 피드백을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="45c31-150">[Get in touch](http://adaptivecards.io/connect) with any feedback you have</span></span>
