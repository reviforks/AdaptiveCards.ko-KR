---
title: 카드 렌더링 - iOS SDK
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 7d8d8410c030584dc5a518af7e6473d1d51f3991
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67134324"
---
# <a name="render-a-card---ios"></a>카드 렌더링 - iOS

iOS SDK를 사용하여 카드를 렌더링하는 방법은 다음과 같습니다.

## <a name="create-a-card-from-a-json-string"></a>JSON 문자열에서 카드 만들기

AdaptiveCard는 JSON 문자열에서 생성

```objective-c

NSString *jsonStr = @"{ \"type\": \"AdaptiveCard\", \"version\": \"1.0\", \"body\": [ { \"type\": \"Image\", \"url\": \"http://adaptivecards.io/content/adaptive-card-50.png\", \"horizontalAlignment\":\"center\" }, { \"type\": \"TextBlock\", \"horizontalAlignment\":\"center\", \"text\": \"Hello **Adaptive Cards!**\" } ], \"actions\": [ { \"type\": \"Action.OpenUrl\", \"title\": \"Learn more\", \"url\": \"http://adaptivecards.io\" }, { \"type\": \"Action.OpenUrl\", \"title\": \"GitHub\", \"url\": \"http://github.com/Microsoft/AdaptiveCards\" } ] }";
ACOAdaptiveCardParseResult *cardParseResult = [ACOAdaptiveCard fromJson:jsonStr];

/// access for parse warnings and errors
NSArray<NSError *> errors = cardParseResult.parseErrors;
NSArray<ACRParseWarning *> warnings = cardPraseResult.parseWarnings;
```

## <a name="render-a-card"></a>카드 렌더링

렌더러는 적응형 카드와 호스트 구성을 사용합니다. HostConfig는 nil일 수 있으며, nil인 경우 기본값이 사용됩니다.
반환된 UIView는 자동 레이아웃을 사용합니다. 너비는 widthConstraint에서 설정한 값에 따라 제한됩니다. 0 값을 사용하면 바인딩되지 않습니다.
높이가 바인딩되지 않으며, 반환될 때 렌더링된 모든 콘텐츠의 합이 높이로 사용됩니다. 새 차원을 바인딩하려면 NSLayoutConstraint를 사용하세요. 정확한 차원은 상위 보기 viewcontroller의 viewDidLayoutSubview 컨텍스트에서 또는 ACRViewController가 사용되는 경우 이름이 같은 메서드에서 액세스할 수 있습니다.

```objective-c
ACRRenderResult *renderResult;
if(cardParseResult.isValid){
    renderResult = [ACRRenderer render:cardParseResult.card config:nil widthConstraint:335];
}
``` 
### <a name="example"></a>예제

```objective-c
--------------------------------------------------------------------------------
ViewController.m
--------------------------------------------------------------------------------
#import "ViewController.h"
#import <SafariServices/SafariServices.h>

@interface ViewController ()

@end

@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];

    NSString *jsonStr = @"{ \"type\": \"AdaptiveCard\", \"version\": \"1.0\", \"body\": [ { \"type\": \"Image\", \"url\": \"http://adaptivecards.io/content/adaptive-card-50.png\", \"horizontalAlignment\":\"center\" }, { \"type\": \"TextBlock\", \"horizontalAlignment\":\"center\", \"text\": \"Hello **Adaptive Cards!**\" } ], \"actions\": [ { \"type\": \"Action.OpenUrl\", \"title\": \"Learn more\", \"url\": \"http://adaptivecards.io\" }, { \"type\": \"Action.OpenUrl\", \"title\": \"GitHub\", \"url\": \"http://github.com/Microsoft/AdaptiveCards\" } ] }";
    ACRRenderResult *renderResult;
    ACOAdaptiveCardParseResult *cardParseResult = [ACOAdaptiveCard fromJson:jsonStr];
    if(cardParseResult.isValid){
        renderResult = [ACRRenderer render:cardParseResult.card config:nil widthConstraint:335];
    }

    if(renderResult.succeeded)
    {
        ACRView *ad = renderResult.view;
        ad.acrActionDelegate = self;
        
        UIView *view = self.view;
        view.autoresizingMask |= UIViewAutoresizingFlexibleHeight;
        [self.view addSubview:ad];
        ad.translatesAutoresizingMaskIntoConstraints = NO;
        
        [NSLayoutConstraint constraintWithItem:ad attribute:NSLayoutAttributeCenterX relatedBy:NSLayoutRelationEqual toItem:view attribute:NSLayoutAttributeCenterX multiplier:1.0 constant:0].active = YES;

        [NSLayoutConstraint constraintWithItem:ad attribute:NSLayoutAttributeCenterY relatedBy:NSLayoutRelationEqual toItem:view attribute:NSLayoutAttributeCenterY multiplier:1.0 constant:3].active = YES;
    }
}

- (void)didFetchUserResponses:(ACOAdaptiveCard *)card action:(ACOBaseActionElement *)action
{
    if(action.type == ACROpenUrl){
        NSURL *url = [NSURL URLWithString:[action url]];
        SFSafariViewController *svc = [[SFSafariViewController alloc] initWithURL:url];
        [self presentViewController:svc animated:YES completion:nil];
    }
}

@end

```

```swift
--------------------------------------------------------------------------------
ViewController.swft
--------------------------------------------------------------------------------

import UIKit
import SafariServices

class ViewController: UIViewController, ACRActionDelegate {

    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
        let jsonStr = "{ \"type\": \"AdaptiveCard\", \"version\": \"1.0\", \"body\": [ { \"type\": \"Image\", \"url\": \"http://adaptivecards.io/content/adaptive-card-50.png\", \"horizontalAlignment\":\"center\" }, { \"type\": \"TextBlock\", \"horizontalAlignment\":\"center\", \"text\": \"Hello **Adaptive Cards!**\" } ], \"actions\": [ { \"type\": \"Action.OpenUrl\", \"title\": \"Learn more\", \"url\": \"http://adaptivecards.io\" }, { \"type\": \"Action.OpenUrl\", \"title\": \"GitHub\", \"url\": \"http://github.com/Microsoft/AdaptiveCards\" } ] }";

        let cardParseResult = ACOAdaptiveCard.fromJson(jsonStr);
        if((cardParseResult?.isValid)!){
            let renderResult = ACRRenderer.render(cardParseResult!.card, config: nil, widthConstraint: 335);

            if(renderResult?.succeeded ?? false)
            {
                let ad = renderResult?.view;
                ad!.acrActionDelegate = (self as ACRActionDelegate);
                self.view.autoresizingMask = [.flexibleHeight];
                self.view.addSubview(ad!);
                ad!.translatesAutoresizingMaskIntoConstraints = false;
    
                NSLayoutConstraint(item: ad!, attribute: .centerX, relatedBy: .equal, toItem: view, attribute: .centerX, multiplier: 1.0, constant: 0).isActive = true;
                NSLayoutConstraint(item: ad!, attribute: .centerY, relatedBy: .equal, toItem: view, attribute: .centerY, multiplier: 1.0, constant: 3).isActive = true;
            }
        }
    }

    func didFetchUserResponses(_ card: ACOAdaptiveCard, action: ACOBaseActionElement)
    {
        if(action.type == ACRActionType.openUrl){
            let url = URL.init(string:action.url());
            let svc = SFSafariViewController.init(url: url!);
            self.present(svc, animated: true, completion: nil);
        }
    }

}
```
