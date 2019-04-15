---
title: IOS SDK-카드를 렌더링 합니다.
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 625701e38389cc1a54682b72ce2315c14180e576
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552475"
---
# <a name="render-a-card---ios"></a><span data-ttu-id="e41f1-102">IOS-카드를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41f1-102">Render a card - iOS</span></span>

<span data-ttu-id="e41f1-103">IOS SDK를 사용 하 여 카드를 렌더링 하는 방법을 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e41f1-103">Here's how to render a card using the iOS SDK.</span></span>

## <a name="create-a-card-from-a-json-string"></a><span data-ttu-id="e41f1-104">JSON 문자열에서 카드 만들기</span><span class="sxs-lookup"><span data-stu-id="e41f1-104">Create a card from a JSON string</span></span>

<span data-ttu-id="e41f1-105">AdaptiveCard는 JSON 문자열에서 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e41f1-105">AdaptiveCard is generated from JSON string</span></span>

```objective-c
ACOParseResult *cardParseResult = [ACOAdaptiveCards FromJson:jsonStr];
/// access for parse warnings and errors
NSArray<NSError *> errors = cardParseResult.parseErrors;
NSArray<ACRParseWarning *> warnings = cardPraseResult.parseWarnings;
```

## <a name="render-a-card"></a><span data-ttu-id="e41f1-106">카드를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41f1-106">Render a Card</span></span>

<span data-ttu-id="e41f1-107">Rederer는 적응 카드 및 호스트 구성 합니다. HostConfig nil, 수 및 nil 기본값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e41f1-107">Rederer takes adaptive card and host config. HostConfig can be nil, and if nil, default value will be used.</span></span>

```objective-c
ACRRenderResult *renderResult;
renderResult = [ACRRenderer render:cardParseResult.card
                            config:nil
                   widthConstraint:300.0];
``` 

### <a name="example"></a><span data-ttu-id="e41f1-108">예제</span><span class="sxs-lookup"><span data-stu-id="e41f1-108">Example</span></span>

```objective-c
ACRRenderResult *renderResult;
ACOHostConfigParseResult *hostconfigParseResult = [ACOHostConfig FromJson:self.hostconfig];
ACOAdaptiveCardsParseResult *cardParseResult       = [ACOAdaptiveCards FromJson:jsonStr];

// checking parse result
if(hostconfigParseResult.IsValid == YES && cardParseResult.IsValid == YES)
{
    renderResult = [ACRRenderer render:cardParseResult.card
                                config:hostconfigParseResult.config
                       widthConstraint:300.0];
}   
    
if(renderResult.Suceeded == YES)
{
    // access returned UIView object
    ACRView *adaptiveView = renderResult.view;
    [self.view addSubview:adcVc.view];
}
```

### <a name="render-a-card-as-uiviewcontroller"></a><span data-ttu-id="e41f1-109">카드 UIViewController 렌더링</span><span class="sxs-lookup"><span data-stu-id="e41f1-109">Render a Card as UIViewController</span></span>

<span data-ttu-id="e41f1-110">AdaptiveCard 렌더러 UIViewController를 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e41f1-110">AdaptiveCard renderer can also return UIViewController.</span></span>

```objective-c
ACRRenderResult *renderResult = [ACRRenderer renderAsViewController:card config:config frame:frame delegate:acrActionDelegate];

renderResult.viewif(renderResult.Suceeded == YES)
{
    ACRViewController *adaptiveViewController = renderResult.viewcontroller;
    [self addChildViewController:adaptiveViewController];
    [self.view addSubview:adaptiveViewController.view];
    [adaptiveViewController didMoveToParentViewController:self];
    ...
}
```

<span data-ttu-id="e41f1-111">UIView 자동 레이아웃을 사용 하 여 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41f1-111">Returned UIView uses autolayout.</span></span> <span data-ttu-id="e41f1-112">너비가는 widthConstraint 설정한 값으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e41f1-112">Width will be constraint to the value set by widthConstraint.</span></span> <span data-ttu-id="e41f1-113">0 값을 사용 하는 경우에 연결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e41f1-113">If 0 value is used, it won't be bound.</span></span>
<span data-ttu-id="e41f1-114">높이 바인딩되지 않은 시간과 렌더링 하는 모든 콘텐츠의 합계의 높이 것을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41f1-114">Height is not bound, and when returned it will have the height of sums of all contents rendered.</span></span> <span data-ttu-id="e41f1-115">차원 보기에 바인딩된 NSLayoutConstraint 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e41f1-115">To bound the view dimension, please use NSLayoutConstraint.</span></span> <span data-ttu-id="e41f1-116">정확한 차원이입니다 ACRViewController 사용 되는 경우 상위 뷰의 viewcontroller 또는 동일한 이름 가진 해당 메서드의 viewDidLayoutSubview 컨텍스트에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e41f1-116">The exact dimension is accessible from the context of viewDidLayoutSubview of its superview's viewcontroller or its method with the same name if ACRViewController is used.</span></span>


### <a name="compact-style-inputchoiceset"></a><span data-ttu-id="e41f1-117">Compact 스타일 Input.ChoiceSet</span><span class="sxs-lookup"><span data-stu-id="e41f1-117">Compact Style Input.ChoiceSet</span></span>

<span data-ttu-id="e41f1-118">Input.ChoiceSet의 UI 표현을 UINavigationController, 있고는 현재 활성 UIViewController UIView 선택 작업을 허용 하는 전환 하 게 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41f1-118">UI representation of Input.ChoiceSet has UINavigationController, and it needs to be presented to a presently active UIViewController to transition into UIView that allows user selection.</span></span>

<span data-ttu-id="e41f1-119">이렇게 하려면 ACRActionDelegate의 didFecthSecondaryView를 구현 하세요.</span><span class="sxs-lookup"><span data-stu-id="e41f1-119">To accomplish that, please implement didFecthSecondaryView of ACRActionDelegate.</span></span>

```objective-c
- (void)didFetchSecondaryView:(ACOAdaptiveCard *)card navigationController:(UINavigationController *)navigationController{
    [self presentViewController:navigationController animated:YES completion:nil];
}  
```

<span data-ttu-id="e41f1-120">대리자를 후크 되었습니다에, 하는 경우 이렇게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41f1-120">If the delgate has not been hooked up, do so.</span></span>

```objective-c
adaptiveView.acrActionDelegate = self
```