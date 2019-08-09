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
# <a name="adaptive-cards-template-service"></a><span data-ttu-id="f14ad-102">적응 카드 템플릿 서비스</span><span class="sxs-lookup"><span data-stu-id="f14ad-102">Adaptive Cards Template Service</span></span>

<span data-ttu-id="f14ad-103">적응 카드 템플릿 서비스는 누구나 잘 알려진 템플릿 집합을 찾고, 참여 하 고, 공유할 수 있도록 하는 개념 증명 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-103">The Adaptive Cards Template Service is a proof-of-concept service that allows anyone to find, contribute to, and share a set of well-known templates.</span></span>

<span data-ttu-id="f14ad-104">일부 데이터를 표시 하지만 사용자 지정 적응 카드를 작성 하지 않으려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-104">It's useful if you want to display some data but don't want to bother writing a custom adaptive card for it.</span></span>

> <span data-ttu-id="f14ad-105">[적응 카드 템플릿 개요](index.md) 는이 내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f14ad-105">Please read this for an [overview of Adaptive Card Templating](index.md)</span></span>

> [!IMPORTANT] 
> 
> <span data-ttu-id="f14ad-106">*사용 약관 및 규약*</span><span class="sxs-lookup"><span data-stu-id="f14ad-106">*Terms and agreement*</span></span> 
> 
> <span data-ttu-id="f14ad-107">이 **알파** 서비스는 모든 오류를 포함 하 여 "있는 그대로" 제공 되며 어떤 방식으로든 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-107">This **alpha-level** service is provided "as-is", with all faults and is not supported in any way.</span></span> <span data-ttu-id="f14ad-108">서비스의 모든 데이터 컬렉션은 [Microsoft 개인 정보 취급 방침](https://go.microsoft.com/fwlink/?LinkID=824704)을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-108">Any data collection from the service is subject to the [Microsoft privacy statement](https://go.microsoft.com/fwlink/?LinkID=824704).</span></span>
> 
> <span data-ttu-id="f14ad-109">이러한 기능은 **미리 보기 상태 이며 변경 될 수**있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-109">These features are **in preview and subject to change**.</span></span> <span data-ttu-id="f14ad-110">사용자 의견은 환영 뿐만 아니라 필요한 기능을 제공 하기 위해 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-110">Your feedback is not only welcome, but  critical to ensure we deliver the features **you** need.</span></span>

## <a name="how-does-the-service-help-me"></a><span data-ttu-id="f14ad-111">서비스는 어떻게 도움이 되나요?</span><span class="sxs-lookup"><span data-stu-id="f14ad-111">How does the service help me?</span></span>

<span data-ttu-id="f14ad-112">데이터의 조각이 있다면 조직 내에서의 재무 데이터, Microsoft Graph 데이터, 데이터, 데이터 또는 사용자 지정 데이터 일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-112">Let's say I just got a piece of data, maybe it's financial data, Microsoft Graph data, schema.org data, or custom data from within my organization.</span></span> 

<span data-ttu-id="f14ad-113">이제 사용자에 게 데이터를 표시 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-113">Now I want to display the data to a user.</span></span> 

<span data-ttu-id="f14ad-114">일반적으로 최종 사용자에 게 제공 하는 모든 프런트 엔드 스택에서 사용자 지정 UI 코드를 작성 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-114">Traditionally that means writing custom UI code in all of the front-end stacks that I deliver to end-users.</span></span>

<span data-ttu-id="f14ad-115">그러나 앱에서 데이터 형식에 따라 새 UI 템플릿을 "학습" 할 수 있는 전 세계의 경우는 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="f14ad-115">But what if there were a world where my app could "learn" new UI templates based on the type of data?</span></span> <span data-ttu-id="f14ad-116">누구나 자신의 프로젝트, 조직 내 또는 전체 인터넷에서 공용 UI 템플릿을 기고, 향상 및 공유할 수 있는 세계입니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-116">A world where anyone could contribute, enhance, and share common UI templates, within their own projects, within an organization, or for the entire internet.</span></span>

## <a name="what-is-the-card-template-service"></a><span data-ttu-id="f14ad-117">카드 템플릿 서비스는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="f14ad-117">What is the card template service?</span></span>

<span data-ttu-id="f14ad-118">카드 템플릿 서비스는 다음을 돕는 간단한 REST 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-118">The card template service is a simple REST endpoint that helps:</span></span>

* <span data-ttu-id="f14ad-119">데이터 구조를 분석 하 여 템플릿 **찾기**</span><span class="sxs-lookup"><span data-stu-id="f14ad-119">**Find** a template by analyzing the structure of your data</span></span>
* <span data-ttu-id="f14ad-120">*데이터를 서버로 전송 하거나 장치를 떠나지 않고* 클라이언트에 직접 바인딩할 수 있도록 템플릿을 **가져옵니다** .</span><span class="sxs-lookup"><span data-stu-id="f14ad-120">**Get** a template so you can bind it directly on the client, *without sending your data to the server or ever leaving the device*</span></span>
* <span data-ttu-id="f14ad-121">클라이언트 쪽 데이터 바인딩이 적절 하지 않거나 가능 하지 않은 경우 서버에서 템플릿 **채우기**</span><span class="sxs-lookup"><span data-stu-id="f14ad-121">**Populate** a template on the server, when client-side data binding isn't appropriate or possible</span></span>

<span data-ttu-id="f14ad-122">모두 뒤에는 다음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-122">Behind it all, is:</span></span>

* <span data-ttu-id="f14ad-123">GitHub에서 지원 되는 공유 오픈 소스 템플릿 리포지토리입니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-123">A shared, open-source template repository backed by GitHub.</span></span> <span data-ttu-id="f14ad-124">*(리포지토리는 현재 비공개 이지만 일부 느슨한 끝을 연결 하는 즉시 공용으로 설정 됩니다.)*</span><span class="sxs-lookup"><span data-stu-id="f14ad-124">*(The repo is currently private but will be made public as soon as we tie up some loose ends)*</span></span>
* <span data-ttu-id="f14ad-125">모든 템플릿은 리포지토리의 플랫 JSON 파일로, 개발자 워크플로의 자연 부분을 편집, 참여 및 공유 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-125">All the templates are flat JSON files in the repo, which makes editing, contributing, and sharing a natural part of a developer workflow.</span></span>
* <span data-ttu-id="f14ad-126">서비스에 대 한 코드를 사용할 수 있으므로 사용자에 게 가장 적합 한 모든 위치를 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-126">The code for the service will be made available so you can host wherever makes the most sense to you.</span></span> 

## <a name="using-the-service"></a><span data-ttu-id="f14ad-127">서비스 사용</span><span class="sxs-lookup"><span data-stu-id="f14ad-127">Using the service</span></span>

### <a name="get-all-templates"></a><span data-ttu-id="f14ad-128">모든 템플릿 가져오기</span><span class="sxs-lookup"><span data-stu-id="f14ad-128">Get all templates</span></span> 

<span data-ttu-id="f14ad-129">이 끝점은 알려진 모든 템플릿 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-129">This endpoint returns a list of all known templates.</span></span>

> `HTTP GET https://templates.adaptivecards.io/list`

<span data-ttu-id="f14ad-130">**응답 발췌**</span><span class="sxs-lookup"><span data-stu-id="f14ad-130">**Response excerpt**</span></span>

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

### <a name="find-a-template"></a><span data-ttu-id="f14ad-131">템플릿 찾기</span><span class="sxs-lookup"><span data-stu-id="f14ad-131">Find a template</span></span>

<span data-ttu-id="f14ad-132">이 끝점은 데이터 구조를 분석 하 여 템플릿을 찾으려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-132">This endpoint tries to find a template by analyzing the structure of your data.</span></span>

> `HTTP POST https://templates.adaptivecards.io/find`

#### <a name="example"></a><span data-ttu-id="f14ad-133">예제</span><span class="sxs-lookup"><span data-stu-id="f14ad-133">Example</span></span>

<span data-ttu-id="f14ad-134">[Microsoft Graph](https://graph.microsoft.com) 끝점을 적중 하 여에 대 한 조직 데이터를 가져오는 것을 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-134">Let's say I just hit a [Microsoft Graph](https://graph.microsoft.com) endpoint to get organizational data about me.</span></span>

> `HTTP GET https://graph.microsoft.com/v1.0/me/`

![그래프 탐색기 스크린샷](content/2019-08-01-12-08-13.png)

<span data-ttu-id="f14ad-136">해당 API는 **JSON 데이터**를 반환 했지만, 적응 카드를 사용 하 여 사용자에 게 **표시** 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="f14ad-136">That API returned **JSON data**, but how do I **display it** to users using Adaptive Cards?</span></span> 

<span data-ttu-id="f14ad-137">먼저이 형식의 데이터에 대 한 템플릿이 있는지 확인 한 후 `/find` `POST body`에 내 데이터를 사용 하 여 끝점에 대 한 HTTP 요청을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-137">First I want to see if a template exists for this type of data, so I make an HTTP request to the `/find` endpoint with my data in the `POST body`.</span></span>

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

<span data-ttu-id="f14ad-138">**응답이**</span><span class="sxs-lookup"><span data-stu-id="f14ad-138">**Response:**</span></span>

```json
[
  {
    "templateUrl": "graph.microsoft.com/Profile.json",
    "confidence": 1
  }
]
```

<span data-ttu-id="f14ad-139">서비스는 일치 하는 템플릿 목록을 반환 하며, `confidence` 일치 하는 항목을 닫는 방법을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-139">The service returns a list of any matching templates, along with a `confidence` indicating how close the match is.</span></span> <span data-ttu-id="f14ad-140">이제 해당 템플릿 URL을 사용 하 여 템플릿을 **가져오거나** 서버 쪽으로 **채울** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-140">Now I can use that template URL to **get** the template, or **populate** it server-side.</span></span>

### <a name="get-a-template"></a><span data-ttu-id="f14ad-141">템플릿 가져오기</span><span class="sxs-lookup"><span data-stu-id="f14ad-141">Get a template</span></span>

<span data-ttu-id="f14ad-142">이 끝점에서 검색 된 템플릿은 [Templatng sdk를 사용 하 여](sdk.md)런타임 시 데이터로 채워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-142">A template retrieved from this endpoint can be populated with data at runtime [using the templatng SDKs](sdk.md).</span></span>

> `HTTP GET https://templates.adaptivecards.io/[TEMPLATE-PATH]`

<span data-ttu-id="f14ad-143">템플릿에 "샘플 데이터"를 포함할 수도 있습니다. 그러면 디자이너에서 다음과 같이 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-143">You can also include "sample data" with the template, which makes editing in the designer more friendly:</span></span>

> `HTTP GET https://templates.adaptivecards.io/[TEMPLATE-PATH]?sampleData=true`

#### <a name="example"></a><span data-ttu-id="f14ad-144">예제</span><span class="sxs-lookup"><span data-stu-id="f14ad-144">Example</span></span>

<span data-ttu-id="f14ad-145">`/find` 위에서 반환 된 Microsoft Graph 프로필 템플릿을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-145">Let's get the Microsoft Graph profile template that was returned from `/find` above.</span></span>

`HTTP GET https://templates.adaptivecards.io/graph.microsoft.com/Profile.json`

<span data-ttu-id="f14ad-146">**응답 발췌**</span><span class="sxs-lookup"><span data-stu-id="f14ad-146">**Response excerpt**</span></span>

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

<span data-ttu-id="f14ad-147">이제이 템플릿을 템플릿 [sdk](sdk.md) 와 함께 사용 하 여 미리 렌더링 된 적응 카드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-147">Now use this template with the [templating SDKs](sdk.md) to create a ready-to-render Adaptive Card.</span></span>

### <a name="populate-a-template-server-side"></a><span data-ttu-id="f14ad-148">템플릿 서버 쪽 채우기</span><span class="sxs-lookup"><span data-stu-id="f14ad-148">Populate a template server-side</span></span>

<span data-ttu-id="f14ad-149">일부 경우에는 클라이언트에서 템플릿을 채우는 것이 적합 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-149">In some cases it may not make sense to populate a template on the client.</span></span>  <span data-ttu-id="f14ad-150">이러한 사용 사례에 대해, 모든 적응 카드 렌더러에 전달할 준비가 된 완전 한 적응 카드를 서비스에서 반환 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-150">For these use cases, you can have the service return a fully-populated Adaptive Card, ready to be passed to any Adaptive Card Renderer.</span></span>

> `HTTP POST https://templates.adaptivecards.io/[TEMPLATE-PATH]`

#### <a name="example"></a><span data-ttu-id="f14ad-151">예제</span><span class="sxs-lookup"><span data-stu-id="f14ad-151">Example</span></span>

<span data-ttu-id="f14ad-152">위의 데이터를 `/find` 사용 하 여 반환 된 Microsoft Graph 프로필 템플릿을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-152">Let's populate the Microsoft Graph profile template that was returned from `/find` using the data above.</span></span>

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

<span data-ttu-id="f14ad-153">**응답 발췌**</span><span class="sxs-lookup"><span data-stu-id="f14ad-153">**Response excerpt**</span></span>

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

<span data-ttu-id="f14ad-154">응답이 `TextBlock` 요청에서`GET` 와 같이 첫 번째 `"Megan Bowen"` 의 텍스트를 대신 `"{name}"`로 대체 한 것을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-154">Notice how the response replaced the text of the first `TextBlock` with `"Megan Bowen"` instead of `"{name}"`, as in the `GET` request.</span></span> <span data-ttu-id="f14ad-155">이제이 AdaptiveCard는 클라이언트 쪽 템플릿을 거치지 않고도 적응 카드 렌더러에 전달 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-155">This AdaptiveCard can now be passed to any Adaptive Card renderer without going through client-side templating.</span></span>

## <a name="contributing-templates"></a><span data-ttu-id="f14ad-156">참여 템플릿</span><span class="sxs-lookup"><span data-stu-id="f14ad-156">Contributing templates</span></span>

<span data-ttu-id="f14ad-157">템플릿 서비스는 GitHub 리포지토리 (현재 **비공개**)에 의해 지원 되지만 일부 느슨한 종료를 연결 하면 소스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-157">The template service is backed by a GitHub repo (which is currently **private**), but we will open source once we tie up some loose ends.</span></span>

<span data-ttu-id="f14ad-158">템플릿에 대 한 백업 저장소로 GitHub를 사용 하는 것이 좋습니다. 템플릿을 작성 하 고, 개선 하 고, 공유 하는 프로세스를 "democratize" 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-158">Our hope is that by using GitHub as a backing store for the templates, we can "democratize" the process of authoring, enhancing, and sharing templates.</span></span> <span data-ttu-id="f14ad-159">누구나 완전히 새로운 템플릿을 포함 하는 끌어오기 요청을 제출 하거나 기존 항목에 대 한 향상 된 기능을 만들 수 있습니다. GitHub의 개발자에 게 친숙 한 환경 내 모두.</span><span class="sxs-lookup"><span data-stu-id="f14ad-159">Anyone can submit a Pull Request that includes an entirely new template, or make enhancements to existing ones... all within the developer-friendly experience of GitHub.</span></span>

## <a name="self-hosting-the-service"></a><span data-ttu-id="f14ad-160">서비스 자체 호스팅</span><span class="sxs-lookup"><span data-stu-id="f14ad-160">Self-hosting the service</span></span>

<span data-ttu-id="f14ad-161">에서 `https://templates.adaptivecards.io`호스트 되는 "중앙" 적응 카드 템플릿 서비스에는 일부 데이터 형식이 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-161">Not all types of data are appropriate for the "central" Adaptive Cards template service hosted at `https://templates.adaptivecards.io`.</span></span> 

<span data-ttu-id="f14ad-162">사용자가 조직 내에서 템플릿 서비스를 호스팅할 수 있는지 확인 하 고, 소스 코드를 사용할 수 있도록 하 고, Azure 또는 자신의 백 엔드에 쉽게 배포할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-162">We want to make sure anyone can host the template service within your organization, so the source code will be made available and we'll make it very simple to deploy to Azure or your own back-end.</span></span>

<span data-ttu-id="f14ad-163">이에 대 한 자세한 내용은 뒷부분에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14ad-163">More on this at a later date.</span></span>