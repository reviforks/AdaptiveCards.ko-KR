---
title: 음성 및 고급 사용자 지정
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 19e77b86da9d163f5fcf6a6074071a4638a8d793
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2019
ms.locfileid: "59552615"
---
# <a name="speech-and-advanced-customization"></a>음성 및 고급 사용자 지정
우리는 Cortana와 같은 서비스를 통해 음성으로 상호 작용하는 시대에 살고 있습니다.  적응형 카드는 처음부터 음성을 지원하도록 설계되었으며, 멋진 새 서식 시나리오를 지원합니다.

`speak` 태그는 시각적 디스플레이가 기본 환경이 아닌 환경(예: 주행 중 차량 계기판)에 적응형 카드를 제공할 수 있게 해줍니다. 

## <a name="speak-property"></a>음성 속성
음성을 지원하기 위해 사용자에게 말하는 텍스트가 포함된 `speak` 속성이 있습니다. 음성 합성 마크업 언어([SSML](https://msdn.microsoft.com/en-us/library/office/hh361578))를 사용하여 텍스트에 주석을 달 수 있습니다. SSML은 음성의 속도, 톤, 억양을 제어합니다.  자체 서비스에서 오디오를 스트리밍하거나 TTS 오디오 스트림을 렌더링하여 매우 유연하게 사용자 지정을 할 수 있습니다.

호스트 애플리케이션의 음성 속성 사용 패턴은 두 가지가 있습니다.

* **제공 시** - 카드가 제공되면 클라이언트가 카드의 음성 속성을 읽어서 카드 전체를 설명할지 선택할 수 있습니다.
* **요청 시** - 스키마는 서식이 더 풍부한 접근성 모델을 지원하기 위해 각 요소에 음성 태그를 지원합니다. 클라이언트는 카드에 있는 각 요소의 음성 속성을 읽을 수 있습니다.

### <a name="examples"></a>예

```json
    "speak":"hello world!"

    "speak":"<s>This is sentence 1.</s><s>This is sentence two</s>"

    "speak":"<speak><audio src='https://www.soundjay.com/misc/bell-ringing-04.mp3'/><s>Time to wake up!</s></speak>"
```

## <a name="speech-content-design"></a>음성 콘텐츠 디자인

음성용으로 설계된 콘텐츠는 시각적 표시를 위한 콘텐츠와 다릅니다. 카드를 설계할 때는 사용자가 보는 즐거움을 느낄 수 있게 정보를 제공하도록 전체 시각적 환경을 설계합니다. 음성용으로 설계할 때는 사용자가 듣는 즐거움을 느낄 수 있게 콘텐츠를 말로 설명하는 방식을 생각해 보아야 합니다.  
