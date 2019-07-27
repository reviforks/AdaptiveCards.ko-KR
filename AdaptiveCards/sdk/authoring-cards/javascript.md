---
title: 적응 카드용 JavaScript SDK
author: matthidinger
ms.author: mahiding
ms.date: 07/26/2019
ms.topic: article
ms.openlocfilehash: 039171d895fac0975bf9eff4fe84fdf8b6f7e4af
ms.sourcegitcommit: f8de9c02b92cd8927a18e59e5650c92b2b78db06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2019
ms.locfileid: "68523832"
---
# <a name="javascript-sdk-for-creating-cards"></a><span data-ttu-id="d02e0-102">카드를 만들기 위한 JavaScript SDK</span><span class="sxs-lookup"><span data-stu-id="d02e0-102">JavaScript SDK for creating cards</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d02e0-103">JSON을 serialize 하는 라이브러리는 아직 개발 중 이며 milage 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e0-103">The library for serializing JSON is still in development and your milage may vary.</span></span>

<span data-ttu-id="d02e0-104">[시작](../../authoring-cards/getting-started.md)에서 설명한 바와 같이 적응 카드는 카드 개체 모델의 직렬화 된 JSON 개체에 해당 하는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d02e0-104">As we described in the [Getting Started](../../authoring-cards/getting-started.md), an Adaptive Card is nothing more than a serialized JSON object of a card object model.</span></span>  <span data-ttu-id="d02e0-105">개체 모델을 쉽게 조작할 수 있도록 하기 위해 json을 쉽게 직렬화/역직렬화 할 수 있는 강력한 형식의 클래스 계층 구조를 정의 하는 몇 가지 라이브러리를 정의 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e0-105">To make it easy to manipulate the object model we have defined some libraries which define a strongly typed class hierarchy that is easy to serialize/deserialize json.</span></span>

<span data-ttu-id="d02e0-106">적응 카드 json을 만들려는 모든 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e0-106">You can use any tooling that you want to create the adaptive card json.</span></span>

<span data-ttu-id="d02e0-107">Npm `adaptivecards` 패키지는 javascript에서 적응 카드로 작업 하기 위한 라이브러리를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e0-107">The `adaptivecards` npm package defines a library for working with adaptive cards in javascript</span></span>

## <a name="to-install"></a><span data-ttu-id="d02e0-108">설치 하려면</span><span class="sxs-lookup"><span data-stu-id="d02e0-108">To install</span></span>
```console
npm install adaptivecards
```

## <a name="example"></a><span data-ttu-id="d02e0-109">예제</span><span class="sxs-lookup"><span data-stu-id="d02e0-109">Example</span></span>

<span data-ttu-id="d02e0-110">다음 API는 개체 모델을 사용 하 여 적응 카드를 생성 하 고이를 JSON으로 serialize 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d02e0-110">The following API shows how to construct an Adaptive Card using the object model and serialize it to JSON.</span></span>

```typescript
let card = new Adaptive.AdaptiveCard();
card.version = new Adaptive.Version(1, 0);

let textBlock = new Adaptive.TextBlock();
textBlock.text = "Hello World";

card.addItem(textBlock);

let json = card.toJSON();
```
