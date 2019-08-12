---
title: 템플릿 개요
author: matthidinger
ms.author: mahiding
ms.date: 07/29/2019
ms.topic: article
ms.openlocfilehash: ca21c70abc4638db8f96f3564d9e006aea39f926
ms.sourcegitcommit: a16f53ba10a8607deacde5c8cc78927cac58657c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68878950"
---
# <a name="adaptive-cards-templating-preview"></a>적응형 카드 템플릿(미리 보기)

적응형 카드를 **생성**, **재사용**, **공유**하는 데 도움이 되는 새로운 도구의 미리 보기를 공유하게 되어 기쁩니다. 

> [!IMPORTANT] 
> 
> 이러한 기능은 **미리 보기 상태이며 변경될 수 있습니다**. 사용자 의견은 언제나 환영이며, **사용자**에게 필요한 기능을 제공하는 데 중요합니다.

## <a name="how-can-templating-help-you"></a>템플릿을 어떻게 활용할 수 있을까요?

템플릿을 사용하면 적응형 카드에서 **레이아웃**과 **데이터**를 분리할 수 있습니다. 

### <a name="it-helps-design-a-card-once-and-then-populate-it-with-real-data"></a>카드를 한 번 디자인하고 실제 데이터로 채우는 데 유용

현재 [적응형 카드 디자이너](https://adaptivecards.io/designer)를 사용하여 카드를 만든 다음, 해당 JSON을 사용하여 **동적 콘텐츠**로 페이로드를 채울 수는 없습니다. 이 작업을 수행하려면 사용자 지정 코드를 작성하여 JSON 문자열을 빌드하거나 개체 모델 SDK를 사용하여 카드를 나타내는 OM을 빌드하고 JSON으로 직렬화해야 합니다. 어떤 경우든 디자이너는 일회성 단방향 작업이며 나중에 코드로 변환한 후에는 카드 디자인을 쉽게 조정할 수 없습니다.

### <a name="it-makes-tranmissions-over-the-wire-smaller"></a>유선 전송 간소화

템플릿과 데이터를 **클라이언트에서 직접** 결합할 수 있는 환경을 생각해 보세요. 즉, 동일한 템플릿을 여러 번 사용하거나 새 데이터를 사용하여 업데이트하려는 경우 새 데이터를 디바이스에 전송하기만 하면 동일한 템플릿을 계속 다시 사용할 수 있습니다.

### <a name="it-helps-you-create-a-great-looking-card-from-just-the-data-you-provide"></a>자신이 제공하는 데이터로만 멋진 카드를 만드는 데 유용

적응형 카드도 좋지만 사용자에게 표시하려는 모든 항목에 대한 적응형 카드를 작성할 필요가 없다면 어떨까요? 아래에 설명된 템플릿 서비스를 사용하면 모든 사용자가 모든 유형의 데이터에 대한 템플릿을 기고, 검색 및 공유할 수 있는 환경을 만들 수 있습니다. 

자체 프로젝트, 조직 내에서 또는 전체 인터넷과 공유할 수 있습니다.

### <a name="ai-and-other-services-could-improve-user-experiences"></a>AI 및 기타 서비스를 통해 사용자 환경 개선 가능

콘텐츠와 데이터를 분리하여 AI 및 기타 서비스가 카드에 표시되는 데이터를 "추론"할 수 있게 해주고, 사용자 생산성을 개선하거나 항목을 검색할 수 있게 해줍니다.

## <a name="what-is-adaptive-cards-templating"></a>적응형 카드 템플릿이란?

3가지 주요 구성 요소로 이루어져 있습니다.

1. **[템플릿 언어](language.md)** 는 템플릿을 작성하는 데 사용되는 구문입니다. 디자이너를 사용하여 디자인 타임에 "샘플 데이터"를 포함하여 템플릿을 미리 볼 수도 있습니다.
2. **[템플릿 SDK](sdk.md)** 는 지원되는 모든 적응형 카드 플랫폼에 존재합니다. 이러한 SDK를 사용하여 백 엔드에서 또는 클라이언트에서 직접 실제 데이터로 템플릿을 채울 수 있습니다. 
3. **[템플릿 서비스](service.md)** 는 누구나 잘 알려진 템플릿 세트를 찾고, 기고하고, 공유할 수 있게 해주는 개념 증명 서비스입니다.

## <a name="template-language"></a>템플릿 언어

템플릿 언어는 적응형 카드 템플릿을 작성하는 데 사용되는 구문입니다. 

> [!NOTE]
> 
> 다음 링크를 새 탭에서 열고 아래 예를 따라 진행합니다.
>
> **https://vnext.adaptivecards.io/designer**
> 
> 디자인 모드와 미리 보기 모드 간에 전환하려면 **미리 보기 모드** 단추를 클릭합니다.

![디자이너 스크린샷](content/2019-08-01-13-58-27.png)

["vNext Designer](https://vnext.adaptivecards.io/designer)"는 템플릿을 작성하고 디자인 타임에 카드를 미리 볼 수 있게 **샘플 데이터**를 제공하는 지원 기능을 추가합니다.

아래 예를 **카드 페이로드 편집기** 창에 붙여넣습니다. 

**EmployeeCardTemplate.json**

```json
{
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "ColumnSet",
            "style": "accent",
            "bleed": true,
            "columns": [
                {
                    "type": "Column",
                    "width": "auto",
                    "items": [
                        {
                            "type": "Image",
                            "url": "{photo}",
                            "altText": "Profile picture",
                            "size": "Small",
                            "style": "Person"
                        }
                    ]
                },
                {
                    "type": "Column",
                    "width": "stretch",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Hi {name}!",
                            "size": "Medium"
                        },
                        {
                            "type": "TextBlock",
                            "text": "Here's a bit about your org...",
                            "spacing": "None"
                        }
                    ]
                }
            ]
        },
        {
            "type": "TextBlock",
            "text": "Your manager is: **{manager.name}**"
        },
        {
            "type": "TextBlock",
            "text": "Your peers are:"
        },
        {
            "type": "FactSet",
            "facts": [
                {
                    "$data": "{peers}",
                    "title": "{name}",
                    "value": "{title}"
                }
            ]
        }
    ]
}
```

그런 다음, 아래의 JSON 데이터를 **샘플 데이터 편집기**에 붙여넣습니다. 

**샘플 데이터**를 사용하면 실제 데이터를 전달할 때 런타임에 카드가 어떻게 표시되는지 정확하게 볼 수 있습니다.

**EmployeeData**

```json
{
    "name": "Matt",
    "photo": "https://pbs.twimg.com/profile_images/3647943215/d7f12830b3c17a5a9e4afcc370e3a37e_400x400.jpeg",
    "manager": {
        "name": "Thomas",
        "title": "PM Lead"
    },
    "peers": [
        {
            "name": "Lei",
            "title": "Sr Program Manager"
        },
        {
            "name": "Andrew",
            "title": "Program Manager II"
        },
        {
            "name": "Mary Anne",
            "title": "Program Manager"
        }
    ]
}
```

**미리 보기 모드** 단추를 클릭합니다. 위에서 제공한 샘플 데이터에 따라 카드가 렌더링되는 것을 볼 수 있습니다. 자유롭게 샘플 데이터를 조정하고 실시간으로 카드 업데이트를 확인하세요.

**축하합니다.** 첫 번째 적응형 카드 템플릿을 작성했습니다. 다음에는 템플릿을 실제 데이터로 채우는 방법을 알아보겠습니다.

> [템플릿 언어](language.md)에 대한 자세한 정보

## <a name="sdk-support"></a>SDK 지원

템플릿 SDK를 사용하여 템플릿을 실제 데이터로 채울 수 있습니다.

> [!NOTE]
>
> 초기 미리 보기 중에는 제한된 SDK 세트만 사용할 수 있습니다. 출시 후에는 지원되는 모든 적응형 카드 플랫폼에 대한 템플릿 라이브러리가 제공될 예정입니다.

플랫폼 | 설치 | 설명서
--- | --- | ---
JavaScript | `npm install adaptivecards-templating` | [설명서](https://www.npmjs.com/package/adaptivecards-templating)
.NET | *서비스 예정* | *서비스 예정*

### <a name="javascript-example"></a>JavaScript 예

아래 JavaScript는 템플릿을 데이터로 채우는 데 사용되는 일반적인 패턴을 보여줍니다.

```js
var template = new ACData.Template({ 
    // EmployeeCardTemplate goes here
});

var dataContext = new ACData.EvaluationContext();
dataContext.$root = {
    // Data goes here
};

var card = template.expand(dataContext);
// Now you have an AdaptiveCard ready to render!
```

> [템플릿 SDK](sdk.md)에 대한 자세한 정보

## <a name="template-service"></a>템플릿 서비스

적응형 카드 템플릿 서비스는 누구나 잘 알려진 템플릿 세트를 찾고, 기고하고, 공유할 수 있게 해주는 개념 증명 서비스입니다.

일부 데이터를 표시하되, 사용자 지정 적응형 카드를 작성하지 않으려는 경우에 유용합니다.

템플릿을 가져오는 API는 간단하게 사용할 수 있지만, 실제로 서비스는 데이터를 분석하고 사용자가 사용할 수 있는 템플릿을 찾는 기능을 포함하여 훨씬 더 많은 기능을 제공합니다.

`HTTP GET https://templates.adaptivecards.io/graph.microsoft.com/Profile.json`

모든 템플릿은 다른 오픈 소스 코드처럼 사용자가 참여할 수 있도록 GitHub 리포지토리에 저장된 일반 JSON 파일입니다.

> [카드 템플릿 서비스](service.md)에 대한 자세한 정보

## <a name="whats-next-and-sending-feedback"></a>다음 단계 및 피드백 보내기

템플릿과 데이터와 프레젠테이션 분리는 "일반적이고 일관된 방식으로 카드 콘텐츠를 교환하는 에코시스템"이라는 사명에 성큼 다가갈 수 있게 해줍니다.

최대한 빨리 더 많은 것을 공유하고 싶습니다. 그동안 [GitHub](https://github.com/microsoft/AdaptiveCards) 또는 Twitter **[@MattHidinger](https://twitter.com/matthidinger)** / **#AdaptiveCards**에 피드백을 보내 주세요. 
