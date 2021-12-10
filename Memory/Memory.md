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

 4. 9 ways to avoid memory leaks in Android [read] <br>
    https://medium.com/android-news/9-ways-to-avoid-memory-leaks-in-android-b6d81648e35e <br>
    다 읽고 나니 드는 생각이 "아 나는 도대체 얼마나 많은 memory leak을 만들었을까?" 싶었다.
    초보개발자라면 local db로 부터 데이터를 가져올 때 Singleton db class를 사용하여 나도 모르게 activity 또는 fragment의 context를 사용했을지도 모른다
    이렇게 되면 해당 액티비티 또는 프래그먼트가 사라져야할 때 context가 singleton class에 계속 묶여있게 된다.
    activity나 fragment의 context 대신 application context를 사용하자. 만약에 application context를 사용하지 않으면 해당 actitivity나 fragment가
    종료될 때 반드시 context = null 해줄 수 있도록 해야한다.
    이외에도 여러가지 꿀팁들이 많이 있어서 두고두고 읽어볼만 하다

 5. Android : References to a Context and memory leaks [read] <br>
    https://stackoverflow.com/questions/3346080/android-references-to-a-context-and-memory-leaks <br.

 6. [Kotlin] 메모리릭 방지하기 | Kotlin, Lambda의 강력함 | Lambda는 진리입니다. <br>
    https://meetup.toast.com/posts/186 <br>
    기본적으로 Anonymous inner class를 사용하면 Outer class의 Reference를 가지게 된다. 그래서 memory leack이 발생할 여지가 있다.
    반면, SAM, lambda를 사용하면 static field를 생성하여 작업을 진행하므로 상대적으로 memory leak이 발생할 여지가 줄어든다.
    따라서 lambda를 사용하는것이 좋다.

    
    
     