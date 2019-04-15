---
title: Adaptive Card 도구
author: matthidinger
ms.author: mahiding
ms.date: 03/14/2019
ms.topic: article
ms.openlocfilehash: 35ce89653a6cf2a313518be0f221a166e1eb7711
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552505"
---
# <a name="card-designer"></a><span data-ttu-id="74d86-102">카드 디자이너</span><span class="sxs-lookup"><span data-stu-id="74d86-102">Card Designer</span></span> 

<span data-ttu-id="74d86-103">카드를 디자인 하는 도구에 대 한 필요 합니까?</span><span class="sxs-lookup"><span data-stu-id="74d86-103">Need for a tool to design your cards?</span></span> <span data-ttu-id="74d86-104">브라우저 기반 적응 카드에 디자이너에 더 [https://adaptivecards.io/designer](https://adaptivecards.io/designer)</span><span class="sxs-lookup"><span data-stu-id="74d86-104">Look no further than the browser-based adaptive card designer at [https://adaptivecards.io/designer](https://adaptivecards.io/designer)</span></span>

<span data-ttu-id="74d86-105">[![디자이너의 스크린 샷](media/tools/designer.jpg)](https://adaptivecards.io/designer)</span><span class="sxs-lookup"><span data-stu-id="74d86-105">[![designer screenshot](media/tools/designer.jpg)](https://adaptivecards.io/designer)</span></span>

## <a name="embed-the-designer-into-your-app"></a><span data-ttu-id="74d86-106">앱에 디자이너를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="74d86-106">Embed the designer into your app</span></span>

<span data-ttu-id="74d86-107">그러나 가능한 경우 사용자가 있는 송신 하는 이유 **카드 디자이너 웹에 직접 포함** JavaScript 라이브러리를 사용 하 여 앱.</span><span class="sxs-lookup"><span data-stu-id="74d86-107">But why send your users there when you can **embed the card designer directly into your web** app using our JavaScript library.</span></span> 

<span data-ttu-id="74d86-108">체크 아웃 합니다 [adaptivecards 디자이너](https://npmjs.com/adaptivecards-designer) 패키지를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="74d86-108">Check out the [adaptivecards-designer](https://npmjs.com/adaptivecards-designer) package to get started.</span></span>

# <a name="schema-validation"></a><span data-ttu-id="74d86-109">스키마 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="74d86-109">Schema validation</span></span>

<span data-ttu-id="74d86-110">스키마 유효성 검사는 쉽게 작성 하 고 도구를 사용 하도록 설정 하도록 하는 강력한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="74d86-110">Schema validation is a powerful way of making authoring easier and enabling tooling.</span></span>

## <a name="json-schema"></a><span data-ttu-id="74d86-111">JSON 스키마</span><span class="sxs-lookup"><span data-stu-id="74d86-111">JSON Schema</span></span>
<span data-ttu-id="74d86-112">전체 제공 했습니다 [JSON 스키마 파일](http://adaptivecards.io/schemas/adaptive-card.json) 편집 하 고 json에서 adaptive card의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="74d86-112">We have provided a complete [JSON Schema file](http://adaptivecards.io/schemas/adaptive-card.json) for editing and validating adaptive cards in json.</span></span>

<span data-ttu-id="74d86-113">Visual Studio 및 Visual Studio Code에서 포함 하 여 자동 Intellisense를 가져올 수 있습니다는 `$schema` 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="74d86-113">In Visual Studio and Visual Studio Code you can get automatic Intellisense by including a `$schema` reference.</span></span>

![잘못 된](media/tools/invalidjson1.png)

![자동 완성](media/tools/autocomplete.png)

### <a name="example"></a><span data-ttu-id="74d86-116">예제</span><span class="sxs-lookup"><span data-stu-id="74d86-116">Example</span></span>

```json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "0.5",
    "body": []
}
```

# <a name="tools-and-samples"></a><span data-ttu-id="74d86-117">도구 및 샘플</span><span class="sxs-lookup"><span data-stu-id="74d86-117">Tools and samples</span></span>
<span data-ttu-id="74d86-118">일부 도구 및 샘플 소스 트리에 유용한 도구 뿐만 아니라 유용한 참조에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74d86-118">There are some tools and samples in the source tree which are useful references as well as useful tools.</span></span>

## <a name="visual-studio-code-extension"></a><span data-ttu-id="74d86-119">Visual Studio Code 확장</span><span class="sxs-lookup"><span data-stu-id="74d86-119">Visual Studio Code Extension</span></span>
<span data-ttu-id="74d86-120">자체 편집기 내부에서 실시간으로 편집 하는 카드를 시각화할 수 있는 Visual Studio 코드 확장을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="74d86-120">We have created a Visual Studio code extension which allows you to visualize the card you are editing in real time inside the editor itself.</span></span> 

![확장](media/tools/vscode-extension.png)

<span data-ttu-id="74d86-122">를 설치 하려면 확장 Marketplace 열고 검색할 **적응 카드 뷰어**합니다.</span><span class="sxs-lookup"><span data-stu-id="74d86-122">To install, open Extensions Marketplace and search for **Adaptive Card Viewer**.</span></span>

![marketplace](media/tools/vscode-extension-marketplace.png)

### <a name="usage"></a><span data-ttu-id="74d86-124">사용법</span><span class="sxs-lookup"><span data-stu-id="74d86-124">Usage</span></span>

<span data-ttu-id="74d86-125">Adaptive Card를 사용 하 여.json 파일을 편집할 때 `$schema` 속성을 사용 하 여 볼 수 있습니다 `Ctrl+Shift+V A`합니다.</span><span class="sxs-lookup"><span data-stu-id="74d86-125">When you are editing a .json file with an Adaptive Card `$schema` property you can view by using `Ctrl+Shift+V A`.</span></span>
```json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

### <a name="options"></a><span data-ttu-id="74d86-126">변수</span><span class="sxs-lookup"><span data-stu-id="74d86-126">Options</span></span>

<span data-ttu-id="74d86-127">다음 Visual Studio Code 설정은입니다 AdaptiveCards 뷰어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74d86-127">The following Visual Studio Code setting is available for the AdaptiveCards Viewer.</span></span> <span data-ttu-id="74d86-128">사용자 설정 또는 작업 영역 설정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74d86-128">This can be set in User Settings or Workspace Settings.</span></span>

```js
{
    // Open or not open the preview screen automatically
    "adaptivecardsviewer.enableautopreview": true,
}
```

## <a name="wpf-visualizer-sample"></a><span data-ttu-id="74d86-129">WPF 시각화 도우미 샘플</span><span class="sxs-lookup"><span data-stu-id="74d86-129">WPF Visualizer Sample</span></span>
<span data-ttu-id="74d86-130">합니다 [WPF 시각화 도우미 샘플 프로젝트](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) 사용 WPF/Xaml을 사용 하 여 Windows 컴퓨터에서 카드를 시각화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74d86-130">The [WPF visualizer sample project](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) lets you visualize cards using WPF/Xaml on a Windows machine.</span></span>  <span data-ttu-id="74d86-131">`hostconfig` 호스트 구성 설정 보기 및 편집에 대 한 편집기 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="74d86-131">A `hostconfig` editor is built in for editing and viewing host config settings.</span></span> <span data-ttu-id="74d86-132">응용 프로그램에서 렌더링에서 사용 하는 JSON으로 이러한 설정을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="74d86-132">Save these settings as a JSON to use them in rendering in your application.</span></span>

![wpf 시각화 도우미](media/tools/wpfvisualizer.png)

## <a name="wpf-imagerender-sample"></a><span data-ttu-id="74d86-134">WPF ImageRender 샘플</span><span class="sxs-lookup"><span data-stu-id="74d86-134">WPF ImageRender Sample</span></span>
<span data-ttu-id="74d86-135">합니다 [ImageRender 샘플 프로젝트](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/AdaptiveCards.Sample.ImageRender) WPF를 사용 하 여 명령줄에서 PNG 모든 카드가 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="74d86-135">The [ImageRender sample project](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/AdaptiveCards.Sample.ImageRender) turns any card into a PNG from the command line using WPF.</span></span> 
