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
# <a name="adaptive-cards-for-bot-developers"></a><span data-ttu-id="5bdbc-102">봇 개발자용 적응형 카드</span><span class="sxs-lookup"><span data-stu-id="5bdbc-102">Adaptive Cards for Bot Developers</span></span>

<span data-ttu-id="5bdbc-103">적응형 카드는 봇에 매우 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-103">Adaptive Cards are a great fit for Bots.</span></span> <span data-ttu-id="5bdbc-104">카드를 한 번 작성한 후 Microsoft Teams와 같은 여러 앱, 자신의 웹 사이트 등에 멋지게 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-104">They let you author a card once and have it render beautifully inside multiple apps, like  Microsoft Teams, your own website, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="5bdbc-105">현재 미리 보기에서는 Skype가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-105">Skype is not supported in the current preview.</span></span> <span data-ttu-id="5bdbc-106">최신 정보는 [파트너 상태](../resources/partners.md) 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-106">See the [Partner Status](../resources/partners.md) page for the latest.</span></span>

## <a name="try-it-out"></a><span data-ttu-id="5bdbc-107">시도해보기</span><span class="sxs-lookup"><span data-stu-id="5bdbc-107">Try it out</span></span>

<span data-ttu-id="5bdbc-108">다음 링크를 클릭하고 [Scuba Bot과 이야기하세요](http://contososcubademo.azurewebsites.net/).</span><span class="sxs-lookup"><span data-stu-id="5bdbc-108">Click the following link and [talk to our Scuba Bot](http://contososcubademo.azurewebsites.net/).</span></span> <span data-ttu-id="5bdbc-109">`I'm looking for scuba`라고 말하면 꿈꾸던 스쿠버 여행을 예약하도록 도와줄 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-109">Say `I'm looking for scuba` and it'll help you book the scuba trip of your dreams.</span></span>  

<span data-ttu-id="5bdbc-110">모든 봇 응답은 적응형 카드를 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-110">All of the bot's responses are created with Adaptive Cards.</span></span>

<span data-ttu-id="5bdbc-111">[![스쿠버 채팅 스크린샷](media/bots/scuba-chat.png)](http://contososcubademo.azurewebsites.net/)</span><span class="sxs-lookup"><span data-stu-id="5bdbc-111">[![Scuba chat screenshot](media/bots/scuba-chat.png)](http://contososcubademo.azurewebsites.net/)</span></span>

<span data-ttu-id="5bdbc-112">**코드 확인**: 전체 [Contoso Scuba Bot 소스 코드](https://github.com/matthidinger/ContosoScubaBot
)는 GitHub에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-112">**Get the code**: the full [Contoso Scuba Bot source code](https://github.com/matthidinger/ContosoScubaBot
) can be found on GitHub.</span></span>


## <a name="bot-framework-integration"></a><span data-ttu-id="5bdbc-113">Bot Framework 통합</span><span class="sxs-lookup"><span data-stu-id="5bdbc-113">Bot Framework Integration</span></span>

<span data-ttu-id="5bdbc-114">[Bot Framework](https://dev.botframework.com/)를 사용하여 Skype, Microsoft Teams, Facebook Messenger 등과 같은 여러 "채널"을 통해 사용자와 채팅할 수 있는 단일 봇을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-114">With the [Bot Framework](https://dev.botframework.com/) you can write a single bot that is able to chat with users across multiple "channels", like Skype, Microsoft Teams, Facebook Messenger, etc.</span></span>

## <a name="walkthrough"></a><span data-ttu-id="5bdbc-115">연습</span><span class="sxs-lookup"><span data-stu-id="5bdbc-115">Walkthrough</span></span>

<span data-ttu-id="5bdbc-116">봇에 적응형 카드를 추가하는 방법은 상당히 직관적입니다.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-116">It's pretty straight forward to add an Adaptive Card to your bot.</span></span>

### <a name="step-0-start-with-a-basic-message"></a><span data-ttu-id="5bdbc-117">0단계: 기본 메시지를 사용하여 시작</span><span class="sxs-lookup"><span data-stu-id="5bdbc-117">Step 0: Start with a basic message</span></span>

<span data-ttu-id="5bdbc-118">모든 채널에 제공하고 사용자에게 텍스트를 표시할 수 있는 표준 Bot Framework `message` 페이로드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-118">Here's a standard Bot Framework `message` payload that can be delivered to any channel and display text to the user.</span></span>

```json
{
   "type": "message",
   "text": "Plain text is ok, but sometimes I long for more..."
}
```

### <a name="step-1-add-an-adaptive-card-attachment"></a><span data-ttu-id="5bdbc-119">1단계: 적응형 카드 `attachment` 추가</span><span class="sxs-lookup"><span data-stu-id="5bdbc-119">Step 1: Add an Adaptive Card `attachment`</span></span>

<span data-ttu-id="5bdbc-120">Bot Framework에는 텍스트 이외의 서식을 추가할 수 있는 `attachments`라는 개념이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-120">To add some richness beyond just text, the Bot Framework has a concept of `attachments`.</span></span> 

<span data-ttu-id="5bdbc-121">사용자 지정 텍스트를 표시하는 적응형 카드를 연결해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-121">Let's attach an Adaptive Card that displays custom text.</span></span>

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

### <a name="step-2-build-even-richer-cards"></a><span data-ttu-id="5bdbc-123">2단계: 서식이 더 많은 카드 작성</span><span class="sxs-lookup"><span data-stu-id="5bdbc-123">Step 2: Build even richer cards</span></span> 

<span data-ttu-id="5bdbc-124">적응형 카드는 사용자 지정 가능한 텍스트보다 훨씬 더 많은 서식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-124">Adaptive Cards offer much more than just customizable text.</span></span> 

<span data-ttu-id="5bdbc-125">다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-125">You can:</span></span> 

* <span data-ttu-id="5bdbc-126">카드에 `Images` 추가</span><span class="sxs-lookup"><span data-stu-id="5bdbc-126">Add `Images` to your card</span></span>
* <span data-ttu-id="5bdbc-127">`Containers` 및 `Columns`를 사용하여 콘텐츠 구성</span><span class="sxs-lookup"><span data-stu-id="5bdbc-127">Organize your content with `Containers` and `Columns`</span></span>
* <span data-ttu-id="5bdbc-128">여러 유형의 `Actions` 추가</span><span class="sxs-lookup"><span data-stu-id="5bdbc-128">Add multiple types of `Actions`</span></span>
* <span data-ttu-id="5bdbc-129">사용자로부터 `Input` 수집</span><span class="sxs-lookup"><span data-stu-id="5bdbc-129">Collect `Input` from your users</span></span>
* <span data-ttu-id="5bdbc-130">한 카드에 `show another card` 명령</span><span class="sxs-lookup"><span data-stu-id="5bdbc-130">Have one card `show another card`</span></span>
* <span data-ttu-id="5bdbc-131">[전체 스키마 탐색기를 확인해 보세요](http://adaptivecards.io/explorer/)!</span><span class="sxs-lookup"><span data-stu-id="5bdbc-131">[Check out the full schema explorer](http://adaptivecards.io/explorer/)!</span></span> 

## <a name="platform-sdks"></a><span data-ttu-id="5bdbc-132">플랫폼 SDK</span><span class="sxs-lookup"><span data-stu-id="5bdbc-132">Platform SDKs</span></span>

<span data-ttu-id="5bdbc-133">봇이 .NET 또는 NodeJS를 사용하여 개발된 경우 라이브러리를 사용하여 적응형 카드를 훨씬 더 쉽게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-133">If your bot is developed using .NET or NodeJS we have libraries to make building Adaptive Cards even easier.</span></span>

<span data-ttu-id="5bdbc-134">플랫폼</span><span class="sxs-lookup"><span data-stu-id="5bdbc-134">Platform</span></span>|<span data-ttu-id="5bdbc-135">설치</span><span class="sxs-lookup"><span data-stu-id="5bdbc-135">Install</span></span>|<span data-ttu-id="5bdbc-136">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="5bdbc-136">Learn more</span></span>
--------|-------|----------
<span data-ttu-id="5bdbc-137">.NET</span><span class="sxs-lookup"><span data-stu-id="5bdbc-137">.NET</span></span> | `Install-Package AdaptiveCards -IncludePrerelease` | [<span data-ttu-id="5bdbc-138">Bot Framework .NET 문서</span><span class="sxs-lookup"><span data-stu-id="5bdbc-138">Bot Framework .NET Docs</span></span>](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-add-rich-card-attachments)
<span data-ttu-id="5bdbc-139">NodeJS</span><span class="sxs-lookup"><span data-stu-id="5bdbc-139">NodeJS</span></span> | `npm install adaptivecards` | [<span data-ttu-id="5bdbc-140">Bot Framework NodeJS 문서</span><span class="sxs-lookup"><span data-stu-id="5bdbc-140">Bot Framework NodeJS Docs</span></span>](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-send-rich-cards)


## <a name="channel-status"></a><span data-ttu-id="5bdbc-141">채널 상태</span><span class="sxs-lookup"><span data-stu-id="5bdbc-141">Channel status</span></span>

<span data-ttu-id="5bdbc-142">Bot Framework를 사용하여 여러 채널에 봇을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-142">The Bot Framework lets you publish your bot to multiple channels.</span></span> <span data-ttu-id="5bdbc-143">Microsoft는 적응형 카드에 대한 완벽한 지원을 제공하기 위해 다양한 채널과 협업하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-143">We're working with various channels to provide full support for Adaptive Cards.</span></span> <span data-ttu-id="5bdbc-144">최신 정보는 [파트너 상태](../resources/partners.md) 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-144">See the [Partner Status](../resources/partners.md) page for the latest.</span></span>


## <a name="dive-in"></a><span data-ttu-id="5bdbc-145">자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-145">Dive in!</span></span>

<span data-ttu-id="5bdbc-146">이 자습서에서는 극히 일부만 다루었으므로 적응형 카드로 봇을 개선하는 더 많은 방법을 살펴보려면 아래의 링크를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5bdbc-146">We've just scratched the surface in this tutorial, so please take a look at the links below to explore more ways that Adaptive Cards can enhance your bot.</span></span>

* <span data-ttu-id="5bdbc-147">영감을 얻기 위해 [샘플 카드 찾아보기](http://adaptivecards.io/samples/)</span><span class="sxs-lookup"><span data-stu-id="5bdbc-147">[Browse Sample cards](http://adaptivecards.io/samples/) for inspiration</span></span>
* <span data-ttu-id="5bdbc-148">[스키마 탐색기](http://adaptivecards.io/explorer)를 사용하여 사용 가능한 요소 알아보기</span><span class="sxs-lookup"><span data-stu-id="5bdbc-148">Use the [Schema Explorer](http://adaptivecards.io/explorer) to learn the available elements</span></span>
* <span data-ttu-id="5bdbc-149">[대화형 비주얼라이저](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)를 사용하여 카드 작성</span><span class="sxs-lookup"><span data-stu-id="5bdbc-149">Build a card using the [Interactive Visualizer](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)</span></span>
* <span data-ttu-id="5bdbc-150">모든 피드백과 [연결 유지](http://adaptivecards.io/connect)</span><span class="sxs-lookup"><span data-stu-id="5bdbc-150">[Get in touch](http://adaptivecards.io/connect) with any feedback you have</span></span>
