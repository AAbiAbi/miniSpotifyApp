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

## Compose

