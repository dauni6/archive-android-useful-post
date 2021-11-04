# Coroutine

 1. Coroutines under the hood <br>
 https://kt.academy/article/cc-under-the-hood
   

 2. Coroutines on Android (part I): Getting the background <br>
   https://medium.com/androiddevelopers/coroutines-on-android-part-i-getting-the-background-3e0e54d20bb <br>
   시리즈로 존재하는데 내용이 너무 좋아서 꼭 다 볼 것!!
   
   
 3. Kotlin Coroutine — 1. Main-safety는 어떻게 가능한 걸까? <br>
 https://eyegochild.medium.com/kotlin-coroutine-2-main-safety%EB%8A%94-%EC%96%B4%EB%96%BB%EA%B2%8C-%EA%B0%80%EB%8A%A5%ED%95%9C-%EA%B1%B8%EA%B9%8C-91ccb6cd2f7a <br>


 4. Exception handling in Kotlin Coroutines <br>
 https://kt.academy/article/cc-exception-handling

    
 5. Scoping functions in Kotlin Coroutines [read] <br> 
 https://kt.academy/article/cc-scoping-functions <br>
 간단한 예제들로 쉽게 이해할 수 있었고, scoping 사용의 문제점과 하지말아야할 코딩도 알려줘서 좋았다.
 막연하게 사용했던 withContext() { /*..*/} 가 async() { /*..*/ } 대신 사용할 수 있는건 알았는데, 동일하다면 둘 다 사용해도 괜찮다고 생각했으나
 async과 await()를 즉시 사용하는 방법은 피하라고 한다. 어짜피 coroutineScope를 사용하면 스스로 완료되기전까지 모든 자식코루틴을 기다리므로
 이 부분이 바로 async처럼 사용가능하다는 의미가 되는 것이다.
 또한 각 scope function을 어떤 상황에서 써야하는지를 명확히 알려줘서 이해하기 쉽다.
 scoping functions들은 기본적으로 모두 coroutineScope 라고 생각한다. withTimeout과 withTimeoutOrNull도 유용하게 사용할 수 있을 것 같다.
 특히 withTimeoutOrNull을 통해 exception을 동작시키는 withTimeout보다 null로 return하는게 유용하게 사용할 수 있을 것 같다.


 6. Constructing coroutine scope [read] <br>
 https://kt.academy/article/cc-constructing-scope#definition-1


