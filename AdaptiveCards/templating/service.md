---
title: 적응 카드 템플릿 서비스
author: matthidinger
ms.author: mahiding
ms.date: 08/01/2019
ms.topic: article
ms.openlocfilehash: 81d1e598b6157b6ba1fedbf458a7c624705afcd5
ms.sourcegitcommit: a16f53ba10a8607deacde5c8cc78927cac58657c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68878890"
---
# <a name="adaptive-cards-template-service"></a>적응 카드 템플릿 서비스

적응 카드 템플릿 서비스는 누구나 잘 알려진 템플릿 집합을 찾고, 참여 하 고, 공유할 수 있도록 하는 개념 증명 서비스입니다.

일부 데이터를 표시 하지만 사용자 지정 적응 카드를 작성 하지 않으려는 경우에 유용 합니다.

> [적응 카드 템플릿 개요](index.md) 는이 내용을 참조 하세요.

> [!IMPORTANT] 
> 
> *사용 약관 및 규약* 
> 
> 이 **알파** 서비스는 모든 오류를 포함 하 여 "있는 그대로" 제공 되며 어떤 방식으로든 지원 되지 않습니다. 서비스의 모든 데이터 컬렉션은 [Microsoft 개인 정보 취급 방침](https://go.microsoft.com/fwlink/?LinkID=824704)을 따릅니다.
> 
> 이러한 기능은 **미리 보기 상태 이며 변경 될 수**있습니다. 사용자 의견은 환영 뿐만 아니라 필요한 기능을 제공 하기 위해 중요 합니다.

## <a name="how-does-the-service-help-me"></a>서비스는 어떻게 도움이 되나요?

데이터의 조각이 있다면 조직 내에서의 재무 데이터, Microsoft Graph 데이터, 데이터, 데이터 또는 사용자 지정 데이터 일 수도 있습니다. 

이제 사용자에 게 데이터를 표시 하려고 합니다. 

일반적으로 최종 사용자에 게 제공 하는 모든 프런트 엔드 스택에서 사용자 지정 UI 코드를 작성 하는 것을 의미 합니다.

그러나 앱에서 데이터 형식에 따라 새 UI 템플릿을 "학습" 할 수 있는 전 세계의 경우는 어떻게 되나요? 누구나 자신의 프로젝트, 조직 내 또는 전체 인터넷에서 공용 UI 템플릿을 기고, 향상 및 공유할 수 있는 세계입니다.

## <a name="what-is-the-card-template-service"></a>카드 템플릿 서비스는 무엇 인가요?

카드 템플릿 서비스는 다음을 돕는 간단한 REST 끝점입니다.

* 데이터 구조를 분석 하 여 템플릿 **찾기**
* *데이터를 서버로 전송 하거나 장치를 떠나지 않고* 클라이언트에 직접 바인딩할 수 있도록 템플릿을 **가져옵니다** .
* 클라이언트 쪽 데이터 바인딩이 적절 하지 않거나 가능 하지 않은 경우 서버에서 템플릿 **채우기**

모두 뒤에는 다음이 있습니다.

* GitHub에서 지원 되는 공유 오픈 소스 템플릿 리포지토리입니다. *(리포지토리는 현재 비공개 이지만 일부 느슨한 끝을 연결 하는 즉시 공용으로 설정 됩니다.)*
* 모든 템플릿은 리포지토리의 플랫 JSON 파일로, 개발자 워크플로의 자연 부분을 편집, 참여 및 공유 하는 데 사용 됩니다.
* 서비스에 대 한 코드를 사용할 수 있으므로 사용자에 게 가장 적합 한 모든 위치를 호스트할 수 있습니다. 

## <a name="using-the-service"></a>서비스 사용

### <a name="get-all-templates"></a>모든 템플릿 가져오기 

이 끝점은 알려진 모든 템플릿 목록을 반환 합니다.

> `HTTP GET https://templates.adaptivecards.io/list`

**응답 발췌**

```json
{
  "graph.microsoft.com": {
    "templates": [
      {
        "file": "Files.json",
        "fullPath": "graph.microsoft.com/Files.json"
      },
      {
        "file": "Profile.json",
        "fullPath": "graph.microsoft.com/Profile.json"
      }
   ]
}
```

### <a name="find-a-template"></a>템플릿 찾기

이 끝점은 데이터 구조를 분석 하 여 템플릿을 찾으려고 시도 합니다.

> `HTTP POST https://templates.adaptivecards.io/find`

#### <a name="example"></a>예제

[Microsoft Graph](https://graph.microsoft.com) 끝점을 적중 하 여에 대 한 조직 데이터를 가져오는 것을 가정해 보겠습니다.

> `HTTP GET https://graph.microsoft.com/v1.0/me/`

![그래프 탐색기 스크린샷](content/2019-08-01-12-08-13.png)

해당 API는 **JSON 데이터**를 반환 했지만, 적응 카드를 사용 하 여 사용자에 게 **표시** 하려면 어떻게 해야 하나요? 

먼저이 형식의 데이터에 대 한 템플릿이 있는지 확인 한 후 `/find` `POST body`에 내 데이터를 사용 하 여 끝점에 대 한 HTTP 요청을 수행 합니다.

```
HTTP POST https://templates.adaptivecards.io/find

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users/$entity",
    "businessPhones": [
        "+1 412 555 0109"
    ],
    "displayName": "Megan Bowen",
    "givenName": "Megan",
    "jobTitle": "Auditor",
    "mail": "MeganB@M365x214355.onmicrosoft.com",
    "mobilePhone": null,
    "officeLocation": "12/1110",
    "preferredLanguage": "en-US",
    "surname": "Bowen",
    "userPrincipalName": "MeganB@M365x214355.onmicrosoft.com",
    "id": "48d31887-5fad-4d73-a9f5-3c356e68a038"
}
```

**응답이**

```json
[
  {
    "templateUrl": "graph.microsoft.com/Profile.json",
    "confidence": 1
  }
]
```

서비스는 일치 하는 템플릿 목록을 반환 하며, `confidence` 일치 하는 항목을 닫는 방법을 나타냅니다. 이제 해당 템플릿 URL을 사용 하 여 템플릿을 **가져오거나** 서버 쪽으로 **채울** 수 있습니다.

### <a name="get-a-template"></a>템플릿 가져오기

이 끝점에서 검색 된 템플릿은 [Templatng sdk를 사용 하 여](sdk.md)런타임 시 데이터로 채워질 수 있습니다.

> `HTTP GET https://templates.adaptivecards.io/[TEMPLATE-PATH]`

템플릿에 "샘플 데이터"를 포함할 수도 있습니다. 그러면 디자이너에서 다음과 같이 편집할 수 있습니다.

> `HTTP GET https://templates.adaptivecards.io/[TEMPLATE-PATH]?sampleData=true`

#### <a name="example"></a>예제

`/find` 위에서 반환 된 Microsoft Graph 프로필 템플릿을 살펴보겠습니다.

`HTTP GET https://templates.adaptivecards.io/graph.microsoft.com/Profile.json`

**응답 발췌**

```json
{
  "type": "AdaptiveCard",
  "version": "1.0",
  "body": [
    {
      "type": "TextBlock",
      "size": "Medium",
      "weight": "Bolder",
      "text": "{name}"
    },
    {
        // ...snip
    }
  ]
}
```

이제이 템플릿을 템플릿 [sdk](sdk.md) 와 함께 사용 하 여 미리 렌더링 된 적응 카드를 만듭니다.

### <a name="populate-a-template-server-side"></a>템플릿 서버 쪽 채우기

일부 경우에는 클라이언트에서 템플릿을 채우는 것이 적합 하지 않을 수 있습니다.  이러한 사용 사례에 대해, 모든 적응 카드 렌더러에 전달할 준비가 된 완전 한 적응 카드를 서비스에서 반환 하도록 설정할 수 있습니다.

> `HTTP POST https://templates.adaptivecards.io/[TEMPLATE-PATH]`

#### <a name="example"></a>예제

위의 데이터를 `/find` 사용 하 여 반환 된 Microsoft Graph 프로필 템플릿을 채웁니다.

```
HTTP POST https://templates.adaptivecards.io/graph.microsoft.com/Profile.json

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users/$entity",
    "businessPhones": [
        "+1 412 555 0109"
    ],
    "displayName": "Megan Bowen",
    "givenName": "Megan",
    "jobTitle": "Auditor",
    "mail": "MeganB@M365x214355.onmicrosoft.com",
    "mobilePhone": null,
    "officeLocation": "12/1110",
    "preferredLanguage": "en-US",
    "surname": "Bowen",
    "userPrincipalName": "MeganB@M365x214355.onmicrosoft.com",
    "id": "48d31887-5fad-4d73-a9f5-3c356e68a038"
}
```

**응답 발췌**

```json
{
  "type": "AdaptiveCard",
  "version": "1.0",
  "body": [
    {
      "type": "TextBlock",
      "size": "Medium",
      "weight": "Bolder",
      "text": "Megan Bowen"
    },
    {
        // ...snip
    }
  ]
}
```

응답이 `TextBlock` 요청에서`GET` 와 같이 첫 번째 `"Megan Bowen"` 의 텍스트를 대신 `"{name}"`로 대체 한 것을 확인 합니다. 이제이 AdaptiveCard는 클라이언트 쪽 템플릿을 거치지 않고도 적응 카드 렌더러에 전달 될 수 있습니다.

## <a name="contributing-templates"></a>참여 템플릿

템플릿 서비스는 GitHub 리포지토리 (현재 **비공개**)에 의해 지원 되지만 일부 느슨한 종료를 연결 하면 소스를 엽니다.

템플릿에 대 한 백업 저장소로 GitHub를 사용 하는 것이 좋습니다. 템플릿을 작성 하 고, 개선 하 고, 공유 하는 프로세스를 "democratize" 할 수 있습니다. 누구나 완전히 새로운 템플릿을 포함 하는 끌어오기 요청을 제출 하거나 기존 항목에 대 한 향상 된 기능을 만들 수 있습니다. GitHub의 개발자에 게 친숙 한 환경 내 모두.

## <a name="self-hosting-the-service"></a>서비스 자체 호스팅

에서 `https://templates.adaptivecards.io`호스트 되는 "중앙" 적응 카드 템플릿 서비스에는 일부 데이터 형식이 적합 하지 않습니다. 

사용자가 조직 내에서 템플릿 서비스를 호스팅할 수 있는지 확인 하 고, 소스 코드를 사용할 수 있도록 하 고, Azure 또는 자신의 백 엔드에 쉽게 배포할 수 있도록 합니다.

이에 대 한 자세한 내용은 뒷부분에 있습니다.