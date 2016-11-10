# JCPlayer
A simple JcAudio player for Android that you can plugin to your apps quickly get JcAudio playback working.

## Tested URLs
- http://xxxx/abc.mp3

## Not tested URLs
- http://xxxx/abc.m4a
- http://xxxx:1232
- http://xxxx/abc.pls
- http://xxxx/abc.ram
- http://xxxx/abc.wax
- rtmp://xxxx
- http://xxxx/abc.aspx
- http://xxxx/abc.php
- http://xxxx/abc.html
- mms://xxxx

##Maven
```Gradle
allprojects {
    repositories {
        jcenter()
        maven {
            url  "http://dl.bintray.com/jeancsanchez/maven"
        }
    }
}
```
##Gradle Dependency
```Gradle
dependencies {
    // ... other dependencies
    compile 'io.github.jeancsanchez.jcplayer:jcplayer:2.0.2-alpha'
}
```


##Getting Started
You only need  a JcPlayerView on your Layout Activity. All the controls and everything else are created by the player view itself.
```xml
<com.example.jean.jcplayer.JcPlayerView
    android:id="@+id/jcplayer"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
</com.example.jean.jcplayer.JcPlayerView>
```

##Code Setup
####Find your JcPlayerView xml and...
```java
    jcplayerView = (JcPlayerView) findViewById(R.id.jcplayerView);
```

###Option 1: Just play 
```java
    jcplayerView.playAudio("http://www.example.com.br/audio.mp3, "Nice audio");
```

###Option 2: Initialize an anonymous playlist with a default title for all
```java
    ArrayList<String> urls = new ArrayList<>();
    urls.add("http://www.example.com.br/android/Music_01.mp3");
    urls.add("http://www.example.com.br/android/Music_02.mp3");
    
    player.initAnonPlaylist(urls);
```

###Option 3: Initialize an playlist with a custom title for all
```java
    ArrayList<String> urls = new ArrayList<>();
    urls.add("http://www.example.com.br/android/Music_01.mp3");
    urls.add("http://www.example.com.br/android/Music_02.mp3");
    
    player.initWithTitlePlaylist(urls, "Awesome music");
```

###Call the notification player where you want.
```java
    player.createNotification(); // default icon
```
OR
```java
    player.createNotification(R.drawable.myIcon); // Your icon resource
```

## TODO LIST##

* [ ] Support others audio formats.
