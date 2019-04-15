---
title: 음성 및 고급 사용자 지정
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 19e77b86da9d163f5fcf6a6074071a4638a8d793
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552615"
---
# <a name="speech-and-advanced-customization"></a>음성 및 고급 사용자 지정
우리 Cortana와 같은 서비스를 통해 음성 상호 작용의 시대에 살고 있습니다.  Adaptive card는 하루에서 음성 변환, 멋진 새로운 바늘 전체 시나리오를 지원 하도록 설계 되었습니다.

`speak` 태그 적응 카드 시각적 표시 되지 위치 기본 환경 같은 자동차 대시보드를 구동 하는 동안 환경에 전달할 수 있습니다. 

## <a name="speak-property"></a>속성 사용
음성 것을 지원 하기는 `speak` 사용자에 게 텍스트를 포함 하는 속성입니다. 음성 합성 태그 언어를 사용 하 여 텍스트 주석을 추가할 수 있습니다 ([SSML](https://msdn.microsoft.com/en-us/library/office/hh361578)). SSML 속도, 톤 및 음성의 변 곡점 제어합니다.  도 수 있도록 스트림에 오디오를 렌더 TTS 오디오 스트림을 자체 서비스에서 사용자 지정에 대 한 상당한 유연성을 제공 합니다.

두 가지 패턴에 대 한 호스트 응용 프로그램 속성의 사용을 말하고 있습니다.

* **배송** -카드, 전달 하는 경우 클라이언트는 전체적으로 카드를 설명 하는 카드에 대 한 읽기 속성 읽기를 바꿀 수 있습니다.
* **주문형** -각 요소에 대 한 태그를 말하기에서 스키마에서 지 원하는 다양 한 내게 필요한 옵션 모델을 지원 하기 위해. 클라이언트는 카드의 각 요소에 대해 말하기 속성을 읽을 수 있습니다.

### <a name="examples"></a>예

```json
    "speak":"hello world!"

    "speak":"<s>This is sentence 1.</s><s>This is sentence two</s>"

    "speak":"<speak><audio src='https://www.soundjay.com/misc/bell-ringing-04.mp3'/><s>Time to wake up!</s></speak>"
```

## <a name="speech-content-design"></a>음성 콘텐츠 디자인

음성에 대 한 디자인 콘텐츠는 시각적 표시를 위한 콘텐츠와 다릅니다. 사용자에 게는 해당 하는 방식으로 정보를 제공 하는 전체 visual 환경을 디자인 하는 카드를 디자인할 때. 음성을 디자인할 때 능력이 게는 사용자는 방식으로 콘텐츠를 설명 하는 방법을 고려해 야 합니다.  
