# Bitmap

1. 안드로이드에서의 비트맵과 메모리의 상관관계 <br>
https://medium.com/marojuns-android/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C%EC%97%90%EC%84%9C%EC%9D%98-%EB%B9%84%ED%8A%B8%EB%A7%B5%EA%B3%BC-%EB%A9%94%EB%AA%A8%EB%A6%AC%EC%9D%98-%EC%83%81%EA%B4%80%EA%B4%80%EA%B3%84-125308c293b9

2. 안드로이드 앱 메모리 최적화 <br>
https://d2.naver.com/helloworld/539525

3. Explained: Bitmap vs Vector Graphics <br>
https://www.scan2cad.com/blog/tips/bitmap-vs-vector/

4. Android WebView를 사용한 효과적인 대용량 이미지 로딩 <br>
   https://medium.com/myrealtrip-product/android-webview%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-%ED%9A%A8%EA%B3%BC%EC%A0%81%EC%9D%B8-%EB%8C%80%EC%9A%A9%EB%9F%89-%EC%9D%B4%EB%AF%B8%EC%A7%80-%EB%A1%9C%EB%94%A9-1c20867caa57 <br>
   Glide와 같은 Bitmap을 처리하는 라이브러리가 아닌 WebView를 이용한다는 발상이 신선했다. 중요한건 WebView로 처리하면 Bitmap Heap 메모리를 사용하지 않는다는 것 이다.