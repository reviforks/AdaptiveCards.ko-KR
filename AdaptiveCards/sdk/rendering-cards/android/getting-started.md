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
# <a name="getting-started---android"></a>시작 - Android

Android 네이티브 컨트롤을 대상으로 하는 렌더러입니다.

## <a name="install-maven-package"></a>Maven 패키지 설치

[![Maven Central](https://img.shields.io/maven-central/v/io.adaptivecards/adaptivecards-android.svg)](https://search.maven.org/#search%7Cga%7C1%7Ca%3A%22adaptivecards-android%22)

게시된 패키지를 찾을 수 있습니다. ![여기](https://search.maven.org/search?q=g:io.adaptivecards)

프로젝트에 라이브러리를 포함하려면 종속성 섹션의 프로젝트 gradle.build에 이 줄을 포함해야 합니다.

```build.gradle
 implementation 'io.adaptivecards:adaptivecards-android:1.1.0'
```
프로젝트에 포함하려는 버전에 따라 버전 번호를 변경해야 합니다.

## <a name="add-import"></a>가져오기 추기

개체 모델을 포함하려면 이 가져오기를 추가합니다.

```
 import io.adaptivecards.objectmodel.*;
```

렌더러를 포함하려면 이 가져오기를 추가합니다.

```
 import io.adaptivecards.renderer.*;
```

## <a name="next-steps"></a>다음 단계

[카드 렌더링](render-a-card.md)에서 다음 단계를 확인합니다.
