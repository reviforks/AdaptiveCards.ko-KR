---
title: Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: 735f0f8ed1f0d3fdc78f1c840a7aba1892faa5d4
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553365"
---
# <a name="extensibility---android"></a><span data-ttu-id="0cee4-102">확장성-Android</span><span class="sxs-lookup"><span data-stu-id="0cee4-102">Extensibility - Android</span></span>

## <a name="custom-parsing-of-card-elements"></a><span data-ttu-id="0cee4-103">사용자 지정 카드 요소의 구문 분석</span><span class="sxs-lookup"><span data-stu-id="0cee4-103">Custom Parsing of Card Elements</span></span>

<span data-ttu-id="0cee4-104">사용자가 정의한 지원 카드 요소 파서를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cee4-104">You may extend the parser to suport card elements that you have defined.</span></span> <span data-ttu-id="0cee4-105">예를 들어, 다음과 같은 새 요소 형식이 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="0cee4-105">For example, say we have a new element type that looks like this:</span></span>
```json
{
    "type" : "MyType",
    "MyTypeData" : "My data"
}
```

<span data-ttu-id="0cee4-106">그런 다음 다음 줄을 BaseCardElement에서 확장 된 CardElement 구문 분석 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0cee4-106">Then the following lines demonstrate how to parse it into a CardElement that extends from the BaseCardElement:</span></span>
```java
public class MyCustomCardElement extends BaseCardElement
{

    public MyCustomCardElement(CardElementType type) {
        super(type);
    }

    public String getMyTypeData()
    {
        return myTypeData;
    }

    public void setMyTypeData(String data)
    {
        myTypeData = data;
    }

    private String myTypeData;
}

public class MyCardElementParser extends BaseCardElementParser
{
    @Override
    public BaseCardElement Deserialize(ElementParserRegistration elementParserRegistration, ActionParserRegistration actionParserRegistration, JsonValue value)
    {
        MyCustomCardElement element = new CustomCardElement(CardElementType.Custom);
        element.SetElementTypeString("MyType");
        String val = value.getString();
        try {
            JSONObject obj = new JSONObject(val);
            element.setMyTypeData(obj.getString("secret"));
        } catch (JSONException e) {
            e.printStackTrace();
            element.setMyTypeData("Failed");
        }
        return element;
    }
}
```

<span data-ttu-id="0cee4-107">및 사용자 지정 요소를 포함 하는 AdaptiveCard 개체를 가져온 파서가 등록 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0cee4-107">And this is how to register the parser and get an AdaptiveCard object that contains the custom element:</span></span>
```java
// Create an ElementParserRegistrationObject and add your parser to it
ElementParserRegistration elementParserRegistration = new ElementParserRegistration();
elementParserRegistration.AddParser("MyType", new MyCardElementParser());

AdaptiveCard adaptiveCard = AdaptiveCard.DeserializeFromString(jsonText, elementParserRegistration);
```

<span data-ttu-id="0cee4-108">다음 사용자 지정 요소 렌더링은</span><span class="sxs-lookup"><span data-stu-id="0cee4-108">Next comes rendering the custom element</span></span>

## <a name="custom-rendering-of-card-elements"></a><span data-ttu-id="0cee4-109">카드 요소의 사용자 지정 렌더링</span><span class="sxs-lookup"><span data-stu-id="0cee4-109">Custom Rendering of Card Elements</span></span>

<span data-ttu-id="0cee4-110">이 형식에 대 한 고유한 사용자 지정 렌더러를 정의 하려면 먼저 BaseCardElementParser에서 확장 하는 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cee4-110">To define our own custom renderer for our type, we must first create a class that extends from BaseCardElementParser:</span></span>
```java
public class MyCardElementRenderer extends BaseCardElementRenderer
{
    @Override
    public View render(Context context, FragmentManager fragmentManager, ViewGroup viewGroup, BaseCardElement baseCardElement, Vector<IInputHandler> inputActionHandlerList, ICardActionHandler cardActionHandler, HostConfig hostConfig, ContainerStyle containerStyle) {

        //Call findImplObj on baseCardElement to get the instace we returned at parse. We can then cast that object to our type
        CustomCardElement element = (CustomCardElement) baseCardElement.findImplObj();

        //Create some view and add it to the view group
        TextView textView = new TextView(context);
        textView.setText(element.getMyTypeData());
        textView.setAllCaps(true);
        viewGroup.addView(textView);

        //return the view
        return textView;
    }
}
```

<span data-ttu-id="0cee4-111">이 렌더러 등록 한 후 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cee4-111">We then register this renderer like so:</span></span>
```java
CardRendererRegistration.getInstance().registerRenderer("MyType", new CustomBlahRenderer());

RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, getSupportFragmentManager(), adaptiveCard, cardActionHandler, new HostConfig());
```

