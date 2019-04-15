---
title: 확장성-iOS SDK
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: c3dcae7ef2347201b5f7ce02baf3204db7ee27d6
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553565"
---
# <a name="extensibility---ios"></a><span data-ttu-id="d6d9c-102">확장성-iOS</span><span class="sxs-lookup"><span data-stu-id="d6d9c-102">Extensibility - iOS</span></span>

## <a name="changing-per-element-rendering"></a><span data-ttu-id="d6d9c-103">요소 렌더링 당 변경</span><span class="sxs-lookup"><span data-stu-id="d6d9c-103">Changing per element rendering</span></span>

<span data-ttu-id="d6d9c-104">개발자는 TextBlock 등 renderred AdaptiveCards 요소의 모양을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-104">Developers can customize the look of renderred AdaptiveCards elements such as TextBlock.</span></span>
<span data-ttu-id="d6d9c-105">다음 예제에서는 하나 NumberInput의 배경색을 변경할 수는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-105">Following example shows how one can change background color of NumberInput.</span></span>

```objective-c
ACRRegistration *registration = [ACRRegistration getInstance];
// register custom renderer with registration
// custom renderer must implement ACRIBaseCardElementRenderer protocol
// for more information, please refer to CustomInputNumberRenderer.mm
 [registration setBaseCardElementRenderer:[CustomInputNumberRenderer getInstance] cardElementType:ACRNumberInput];
 ...
/// CustiomInputNumberRenderer.mm
- (UIView *)render:(UIView<ACRIContentHoldingView> *)viewGroup
              rootViewController:(UIViewController *)vc
              inputs:(NSArray *)inputs
     baseCardElement:(ACOBaseCardElement *)acoElem
          hostConfig:(ACOHostConfig *)acoConfig
  {
      ACRInputNumberRenderer *defaultRenderer = [ACRInputNumberRenderer getInstance];
 
      UIView *input = [defaultRenderer render:viewGroup
                           rootViewController:vc
                                       inputs:inputs
                              baseCardElement:acoElem
                                   hostConfig:acoConfig];
      if(input)
      {   
          // customize background color of input
          [input setBackgroundColor: [UIColor colorWithRed:1.0
                                                     green:59.0/255.0
                                                      blue:48.0/255.0
                                                     alpha:1.0]];
      }
      return input;
  }
  ```

 ## <a name="additional-property"></a><span data-ttu-id="d6d9c-106">추가 속성</span><span class="sxs-lookup"><span data-stu-id="d6d9c-106">Additional Property</span></span>

 <span data-ttu-id="d6d9c-107">개발자 또한 json 페이로드의 일부로 추가 속성에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-107">Developers can also send in additional properties as part of json payload.</span></span>
<span data-ttu-id="d6d9c-108">예를 들어, "간격" 및 "id" BaseCardElement에 대 한 json 페이로드 외에도 해당 json 페이로드에 TextBlock의 모퉁이 대 한 반지름을 추가할 수 하나.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-108">For example, in addition to "spacing" and "id" of json payload for BaseCardElement, one can add radius for corners of TextBlock to its json payload.</span></span>

 ```objective-c
 "type":"TextBlock",
 ...
 "radius":20,
 ...
 ```

 ```objective-c
         NSData *additionalProperty = [acoElem additionalProperty];
          if(additionalProperty) {
              NSDictionary *dictionary = [NSJSONSerialization JSONObjectWithData:additionalProperty options:NSJSONReadingMutableLeaves error:nil];
              radiusForMyTextBlock = dictionary[@"radius"];
          ...
```
 ## <a name="custom-parsing"></a><span data-ttu-id="d6d9c-109">구문 분석 하는 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d6d9c-109">Custom Parsing</span></span>

<span data-ttu-id="d6d9c-110">또한 개발자가 사용자 지정 구문 분석 하 고 진행률 표시줄과 같은 adpative 카드에 추가 하는 새 UI 요소가 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-110">Developers can also have custom parsing and have new UI element added to adpative card such as progress bar.</span></span> <span data-ttu-id="d6d9c-111">세부 정보에 대 한 CustomProgressBarRenderer.mm를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-111">Please check CustomProgressBarRenderer.mm for detail.</span></span>
<span data-ttu-id="d6d9c-112">사용자 지정 파서 ACOIBaseCardElementParser 프로토콜을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-112">Custom parser must implement ACOIBaseCardElementParser protocol.</span></span> <span data-ttu-id="d6d9c-113">deserializeToCustomElement 메서드 NSData로 지정 하는 json 페이로드를 지정 하는 구문 분석 하 고 렌더링 AdaptiveCard 개체에 추가 될 UIView 개체에 대 한 포인터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-113">deserializeToCustomElement method should parses given json payload given as NSData and return a pointer to UIView object that will be added to AdaptiveCard rendered object.</span></span>

```objective-c
      CustomProgressBarRenderer *progressBarRenderer = [[CustomProgressBarRenderer alloc] init];
      [registration setCustomElementParser:progressBarRenderer];
```objective-c