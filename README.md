# miniSpotifyApp
A Kotlin Spotify favorite app by leveraging Android Jetpack Library and Hilt Dependency Injection

## Feature

- Implemented the BottomBar & App Navigation using Jetpack Navigation component. Built the feed/album/favorite UI Jetpack Compose following MVVM architecture.
- Created a mock RESTFUL Api json-server with Ktor and used the Retrofit to handle requests.
- Utilized Hilt to do dependency injection, including repository layers within "favorite" and "home" features.
- Enable the local cache ability for favorite feature by using Room Database.
- Integrated the Google Exoplayer to handle the global music playback.


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

Automation,
```
Application                 <- Hilt
    |
    |- Activity             <- Hilt EntryPoint
           |
           |-Fragment       <- Hilt  EntryPoint
           |-Fragment
```
## Build the lite Restful Server with Ktor

Ktor is a back-end server using Kotlin. Concurrency control, 
