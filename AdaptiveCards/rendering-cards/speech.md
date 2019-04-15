---
title: 음성 처리
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: daea48607376c84f0e0f0af9450cac7dcdf67c0e
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552485"
---
# <a name="handling-speech"></a><span data-ttu-id="1405b-102">음성 처리</span><span class="sxs-lookup"><span data-stu-id="1405b-102">Handling speech</span></span>

<span data-ttu-id="1405b-103">Adaptive Card는 지원 음성는 `speak` 어떻게 카드 읽어야 소리 내어 사용자에 대 한 정보를 포함 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1405b-103">To support speech adaptive Cards has the `speak` property which contains information on how a card shoudl be read aloud to a user.</span></span>

<span data-ttu-id="1405b-104">음성 태그를 사용 하 여 주석을 추가할 수 있습니다 [SSML 태그](https://msdn.microsoft.com/en-us/library/office/hh361578(v=office.14).aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="1405b-104">The speech tag can be annotated using  [SSML markup](https://msdn.microsoft.com/en-us/library/office/hh361578(v=office.14).aspx).</span></span> <span data-ttu-id="1405b-105">SSML 음성의 변 곡점 기능 컨트롤 톤 속도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1405b-105">SSML gives you the ability control the speed, tone, inflection of the speech.</span></span>  <span data-ttu-id="1405b-106">도 수 있도록 스트림에 오디오를 렌더링 하 TTS 오디오 스트림 자체 서비스에서 많은 양의 사용자 지정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1405b-106">It even allows you to stream audio or a render a TTS audio stream from your own service, giving you a great deal of customization.</span></span>

<span data-ttu-id="1405b-107">2 패턴에 대 한 호스트 응용 프로그램 속성의 사용을 말하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1405b-107">There are 2 patterns for speak property usage by a host application:</span></span>
* <span data-ttu-id="1405b-108">**배송** 카드는 클라이언트에 전달 될 때-전체적으로 카드를 설명 하는 카드에 대 한 읽기 속성 읽기를 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1405b-108">**on delivery** - When a card is delivered a client may opt to read the Speak property for the card to describe the card as a whole.</span></span>
* <span data-ttu-id="1405b-109">**주문형** -요소당를 말하기 태그에서 스키마에서 지 원하는 다양 한 내게 필요한 옵션 모델을 지원 하기 위해.</span><span class="sxs-lookup"><span data-stu-id="1405b-109">**on demand** - In order to support a richer accessibility model the schema supports a speak tag per element.</span></span>  
<span data-ttu-id="1405b-110">이렇게 하면 클라이언트가 접근성 요구 사항 사용 하 여 각 요소를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1405b-110">This allows for clients to read each element to recipients with accessibility requirements.</span></span>

