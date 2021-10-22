 # Memory
 
 1. [Android] Android Memory Leak 사례 <br>
    https://medium.com/@joongwon/android-memory-leak-%EC%82%AC%EB%A1%80-6565b817a8fe

 
 2. Stressing memory on Android <br>
    https://www.amanjeet.me/stressing-memory-on-android/ 


 3. Java Garbage Collection [read] <br>
    https://d2.naver.com/helloworld/1329 <br>
    읽고 나니 드는 생각은 다른건 몰라도 절대로 명시적으로 System.gc()를 호출하지 말 것 <br>
    (https://codingdog.tistory.com/entry/java-systemgc-%ED%95%A8%EC%88%98-%EC%93%B0%EC%A7%80-%EB%A7%90%EC%95%84%EC%95%BC-%ED%95%A0-%EC%A0%95%EB%8F%84%EB%A1%9C-%EB%AC%B4%EA%B2%81%EB%8B%A4?category=1055041 <= 해당 블로그에서도 같은 말을 함)
    과 HotSpot VM에서 2개의 물리적 공간인 young영역과 old영역이 있다는 것 이다. 우선 System.gc()를 사용하면 어떤 GC알고리즘을 사용하던간에 GC를 실행하는 쓰레드를 제외한
    나머지 모든 쓰레드가 작업을 멈추게 된다. 그렇기 때문에 GC를하려고 다른 작업중인 쓰레드가 멈춰버리는 큰 비용을 내야만 하는 것 이다. GC영역으로 들어가는 과정은 우선 Eden 영역에 객체가 최초로 
    만들어지고 Survivor영역을 통해서 접근 불가능 상태가 되지 않을 시 old영역으로 가게 된다. young영역은 Eden과 Suvivor를 포함한다.
    old영역의 garbage들을 아무래도 young영역에서 사라지지 않았기 때문에 넘어온 것이라 할당 영역의 크기가 큰 만큼
    old영역에서의 GC는 덜 발생하게 된다. 


