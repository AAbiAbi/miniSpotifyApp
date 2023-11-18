# miniSpotifyApp
Android app. miniSpotify

## Activity

```bash
View
 |
 |-tab
 |-tab content-fragment container(switch when clicking)
```
  
When you click a icon to the load finish, there are multiple parts(life cycle).

```bash
life cycle:
     Activity launched
       |
    onCreate() UI initialization, pull data, UI structure, only called once.
       |
     onStart() UI start painting
       |
     onResume() UI finish painting
       |
     Activity Running
       |
     onPause()
       |
     onStop()
       |
     onDestory() corresponding onCreate, only doing once in lifecycle
       |
     Activity shut down
```
Both fragment container and activity will own their life cycles. When the app was put to background and to frontground, it will only call onStart(), .. onStop().




## Network

Asynchro, when we call execute, we just wait the i/o thread to return response.And we will continue doing the main thread.

## Dependency Injection

field dependency injection
```java
class CarII{
 lateinit var eignie: Engine

fun start(){}
}

fun main(){
 var gassCarII = CarII()
 //not safe, muttable
gasCarII.engine = GasEngine()
gasCarII.start()

}
```

constructor dependency injection

```java

class Car(private val engine:Engine){
 lateinit var eignie: Engine

fun start(){}
}
fun main(){
 var gasCar = Car(GasEngine())
 gasCar.start()
 

}
```

