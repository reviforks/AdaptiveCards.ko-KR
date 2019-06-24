---
title: Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: 378171186599dd8d103111da183b7fc2e6e01c42
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67134254"
---
# <a name="extensibility---android"></a>확장성 - Android

## <a name="custom-parsing-of-card-elements"></a>카드 요소의 사용자 지정 구문 분석

정의한 카드 요소를 지원하도록 파서를 확장할 수 있습니다. 예를 들어 다음과 같은 새로운 요소 형식이 있다고 가정해 봅니다.
```json
{
    "type" : "MyType",
    "MyTypeData" : "My data"
}
```

다음 줄은 이 요소를 BaseCardElement에서 확장되는 CardElement로 구문 분석하는 방법을 보여줍니다.
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

그리고 다음은 파서를 등록하고 사용자 지정 요소가 포함된 AdaptiveCard 개체를 가져오는 방법입니다.
```java
// Create an ElementParserRegistrationObject and add your parser to it
ElementParserRegistration elementParserRegistration = new ElementParserRegistration();
elementParserRegistration.AddParser("MyType", new MyCardElementParser());

AdaptiveCard adaptiveCard = AdaptiveCard.DeserializeFromString(jsonText, elementParserRegistration);
```

그 다음은 사용자 지정 요소 렌더링입니다.

## <a name="custom-rendering-of-card-elements"></a>카드 요소의 사용자 지정 렌더링

이 형식의 고유한 사용자 지정 렌더러를 정의하려면 먼저 다음과 같이 BaseCardElementParser에서 확장되는 클래스를 만들어야 합니다.
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

그 후 다음과 같이 이 렌더러를 등록합니다.
```java
CardRendererRegistration.getInstance().registerRenderer("MyType", new CustomBlahRenderer());

RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, getSupportFragmentManager(), adaptiveCard, cardActionHandler, new HostConfig());
```

## <a name="custom-rendering-of-actions"></a>작업의 사용자 지정 렌더링

[!IMPORTANT]
> v1.2에서 작업의 사용자 지정 렌더링을 변경할 계획이며, 아직은 변경되지 않았습니다.

## <a name="custom-image-loading"></a>사용자 지정 이미지 로드

### <a name="ionlineimageloader"></a>IOnlineImageLoader

> [!IMPORTANT]
> **IOnlineImageLoader는 하나만 등록할 수 있으며 이미지를 검색하는 기본 방법보다 우선합니다.**

개발자가 온라인 소스에서 검색할 수 없거나 필수 이전 단계를 완료해야만 검색할 수 있는 이미지를 가져올 수 있도록, 이 상황을 해결할 수 있는 IOnlineImageLoader가 추가되었습니다. OnlineImageLoader를 추가하려면 이 메서드만 구현해야 합니다. 

```java
public HttpRequestResult<Bitmap> loadOnlineImage(String url, GenericImageLoaderAsync loader) throws IOException, URISyntaxException
```

다음은 고양이 이미지에 대한 모든 이미지를 변경하는 OnlineImageLoader의 예입니다.

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

마지막으로, 이 이미지 로더를 등록하려면 코드에 이 줄만 추가해야 합니다.

```java
CardRendererRegistration.getInstance().registerOnlineImageLoader(new OnlineImageLoader());
```

### <a name="iresourceresolver-deprecates-ionlineimageloader"></a>IResourceResolver(IOnlineImageLoader 사용 중단)

v1.2에서는 전체 ResourceResolver 지원이 Android 렌더러에 추가되었습니다. 리소스 확인자 구현은 IOnlineImageLoader와 매우 비슷하지만, ResourceResolver가 있으면 개발자가 카드 하나로 모든 소스의 이미지를 검색하는 여러 가지 방법을 추가할 수 있으며, 이 작업은 이미지를 검색할 때 쿼리할 고유의 접두사에 각 ResourceResolver를 연결하는 방식으로 수행됩니다. 

다음과 비슷한 방법으로 ResourceResolver를 구현할 수 있습니다.

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

앞서 언급했듯이, 여러 ResourceResolver를 등록할 수 있으며, ResourceResolver를 등록하는 방법은 다음과 같습니다.

```java
 CardRendererRegistration.getInstance().registerResourceResolver("data", new ResourceResolver());
 CardRendererRegistration.getInstance().registerResourceResolver("anotherPrefix", new AnotherResourceResolver());
```

#### <a name="transforming-an-ionlineimageloader-to-an-iresourceresolver"></a>IOnlineImageLoader를 IResourceResolver로 변환 

IResourceResolver의 메서드를 IOnlineImageLoader와 최대한 비슷하게 유지하기 위해 노력했기 때문에 IOnlineImageLoader를 IResourceResolver로 변환하는 방법은 매우 간단합니다.

```java
 // IOnlineImageLoader
 public HttpRequestResult<Bitmap> loadOnlineImage(String url, GenericImageLoaderAsync loader) throws IOException, URISyntaxException

 // IResourceResolver
 public HttpRequestResult<Bitmap> resolveImageResource(String uri, GenericImageLoaderAsync genericImageLoaderAsync) throws IOException, URISyntaxException
 public HttpRequestResult<Bitmap> resolveImageResource(String uri, GenericImageLoaderAsync genericImageLoaderAsync, int maxWidth) throws IOException, URISyntaxException
```

보시는 것처럼, 가장 큰 변화는 다음과 같습니다.
* loadOnlineImage(문자열, GenericImageLoaderAsync)가 resolveImageResource(문자열, GenericImageLoaderAsync)로 변경되었습니다.
* 최대 너비가 필요한 시나리오를 지원하기 위해 resolveImageResource(문자열, GenericImageLoaderAsync)의 오버로드가 resolveImageResource(문자열, GenericImageLoaderAsync, int)로 추가되었습니다.

## <a name="custom-media-loading"></a>사용자 지정 미디어 로드

> [!IMPORTANT]
> **IOnlineMediaLoader에 필요한 MediaDataSource가 API 레벨 23 또는 Android M에 추가되었습니다.**

미디어 요소가 포함되면서, 개발자가 기본 mediaPlayer 요소에 사용되는 [MediaDataSource](https://developer.android.com/reference/android/media/MediaDataSource)를 재정의할 수 있도록 IOnlineMediaLoader 인터페이스도 포함되었습니다. **(Android M 필요)**

가장 먼저 해야 할 일은 IOnlineImageLoader를 구현하는 클래스를 만드는 것입니다.

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

OnlineMediaLoader 클래스 구현을 마쳤으면 클래스를 추가하여 등록할 수 있습니다. 
```java
  CardRendererRegistration.getInstance().registerOnlineMediaLoader(new OnlineMediaLoader());
```
