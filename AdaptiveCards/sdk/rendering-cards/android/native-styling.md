---
title: 기본 스타일링 - Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: d0c6b56e0497b78aa149f73dc1d32537689c0386
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145483"
---
# <a name="native-styling---android"></a><span data-ttu-id="7533f-102">기본 스타일링 - Android</span><span class="sxs-lookup"><span data-stu-id="7533f-102">Native styling - Android</span></span>

<span data-ttu-id="7533f-103">Android 렌더러는 기본 스타일링을 지원하지 않지만, v1.2에서는 일부 속성의 스타일링이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7533f-103">Native styling is not supported on the android renderer, v1.2 introduces the support for styling some properties:</span></span>

## <a name="action-sentiment"></a><span data-ttu-id="7533f-104">작업 감정</span><span class="sxs-lookup"><span data-stu-id="7533f-104">Action Sentiment</span></span>

<span data-ttu-id="7533f-105">**v1.2**에는 작업 감정이 포함되어 있으며 다른 버전만큼 다양한 스타일을 지원하지는 않습니다. 유효한 스타일을 구현하고 다음 줄을 프로젝트의 styles.xml에 추가하여 *부정적* 또는 *긍정적* 감정이 포함된 작업을 스타일링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7533f-105">Action sentiment is included in **v1.2** and while not supporting as many styles as other versions, actions with *destructive* or *positive* sentiment can be styled by implementing a valid style and adding the following line into the styles.xml for your project</span></span>

```styles.xml
 <item name="adaptiveActionDestructive">@style/adaptiveActionDestructive</item>
 <item name="adaptiveActionPositive">@style/adaptiveActionPositive</item>
```

## <a name="inline-action"></a><span data-ttu-id="7533f-106">인라인 작업</span><span class="sxs-lookup"><span data-stu-id="7533f-106">Inline Action</span></span>

<span data-ttu-id="7533f-107">인라인 작업을 사용하는 텍스트 입력은 렌더링하려는 작업의 스타일링을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="7533f-107">Text inputs with an inline action allows styling for the action being rendered.</span></span> <span data-ttu-id="7533f-108">이를 이용하여 작업을 단추(adaptiveInlineAction) 또는 이미지(adaptiveInlineActionImage)로 스타일링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7533f-108">This allows styling the action as a button (adaptiveInlineAction) or as an image (adaptiveInlineActionImage)</span></span>

```styles.xml
 <item name="adaptiveInlineAction">@style/adaptiveInlineAction</item>
 <item name="adaptiveInlineActionImage">@style/adaptiveInlineActionImage</item>
```

> [!IMPORTANT]
> <span data-ttu-id="7533f-109">렌더러는 항목의 정확한 이름을 검색하므로 모든 항목 이름을 여기에 보이는 것처럼 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7533f-109">All item names must be kept as shown here as the renderer looks for those exact names</span></span>
