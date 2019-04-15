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
# <a name="render-a-card---ios"></a>IOS-카드를 렌더링 합니다.

IOS SDK를 사용 하 여 카드를 렌더링 하는 방법을 다음과 같습니다.

## <a name="create-a-card-from-a-json-string"></a>JSON 문자열에서 카드 만들기

AdaptiveCard는 JSON 문자열에서 생성 됩니다.

```objective-c
ACOParseResult *cardParseResult = [ACOAdaptiveCards FromJson:jsonStr];
/// access for parse warnings and errors
NSArray<NSError *> errors = cardParseResult.parseErrors;
NSArray<ACRParseWarning *> warnings = cardPraseResult.parseWarnings;
```

## <a name="render-a-card"></a>카드를 렌더링 합니다.

Rederer는 적응 카드 및 호스트 구성 합니다. HostConfig nil, 수 및 nil 기본값이 사용 됩니다.

```objective-c
ACRRenderResult *renderResult;
renderResult = [ACRRenderer render:cardParseResult.card
                            config:nil
                   widthConstraint:300.0];
``` 

### <a name="example"></a>예제

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

### <a name="render-a-card-as-uiviewcontroller"></a>카드 UIViewController 렌더링

AdaptiveCard 렌더러 UIViewController를 반환할 수도 있습니다.

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

UIView 자동 레이아웃을 사용 하 여 반환 합니다. 너비가는 widthConstraint 설정한 값으로 제한 됩니다. 0 값을 사용 하는 경우에 연결 되지 않습니다.
높이 바인딩되지 않은 시간과 렌더링 하는 모든 콘텐츠의 합계의 높이 것을 반환 합니다. 차원 보기에 바인딩된 NSLayoutConstraint 사용 하십시오. 정확한 차원이입니다 ACRViewController 사용 되는 경우 상위 뷰의 viewcontroller 또는 동일한 이름 가진 해당 메서드의 viewDidLayoutSubview 컨텍스트에서 액세스할 수 있습니다.


### <a name="compact-style-inputchoiceset"></a>Compact 스타일 Input.ChoiceSet

Input.ChoiceSet의 UI 표현을 UINavigationController, 있고는 현재 활성 UIViewController UIView 선택 작업을 허용 하는 전환 하 게 표시 해야 합니다.

이렇게 하려면 ACRActionDelegate의 didFecthSecondaryView를 구현 하세요.

```objective-c
- (void)didFetchSecondaryView:(ACOAdaptiveCard *)card navigationController:(UINavigationController *)navigationController{
    [self presentViewController:navigationController animated:YES completion:nil];
}  
```

대리자를 후크 되었습니다에, 하는 경우 이렇게 합니다.

```objective-c
adaptiveView.acrActionDelegate = self
```