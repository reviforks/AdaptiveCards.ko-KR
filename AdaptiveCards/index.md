---
title: 적응형 카드 개요
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 27c7d5ac7da3ae182667cbf8efa90d29f110d1d3
ms.sourcegitcommit: ef03c0eff3272a36cfa88daf99c4d57e4bae9599
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2019
ms.locfileid: "72042528"
---
# <a name="adaptive-cards-overview"></a>적응형 카드 개요 

적응형 카드는 개발자가 일반적이고 일관된 방법으로 UI 콘텐츠를 교환할 수 있는 개방형 카드 교환 형식입니다.

<video controls width="100%" poster="./content/videoposter.png">
    <source src="https://adaptivecardsblob.blob.core.windows.net/assets/AdaptiveCardsOverviewVideo.mp4" type="video/mp4">
</video>

## <a name="how-they-work"></a>작동 방식

[**카드 작성자**](authoring-cards/getting-started.md)는 간단한 JSON 개체로 콘텐츠를 설명합니다. 그런 다음, 해당 콘텐츠는 호스트의 모양과 느낌에 맞게 자동으로 조정되도록 [**호스트 애플리케이션**](rendering-cards/getting-started.md) 내부에서 고유하게 렌더링될 수 있습니다.

예를 들어 Contoso Bot은 Bot Framework를 통해 적응형 카드를 작성할 수 있으며 Skype에 전달될 때 Skype 카드와 비슷한 모양과 느낌을 구현합니다. 동일한 페이로드를 Microsoft Teams에 보낼 때는 Microsoft Teams와 비슷한 모양과 느낌을 구현합니다. 더 많은 호스트 앱이 적응형 카드를 지원하기 시작하면 동일한 페이로드는 이러한 애플리케이션 내에서 자동으로 실행되며, 전부 원래 앱에 있었던 것처럼 느낄 수 있습니다.

모든 것이 친숙하게 느껴지므로 사용자에게 이득입니다. 사용자 환경을 제어할 수 있으므로 앱 호스트에도 이득입니다. 또한 자신의 콘텐츠를 추가 작업 없이 더 널리 퍼뜨릴 수 있으므로 카드 작성자에게도 이득입니다.

## <a name="goals"></a>목표 

적응형 카드의 목표는 다음과 같습니다.

* **이식 가능** - 모든 앱, 디바이스 및 UI 프레임워크
* **개방성** - 오픈 소스이며 공유되는 라이브러리 및 스키마
* **저렴한 비용** - 손쉬운 정의, 손쉬운 사용
* **표현력** - 개발자가 생성하고자 하는 콘텐츠의 롱 테일(Long Tail)이 목표
* **순수하게 선언적** - 코드가 필요하지 않거나 허용되지 않음
* **자동으로 스타일 지정** - 호스트 애플리케이션 UX 및 브랜드 지침에 맞게

## <a name="for-card-authors"></a>카드 작성자의 경우
적응형 카드는 카드 작성자에게 아주 좋습니다.

* **하나의 스키마** - 단일 형식으로 카드 생산 비용을 최소화하고 카드가 사용될 수 있는 장소의 수는 최대화합니다.
* **풍부한 식** - 더 풍부한 팔레트를 통해 콘텐츠를 자신이 표현하고자 하는 것과 더 밀접하게 조정할 수 있습니다.
* **광범위한 도달률** - 콘텐츠는 광범위한 애플리케이션 세트에서 작동하지만, 새 스키마를 배울 필요는 없습니다.
* **입력 컨트롤** - 카드를 보는 사용자로부터 정보를 수집하기 위한 입력 제어를 카드에 포함시킬 수 있습니다.
* **더 나은 도구** - 오픈 카드 에코시스템은 모두가 공유하는 더 나은 도구를 의미합니다.

## <a name="for-experience-owners"></a>환경 소유자의 경우
타사 콘텐츠의 에코시스템으로 진입하려는 앱 개발자라면 다음과 같은 이유로 적응형 카드가 마음에 드실 겁니다.

* **일관된 사용자 환경** - 렌더링된 카드의 스타일을 소유하므로 사용자에게 일관된 환경을 보장합니다.
* **기본 성능** - UI 프레임워크를 직접 대상으로 하므로 기본 성능을 얻을 수 있습니다.
* **안전** - 콘텐츠는 안전한 페이로드로 제공되므로 UI 프레임워크를 원시 태그 및 스크립팅에 개방할 필요가 없습니다.
* **손쉬운 구현** - 라이브러리를 상용화하여 지원하는 플랫폼에서 손쉽게 통합할 수 있습니다. 
* **무료 설명서** - 사유 스키마를 고안, 구현 및 문서화할 필요가 없으므로 시간이 절약됩니다.
* **공유 도구** - 사용자 지정 도구를 만들 필요가 없으므로 시간이 절약됩니다.

## <a name="core-design-principles"></a>주요 디자인 원칙 

적응형 카드는 디자인이 제대로 진행되도록 하는 데 유용한 [기본 원칙](resources/principles.md) 세트에 의해 제어됩니다. 

### <a name="semantic-instead-of-pixel-perfect"></a>정확한 픽셀 대신 의미 체계
Microsoft는 정확한 픽셀 레이아웃과는 대조적으로 의미 체계 값과 개념을 위해 가능한 한 많은 노력을 해왔습니다. 의미 체계 식의 예제는 색상, 크기 및 FactSet와 ImageSet 같은 요소에 나타납니다. 이 모든 것은 호스트 애플리케이션이 실제 모양과 느낌에 대해 더 나은 결정을 내릴 수 있게 해줍니다.

### <a name="card-authors-own-the-content-host-app-owns-the-look-and-feel"></a>카드 작성자는 콘텐츠를 소유하고, 호스트 앱은 모양과 느낌을 소유합니다.
카드 작성자는 자신들이 말하고자 하는 내용을 소유하지만, 그것을 표시하는 애플리케이션은 작성자 애플리케이션의 컨텍스트에서 카드의 모양과 느낌을 소유합니다.

### <a name="keep-it-simple-but-expressive"></a>간단하면서 다양한 표현
적응형 카드가 다양한 표현을 하고 범용적이길 원하지만 UI 프레임워크를 빌드하고 싶지는 않습니다.  목표는 문서에서 Markdown이 충분히 표현되는 것과 동일한 방법으로 “충분히 다양한 표현을 구현”하는 중간 계층을 만드는 것입니다.

Markdown은 간단하고 다양한 표현에 초점을 맞추면서 문서 콘텐츠에 대한 쉽고 일관된 설명을 만들었습니다.  동일한 방법으로 적응형 카드도 카드 콘텐츠를 설명하는 간단하고 효과적인 수단을 만들 수 있다고 생각합니다.

### <a name="when-in-doubt-keep-it-out"></a>의문이 있다면 제외
실수를 감수하며 사는 것보다 나중에 추가하는 것이 더 쉽습니다. 만약 무언가를 추가해야 할지 말지를 논쟁한다면 그대로 놔두기로 결정했습니다.  지원하지 않아도 되는 레거시가 잇는 것보다 속성을 추가하는 것이 항상 더 쉽습니다.


## <a name="build-2019-session"></a>2019 세션 빌드

Microsoft Build 컨퍼런스의 다음 세션은 다양한 사용 사례에서 적응형 카드를 소개합니다. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/wT1yFr_j6IM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
