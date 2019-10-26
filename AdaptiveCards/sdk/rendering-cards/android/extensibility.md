---
title: Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: 9e13ebad04c780db83d25129a9f5829a9d43ef69
ms.sourcegitcommit: ce044dc969d9b9c47a52bd361bfe2b746071913b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72917116"
---
# <a name="extensibility---android"></a><span data-ttu-id="592d2-102">확장성 - Android</span><span class="sxs-lookup"><span data-stu-id="592d2-102">Extensibility - Android</span></span>

<span data-ttu-id="592d2-103">Android 렌더러를 확장 하 여 다음과 같은 여러 가지 시나리오를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-103">The Android renderer can be extended to support multiple scenarios including:</span></span>
* [<span data-ttu-id="592d2-104">카드 요소의 사용자 지정 구문 분석</span><span class="sxs-lookup"><span data-stu-id="592d2-104">Custom Parsing of Card Elements</span></span>](#custom-parsing-of-card-elements)
* [<span data-ttu-id="592d2-105">카드 요소의 사용자 지정 렌더링</span><span class="sxs-lookup"><span data-stu-id="592d2-105">Custom Rendering of Card Elements</span></span>](#custom-rendering-of-card-elements)
* <span data-ttu-id="592d2-106">[액션의 사용자 지정 렌더링](#custom-rendering-of-actions) (v 1.2 이후)</span><span class="sxs-lookup"><span data-stu-id="592d2-106">[Custom Rendering of Actions](#custom-rendering-of-actions) (Since v1.2)</span></span>
* <span data-ttu-id="592d2-107">[사용자 지정 이미지 로드](#custom-image-loading) (v 1.0.1 이후)</span><span class="sxs-lookup"><span data-stu-id="592d2-107">[Custom Image Loading](#custom-image-loading) (Since v1.0.1)</span></span>
* <span data-ttu-id="592d2-108">[사용자 지정 미디어 로드](#custom-media-loading) (v 1.1 이후)</span><span class="sxs-lookup"><span data-stu-id="592d2-108">[Custom Media Loading](#custom-media-loading) (Since v1.1)</span></span>

## <a name="custom-parsing-of-card-elements"></a><span data-ttu-id="592d2-109">카드 요소의 사용자 지정 구문 분석</span><span class="sxs-lookup"><span data-stu-id="592d2-109">Custom Parsing of Card Elements</span></span>

<span data-ttu-id="592d2-110">정의한 카드 요소를 지원하도록 파서를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-110">You may extend the parser to support card elements that you have defined.</span></span> <span data-ttu-id="592d2-111">예를 들어 다음과 같은 새로운 요소 형식이 있다고 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-111">For example, say we have a new element type that looks like this:</span></span>
```json
{
    "type" : "MyType",
    "MyTypeData" : "My data"
}
```

<span data-ttu-id="592d2-112">다음 줄은 이 요소를 BaseCardElement에서 확장되는 CardElement로 구문 분석하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-112">Then the following lines demonstrate how to parse it into a CardElement that extends from the BaseCardElement:</span></span>
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

<span data-ttu-id="592d2-113">그리고 다음은 파서를 등록하고 사용자 지정 요소가 포함된 AdaptiveCard 개체를 가져오는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-113">And this is how to register the parser and get an AdaptiveCard object that contains the custom element:</span></span>
```java
// Create an ElementParserRegistrationObject and add your parser to it
ElementParserRegistration elementParserRegistration = new ElementParserRegistration();
elementParserRegistration.AddParser("MyType", new MyCardElementParser());

AdaptiveCard adaptiveCard = AdaptiveCard.DeserializeFromString(jsonText, elementParserRegistration);
```

<span data-ttu-id="592d2-114">그 다음은 사용자 지정 요소 렌더링입니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-114">Next comes rendering the custom element</span></span>

## <a name="custom-rendering-of-card-elements"></a><span data-ttu-id="592d2-115">카드 요소의 사용자 지정 렌더링</span><span class="sxs-lookup"><span data-stu-id="592d2-115">Custom Rendering of Card Elements</span></span>

> [!IMPORTANT]
>
> <span data-ttu-id="592d2-116">**주요 변경 내용 목록**</span><span class="sxs-lookup"><span data-stu-id="592d2-116">**List of Breaking Changes**</span></span>
>
> [<span data-ttu-id="592d2-117">v1.2의 주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="592d2-117">Breaking changes for v1.2</span></span>](#breaking-changes-for-v12)

<span data-ttu-id="592d2-118">형식에 대 한 사용자 지정 렌더러를 정의 하려면 먼저 ```BaseCardElementRenderer```에서 확장 되는 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-118">To define our own custom renderer for our type, we must first create a class that extends from ```BaseCardElementRenderer```:</span></span>
```java
public class MyCardElementRenderer extends BaseCardElementRenderer
{
    @Override
    public View render(Context context, FragmentManager fragmentManager, ViewGroup viewGroup, BaseCardElement baseCardElement, Vector<IInputHandler> inputActionHandlerList, ICardActionHandler cardActionHandler, HostConfig hostConfig, ContainerStyle containerStyle) {

        //Call findImplObj on baseCardElement to get the instance we returned at parse. We can then cast that object to our type
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

<span data-ttu-id="592d2-119">그 후 다음과 같이 이 렌더러를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-119">We then register this renderer like so:</span></span>
```java
CardRendererRegistration.getInstance().registerRenderer("MyType", new CustomBlahRenderer());

RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, fragmentManager, adaptiveCard, cardActionHandler,  hostConfig);
```

### <a name="breaking-changes-for-v12"></a><span data-ttu-id="592d2-120">V 1.2의 주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="592d2-120">Breaking changes for v1.2</span></span>

<span data-ttu-id="592d2-121">```render``` 메서드가 ```RenderedAdaptiveCard``` 매개 변수를 포함 하도록 변경 되었으며 이제 ContainerStyle이 포함 된 RenderArgs에 대해 ```ContainerStyle``` 변경 되어 BaseCardElementRenderer을 확장 하는 클래스가 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-121">The ```render``` method was changed to include the ```RenderedAdaptiveCard``` parameter and ```ContainerStyle``` was changed for a RenderArgs where the ContainerStyle is now contained so a class that extends BaseCardElementRenderer should look like this</span></span>

```
public class MyCardElementRenderer extends BaseCardElementRenderer
{
    @Override
    public View render(RenderedAdaptiveCard renderedAdaptiveCard, Context context, FragmentManager fragmentManager, ViewGroup viewGroup,
                       BaseCardElement baseCardElement, ICardActionHandler cardActionHandler, HostConfig hostConfig, RenderArgs renderArgs)
    { }
}
```

## <a name="custom-parsing-of-card-actions"></a><span data-ttu-id="592d2-122">카드 작업의 사용자 지정 구문 분석</span><span class="sxs-lookup"><span data-stu-id="592d2-122">Custom Parsing of Card Actions</span></span>

<span data-ttu-id="592d2-123">사용자 지정 작업을 구문 분석할 수 있는 기능을 제공 하는 것과 유사 하 게 사용자 지정 카드 요소를</span><span class="sxs-lookup"><span data-stu-id="592d2-123">Similarly to parsing custom card elements in v1.2 the possibility to parse custom actions was introduced.</span></span> <span data-ttu-id="592d2-124">예를 들어 다음과 같은 새 동작 형식이 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-124">For example, say we have a new action type that looks like this:</span></span>
```json
{
    "type" : "MyAction",
    "ActionData" : "My data"
}
```

<span data-ttu-id="592d2-125">그런 다음, 다음 줄은 ```BaseActionElement```에서 확장 되는 ActionElement로 구문 분석 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-125">Then the following lines demonstrate how to parse it into a ActionElement that extends from the ```BaseActionElement```:</span></span>
```java
public class MyActionElement extends BaseActionElement
{
    public MyActionElement(ActionType type) 
    {
        super(type);
    }

    public String getActionData()
    {
        return mActionData;
    }

    public void setActionData(String s)
    {
        mActionData = s;
    }

    private String mActionData;
    public static final String MyActionId = "myAction";
}

public class MyActionParser extends ActionElementParser
{
    @Override
    public BaseActionElement Deserialize(ParseContext context, JsonValue value)
    {
        MyActionElement element = new MyActionElement(ActionType.Custom);
        element.SetElementTypeString(MyActionElement.MyActionId);
        String val = value.getString();
        try {
            JSONObject obj = new JSONObject(val);
            element.setActionData(obj.getString("ActionData"));
        } catch (JSONException e) {
            e.printStackTrace();
            element.setActionData("Failure");
        }
        return element;
    }

    @Override
    public BaseActionElement DeserializeFromString(ParseContext context, String jsonString)
    {
        MyActionElement element = new MyActionElement(ActionType.Custom);
        element.SetElementTypeString(MyActionElement.MyActionId);
        try {
            JSONObject obj = new JSONObject(jsonString);
            element.setBackwardString(obj.getString("ActionData"));
        } catch (JSONException e) {
            e.printStackTrace();
            element.setBackwardString("Failure");
        }
        return element;
    }
}
```

<span data-ttu-id="592d2-126">다음 줄은 파서를 등록 하 고 사용자 지정 동작 요소를 포함 하는 AdaptiveCard 개체를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-126">And the next lines demonstrate how to register the parser and get an AdaptiveCard object that contains the custom action element:</span></span>
```java
// Create an ActionParserRegistration and add your parser to it
ActionParserRegistration actionParserRegistration = new ActionParserRegistration();
actionParserRegistration.AddParser(MyActionElement.MyActionId, new MyActionParser());

ParseContext context = new ParseContext(null, actionParserRegistration);
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, context);
```

<span data-ttu-id="592d2-127">다음에는 사용자 지정 작업 렌더링을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-127">Next comes rendering the custom action</span></span>

## <a name="custom-rendering-of-actions"></a><span data-ttu-id="592d2-128">작업의 사용자 지정 렌더링</span><span class="sxs-lookup"><span data-stu-id="592d2-128">Custom Rendering of Actions</span></span>

<span data-ttu-id="592d2-129">형식에 대 한 고유한 사용자 지정 작업 렌더러를 정의 하려면 먼저 ```BaseActionElementRenderer```에서 확장 되는 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-129">To define our own custom action renderer for our type, we must first create a class that extends from ```BaseActionElementRenderer```:</span></span>
```java
public class MyActionRenderer extends BaseActionElementRenderer
{
    @Override
    public Button render(RenderedAdaptiveCard renderedCard,
                         Context context,
                         FragmentManager fragmentManager,
                         ViewGroup viewGroup,
                         BaseActionElement baseActionElement,
                         ICardActionHandler cardActionHandler,
                         HostConfig hostConfig,
                         RenderArgs renderArgs)
    {
        Button myActionButton = new Button(context);

        CustomActionElement customAction = (CustomActionElement) baseActionElement.findImplObj();

        myActionButton.setBackgroundColor(getResources().getColor(R.color.greenActionColor));
        myActionButton.setText(customAction.getMessage());
        myActionButton.setAllCaps(false);
        myActionButton.setOnClickListener(new BaseActionElementRenderer.ActionOnClickListener(renderedCard, baseActionElement, cardActionHandler));

        viewGroup.addView(myActionButton);

        return myActionButton;
    }
}
```

<span data-ttu-id="592d2-130">그 후 다음과 같이 이 렌더러를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-130">We then register this renderer like so:</span></span>
```java
CardRendererRegistration.getInstance().registerActionRenderer("myAction", new CustomActionRenderer());

RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, fragmentManager, adaptiveCard, cardActionHandler, hostConfig);
```

## <a name="custom-rendering-of-actions"></a><span data-ttu-id="592d2-131">작업의 사용자 지정 렌더링</span><span class="sxs-lookup"><span data-stu-id="592d2-131">Custom rendering of actions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="592d2-132">v1.2에서 작업의 사용자 지정 렌더링을 변경할 계획이며, 아직은 변경되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-132">Changes to the custom rendering of actions are planned for v1.2 but are not completed yet</span></span>

## <a name="custom-image-loading"></a><span data-ttu-id="592d2-133">사용자 지정 이미지 로드</span><span class="sxs-lookup"><span data-stu-id="592d2-133">Custom image loading</span></span>

### <a name="ionlineimageloader"></a><span data-ttu-id="592d2-134">IOnlineImageLoader</span><span class="sxs-lookup"><span data-stu-id="592d2-134">IOnlineImageLoader</span></span>

> [!IMPORTANT]
> <span data-ttu-id="592d2-135">**IOnlineImageLoader는 하나만 등록할 수 있으며 이미지를 검색하는 기본 방법보다 우선합니다.**</span><span class="sxs-lookup"><span data-stu-id="592d2-135">**Only one IOnlineImageLoader can be registered and it takes precedence against the default way of retrieving images**</span></span>

<span data-ttu-id="592d2-136">개발자가 온라인 소스에서 검색할 수 없거나 필수 이전 단계를 완료해야만 검색할 수 있는 이미지를 가져올 수 있도록, 이 상황을 해결할 수 있는 IOnlineImageLoader가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-136">In order to allow developers to get images that could not just be downloaded or retrieved from an online source or required previous steps before they could be retrieved, the IOnlineImageLoader was added to solve this kind of situations.</span></span> <span data-ttu-id="592d2-137">OnlineImageLoader를 추가하려면 이 메서드만 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-137">To implement an OnlineImageLoader you must only implement the method</span></span> 

```java
public HttpRequestResult<Bitmap> loadOnlineImage(String url, GenericImageLoaderAsync loader) throws IOException, URISyntaxException
```

<span data-ttu-id="592d2-138">다음은 고양이 이미지에 대한 모든 이미지를 변경하는 OnlineImageLoader의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-138">Here's an example of an OnlineImageLoader which changes all images for a cat image</span></span>

```java
public class OnlineImageLoader implements IOnlineImageLoader
{
    public OnlineImageLoader(){}

    @Override
    public HttpRequestResult<Bitmap> loadOnlineImage(String url, GenericImageLoaderAsync loader) throws IOException, URISyntaxException
    {
        String catImnageUri = "http://adaptivecards.io/content/cats/1.png";
        byte[] bytes = HttpRequestHelper.get(catImnageUri);
        if (bytes == null)
        {
            throw new IOException("Failed to retrieve content from " + catImnageUri);
        }

        Bitmap bitmap = BitmapFactory.decodeByteArray(bytes, 0, bytes.length);

        if (bitmap == null)
        {
            throw new IOException("Failed to convert content to bitmap: " + new String(bytes));
        }

        return new HttpRequestResult<>(bitmap);
    }
}
```

<span data-ttu-id="592d2-139">마지막으로, 이 이미지 로더를 등록하려면 코드에 이 줄만 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-139">Finally, to register this image loader, you must only add this line to your code.</span></span>

```java
CardRendererRegistration.getInstance().registerOnlineImageLoader(new OnlineImageLoader());
```

### <a name="iresourceresolver-deprecates-ionlineimageloader"></a><span data-ttu-id="592d2-140">IResourceResolver(IOnlineImageLoader 사용 중단)</span><span class="sxs-lookup"><span data-stu-id="592d2-140">IResourceResolver (deprecates IOnlineImageLoader)</span></span>

<span data-ttu-id="592d2-141">v1.2에서는 전체 ResourceResolver 지원이 Android 렌더러에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-141">For v1.2, the support for full ResourceResolvers was added to the android renderer.</span></span> <span data-ttu-id="592d2-142">리소스 확인자 구현은 IOnlineImageLoader와 매우 비슷하지만, ResourceResolver가 있으면 개발자가 카드 하나로 모든 소스의 이미지를 검색하는 여러 가지 방법을 추가할 수 있으며, 이 작업은 이미지를 검색할 때 쿼리할 고유의 접두사에 각 ResourceResolver를 연결하는 방식으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-142">The implementation of a resource resolver is really similar to that of a IOnlineImageLoader but having ResourceResolvers allows a developer to add multiple ways to retrieve images from any kind of source in a single card, this is done by linking each ResourceResolver to a unique prefix which will be queried when trying to retrieve an image.</span></span> 

<span data-ttu-id="592d2-143">다음과 비슷한 방법으로 ResourceResolver를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-143">You can implement a ResourceResolver similar to this</span></span>

```java
public class ResourceResolver implements IResourceResolver
{
    @Override
    public HttpRequestResult<Bitmap> resolveImageResource(String uri, GenericImageLoaderAsync genericImageLoaderAsync) throws IOException, URISyntaxException
    {
        Bitmap bitmap;
        String dataUri = AdaptiveBase64Util.ExtractDataFromUri(uri);
        CharVector decodedDataUri = AdaptiveBase64Util.Decode(dataUri);
        byte[] decodedByteArray = Util.getBytes(decodedDataUri);
        bitmap = BitmapFactory.decodeByteArray(decodedByteArray, 0, decodedByteArray.length);

        return new HttpRequestResult<>(bitmap);
    }

    @Override
    public HttpRequestResult<Bitmap> resolveImageResource(String uri, GenericImageLoaderAsync genericImageLoaderAsync, int maxWidth) throws IOException, URISyntaxException
    {
        Bitmap bitmap;
        String dataUri = AdaptiveBase64Util.ExtractDataFromUri(uri);
        CharVector decodedDataUri = AdaptiveBase64Util.Decode(dataUri);

        if (uri.startsWith("data:image/svg")) {
            String svgString = AdaptiveBase64Util.ExtractDataFromUri(uri);
            String decodedSvgString = URLDecoder.decode(svgString, "UTF-8");
            Sharp sharp = Sharp.loadString(decodedSvgString);
            Drawable drawable = sharp.getDrawable();
            bitmap = ImageUtil.drawableToBitmap(drawable, maxWidth);
        }
        else
        {
            try
            {
                return genericImageLoaderAsync.loadDataUriImage(uri);
            }
            catch (Exception e)
            {
                return new HttpRequestResult<>(e);
            }
        }

        return new HttpRequestResult<>(bitmap);
    }
}
```

<span data-ttu-id="592d2-144">앞서 언급했듯이, 여러 ResourceResolver를 등록할 수 있으며, ResourceResolver를 등록하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-144">As mentioned previously, you can register multiple ResourceResolvers, to register a ResourceResolver you can do this</span></span>

```java
 CardRendererRegistration.getInstance().registerResourceResolver("data", new ResourceResolver());
 CardRendererRegistration.getInstance().registerResourceResolver("anotherPrefix", new AnotherResourceResolver());
```

#### <a name="transforming-an-ionlineimageloader-to-an-iresourceresolver"></a><span data-ttu-id="592d2-145">IOnlineImageLoader를 IResourceResolver로 변환</span><span class="sxs-lookup"><span data-stu-id="592d2-145">Transforming an IOnlineImageLoader to an IResourceResolver</span></span> 

<span data-ttu-id="592d2-146">IResourceResolver의 메서드를 IOnlineImageLoader와 최대한 비슷하게 유지하기 위해 노력했기 때문에 IOnlineImageLoader를 IResourceResolver로 변환하는 방법은 매우 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-146">Transforming an IOnlineImageLoader to an IResourceResolver is a fairly easy task as the methods for the latter were tried to keep as similar as the IOnlineImageLoader as possible</span></span>

```java
 // IOnlineImageLoader
 public HttpRequestResult<Bitmap> loadOnlineImage(String url, GenericImageLoaderAsync loader) throws IOException, URISyntaxException

 // IResourceResolver
 public HttpRequestResult<Bitmap> resolveImageResource(String uri, GenericImageLoaderAsync genericImageLoaderAsync) throws IOException, URISyntaxException
 public HttpRequestResult<Bitmap> resolveImageResource(String uri, GenericImageLoaderAsync genericImageLoaderAsync, int maxWidth) throws IOException, URISyntaxException
```

<span data-ttu-id="592d2-147">보시는 것처럼, 가장 큰 변화는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-147">As you can see, the biggest changes are</span></span>

* <span data-ttu-id="592d2-148">```loadOnlineImage(String, GenericImageLoaderAsync)``` 이름이 ```resolveImageResource(String, GenericImageLoaderAsync)```</span><span class="sxs-lookup"><span data-stu-id="592d2-148">```loadOnlineImage(String, GenericImageLoaderAsync)``` was renamed to ```resolveImageResource(String, GenericImageLoaderAsync)```</span></span>
* <span data-ttu-id="592d2-149">최대 너비가 필요한 시나리오를 지원 하기 위해 ```resolveImageResource(String, GenericImageLoaderAsync)```에 대 한 오버 로드가 ```resolveImageResource(String, GenericImageLoaderAsync, int)```으로 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-149">an overload for ```resolveImageResource(String, GenericImageLoaderAsync)``` was added as ```resolveImageResource(String, GenericImageLoaderAsync, int)``` in order to support scenarios where the max width is required</span></span>

## <a name="custom-media-loading"></a><span data-ttu-id="592d2-150">사용자 지정 미디어 로드</span><span class="sxs-lookup"><span data-stu-id="592d2-150">Custom Media Loading</span></span>

> [!IMPORTANT]
> <span data-ttu-id="592d2-151">**API 레벨 23 또는 Android M에서 추가 된 ```MediaDataSource``` 필요한 ```IOnlineMediaLoader```를 잊지 마세요.**</span><span class="sxs-lookup"><span data-stu-id="592d2-151">**Remember ```IOnlineMediaLoader``` requires ```MediaDataSource``` which was added in API level 23 or Android M**</span></span>

<span data-ttu-id="592d2-152">미디어 요소가 포함되면서, 개발자가 기본 mediaPlayer 요소에 사용되는 [MediaDataSource](https://developer.android.com/reference/android/media/MediaDataSource)를 재정의할 수 있도록 IOnlineMediaLoader 인터페이스도 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-152">Along with the inclusion of the media element, also was the inclusion of the IOnlineMediaLoader interface which allows developers to override the [MediaDataSource](https://developer.android.com/reference/android/media/MediaDataSource) used for the underlying mediaPlayer element.</span></span> <span data-ttu-id="592d2-153">**(Android M 필요)**</span><span class="sxs-lookup"><span data-stu-id="592d2-153">**(Requires android M)**</span></span>

<span data-ttu-id="592d2-154">가장 먼저 해야 할 일은 IOnlineImageLoader를 구현하는 클래스를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-154">The first needed thing to do is creating a class that implements IOnlineImageLoader</span></span>

```java
@RequiresApi(api = Build.VERSION_CODES.M)
public class OnlineMediaLoader implements IOnlineMediaLoader
{
    /* This class checks if the media source exists */
    public class OnlineFileAvailableChecker extends AsyncTask<String, Void, Boolean>
    {
        public OnlineFileAvailableChecker(String uri)
        {
            m_uri = uri;
        }

        @Override
        protected Boolean doInBackground(String... strings) {
            // if the provided uri is a valid uri or is valid with the resource resolver, then use that
            // otherwise, try to get the media from a local file
            try
            {
                HttpRequestHelper.query(m_uri);
                return true;
            }
            catch (Exception e)
            {
                // Do nothing if the media was not found at all
                e.printStackTrace();
                return false;
            }
        }

        private String m_uri;
   }

       
   @Override
   public MediaDataSource loadOnlineMedia(MediaSourceVector mediaSources, IMediaDataSourceOnPreparedListener mediaDataSourceOnPreparedListener)
   {
       final long mediaSourcesSize = mediaSources.size();
       for(int i = 0; i < mediaSourcesSize; i++)
       {
           String mediaUri = mediaSources.get(i).GetUrl();

           OnlineFileAvailableChecker checker = new OnlineFileAvailableChecker(mediaUri);
           try
           {
               Boolean fileExists = checker.execute("").get();
               if(fileExists)
               {
                   return new MediaDataSourceImpl(mediaUri, mediaDataSourceOnPreparedListener);
               }
           }
           catch (Exception e) { }
       }
       return null;
    }
}
```

<span data-ttu-id="592d2-155">OnlineMediaLoader 클래스 구현을 마쳤으면 클래스를 추가하여 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="592d2-155">Once this class has been implemented, you can register your OnlineMediaLoader class by adding</span></span> 
```java
  CardRendererRegistration.getInstance().registerOnlineMediaLoader(new OnlineMediaLoader());
```
