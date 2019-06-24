---
title: Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: b5f1279317e6b34d2e3bccee2625d972ac185e04
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67134272"
---
# <a name="getting-started---android"></a><span data-ttu-id="e742f-102">시작 - Android</span><span class="sxs-lookup"><span data-stu-id="e742f-102">Getting started - Android</span></span>

<span data-ttu-id="e742f-103">Android 네이티브 컨트롤을 대상으로 하는 렌더러입니다.</span><span class="sxs-lookup"><span data-stu-id="e742f-103">This is a renderer which targets Android native controls.</span></span>

## <a name="install-maven-package"></a><span data-ttu-id="e742f-104">Maven 패키지 설치</span><span class="sxs-lookup"><span data-stu-id="e742f-104">Install Maven package</span></span>

<span data-ttu-id="e742f-105">[![Maven Central](https://img.shields.io/maven-central/v/io.adaptivecards/adaptivecards-android.svg)](https://search.maven.org/#search%7Cga%7C1%7Ca%3A%22adaptivecards-android%22)</span><span class="sxs-lookup"><span data-stu-id="e742f-105">[![Maven Central](https://img.shields.io/maven-central/v/io.adaptivecards/adaptivecards-android.svg)](https://search.maven.org/#search%7Cga%7C1%7Ca%3A%22adaptivecards-android%22)</span></span>

<span data-ttu-id="e742f-106">게시된 패키지를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e742f-106">You can find the published packages</span></span> ![여기](https://search.maven.org/search?q=g:io.adaptivecards)

<span data-ttu-id="e742f-108">프로젝트에 라이브러리를 포함하려면 종속성 섹션의 프로젝트 gradle.build에 이 줄을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e742f-108">To include library to your project you must include this line into your project gradle.build under the dependencies section</span></span>

```build.gradle
 implementation 'io.adaptivecards:adaptivecards-android:1.1.0'
```
<span data-ttu-id="e742f-109">프로젝트에 포함하려는 버전에 따라 버전 번호를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e742f-109">You need to change the version number depending on the version you want to include into your project</span></span>

## <a name="add-import"></a><span data-ttu-id="e742f-110">가져오기 추기</span><span class="sxs-lookup"><span data-stu-id="e742f-110">Add import</span></span>

<span data-ttu-id="e742f-111">개체 모델을 포함하려면 이 가져오기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e742f-111">To include the object model, add this import</span></span>

```
 import io.adaptivecards.objectmodel.*;
```

<span data-ttu-id="e742f-112">렌더러를 포함하려면 이 가져오기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e742f-112">To include the renderer, add this import</span></span>

```
 import io.adaptivecards.renderer.*;
```

## <a name="next-steps"></a><span data-ttu-id="e742f-113">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e742f-113">Next steps</span></span>

<span data-ttu-id="e742f-114">[카드 렌더링](render-a-card.md)에서 다음 단계를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e742f-114">See [Render a card](render-a-card.md) for the next steps!</span></span>
