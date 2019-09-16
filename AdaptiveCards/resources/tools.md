---
title: 적응형 카드 도구
author: matthidinger
ms.author: mahiding
ms.date: 03/14/2019
ms.topic: article
ms.openlocfilehash: ad520693224509deaf0ea1c2cd6a837089dbf2d5
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67137986"
---
# <a name="tools-and-samples"></a><span data-ttu-id="629b9-102">도구 및 샘플</span><span class="sxs-lookup"><span data-stu-id="629b9-102">Tools and Samples</span></span>

## <a name="card-designer"></a><span data-ttu-id="629b9-103">카드 디자이너</span><span class="sxs-lookup"><span data-stu-id="629b9-103">Card Designer</span></span> 

<span data-ttu-id="629b9-104">카드를 디자인하려면 도구가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="629b9-104">Need for a tool to design your cards?</span></span> <span data-ttu-id="629b9-105">[https://adaptivecards.io/designer](https://adaptivecards.io/designer)에서 브라우저 기반 적응형 카드 디자이너만 찾으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="629b9-105">Look no further than the browser-based adaptive card designer at [https://adaptivecards.io/designer](https://adaptivecards.io/designer)</span></span>

<span data-ttu-id="629b9-106">[![디자이너 스크린샷](media/tools/designer.jpg)](https://adaptivecards.io/designer)</span><span class="sxs-lookup"><span data-stu-id="629b9-106">[![designer screenshot](media/tools/designer.jpg)](https://adaptivecards.io/designer)</span></span>

### <a name="embed-the-designer-into-your-app"></a><span data-ttu-id="629b9-107">앱에 디자이너 포함</span><span class="sxs-lookup"><span data-stu-id="629b9-107">Embed the designer into your app</span></span>

<span data-ttu-id="629b9-108">그러나 JavaScript 라이브러리를 사용하여 **웹앱에 직접 카드 디자이너를 포함**할 수 있을 때 사용자를 해당 위치로 보내는 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="629b9-108">But why send your users there when you can **embed the card designer directly into your web** app using our JavaScript library.</span></span> 

<span data-ttu-id="629b9-109">시작하려면 [adaptivecards-designer](https://npmjs.com/adaptivecards-designer) 패키지를 체크 아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="629b9-109">Check out the [adaptivecards-designer](https://npmjs.com/adaptivecards-designer) package to get started.</span></span>

## <a name="schema-validation"></a><span data-ttu-id="629b9-110">스키마 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="629b9-110">Schema validation</span></span>

<span data-ttu-id="629b9-111">스키마 유효성 검사는 쉽게 작성하고 도구를 사용할 수 있는 강력한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="629b9-111">Schema validation is a powerful way of making authoring easier and enabling tooling.</span></span>

<span data-ttu-id="629b9-112">json에서 적응형 카드를 편집하고 유효성 검사하는 데 필요한 전체 [JSON 스키마 파일](http://adaptivecards.io/schemas/1.2.0/adaptive-card.json)을 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="629b9-112">We have provided a complete [JSON Schema file](http://adaptivecards.io/schemas/1.2.0/adaptive-card.json) for editing and validating adaptive cards in json.</span></span> <span data-ttu-id="629b9-113">스키마 URL의 버전이 지정되었으므로 최신 버전의 적응형 카드에 해당 URL이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="629b9-113">Note that the schema URL is versioned, newer versions of Adaptive Cards will have a corresponding URL.</span></span>

<span data-ttu-id="629b9-114">Visual Studio 및 Visual Studio Code에서 `$schema` 참조를 포함하여 자동 IntelliSense를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="629b9-114">In Visual Studio and Visual Studio Code you can get automatic Intellisense by including a `$schema` reference.</span></span>

![불량](media/tools/invalidjson1.png)

![자동 완성](media/tools/autocomplete.png)

## <a name="example"></a><span data-ttu-id="629b9-117">예</span><span class="sxs-lookup"><span data-stu-id="629b9-117">Example</span></span>

```json
{
    "$schema": "http://adaptivecards.io/schemas/1.2.0/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

## <a name="visual-studio-code-extension"></a><span data-ttu-id="629b9-118">Visual Studio Code 확장</span><span class="sxs-lookup"><span data-stu-id="629b9-118">Visual Studio Code Extension</span></span>

<span data-ttu-id="629b9-119">편집기 자체에서 실시간으로 편집 중인 카드를 시각화할 수 있는 Visual Studio Code 확장을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="629b9-119">We have created a Visual Studio code extension which allows you to visualize the card you are editing in real time inside the editor itself.</span></span> 

![확장](media/tools/vscode-extension.png)

<span data-ttu-id="629b9-121">설치하려면 확장 Marketplace를 열고 **적응형 카드 뷰어**를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="629b9-121">To install, open Extensions Marketplace and search for **Adaptive Card Viewer**.</span></span>

![marketplace](media/tools/vscode-extension-marketplace.png)

### <a name="usage"></a><span data-ttu-id="629b9-123">사용</span><span class="sxs-lookup"><span data-stu-id="629b9-123">Usage</span></span>

<span data-ttu-id="629b9-124">적응형 카드 `$schema` 속성으로 .json 파일을 편집하는 경우 `Ctrl+Shift+V A`를 사용하여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="629b9-124">When you are editing a .json file with an Adaptive Card `$schema` property you can view by using `Ctrl+Shift+V A`.</span></span>
```json
{
    "$schema": "http://adaptivecards.io/schemas/1.2.0/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

### <a name="options"></a><span data-ttu-id="629b9-125">옵션</span><span class="sxs-lookup"><span data-stu-id="629b9-125">Options</span></span>

<span data-ttu-id="629b9-126">다음 Visual Studio Code 설정은 AdaptiveCards 뷰어에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="629b9-126">The following Visual Studio Code setting is available for the AdaptiveCards Viewer.</span></span> <span data-ttu-id="629b9-127">이는 사용자 설정 또는 작업 영역 설정에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="629b9-127">This can be set in User Settings or Workspace Settings.</span></span>

```js
{
    // Open or not open the preview screen automatically
    "adaptivecardsviewer.enableautopreview": true,
}
```

## <a name="wpf-visualizer-sample"></a><span data-ttu-id="629b9-128">WPF 시각화 도우미 샘플</span><span class="sxs-lookup"><span data-stu-id="629b9-128">WPF Visualizer Sample</span></span>

<span data-ttu-id="629b9-129">[WPF 시각화 도우미 샘플 프로젝트](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer)를 사용하면 Windows 머신에서 WPF/Xaml을 사용하여 카드를 시각화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="629b9-129">The [WPF visualizer sample project](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) lets you visualize cards using WPF/Xaml on a Windows machine.</span></span>  <span data-ttu-id="629b9-130">호스트 구성 설정을 편집하고 볼 수 있도록 `hostconfig` 편집기가 기본 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="629b9-130">A `hostconfig` editor is built in for editing and viewing host config settings.</span></span> <span data-ttu-id="629b9-131">이 설정을 JSON으로 저장하여 애플리케이션의 렌더링에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="629b9-131">Save these settings as a JSON to use them in rendering in your application.</span></span>

![WPF 시각화 도우미](media/tools/wpfvisualizer.png)

## <a name="wpf-imagerender-sample"></a><span data-ttu-id="629b9-133">WPF ImageRender 샘플</span><span class="sxs-lookup"><span data-stu-id="629b9-133">WPF ImageRender Sample</span></span>

<span data-ttu-id="629b9-134">[ImageRender 샘플 프로젝트](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/AdaptiveCards.Sample.ImageRender)는 WPF를 사용하여 명령줄에서 카드를 PNG로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="629b9-134">The [ImageRender sample project](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/AdaptiveCards.Sample.ImageRender) turns any card into a PNG from the command line using WPF.</span></span> 
