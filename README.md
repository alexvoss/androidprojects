# Android Notes

These notes serve as an aide memoir for some of the finer details of
developing for Android in Kotlin and for the tooling involved. They
are written to complement reading [Android Studio 4.1 Development
Essentials (Kotlin
Edition)](https://www.packtpub.com/mobile/android-studio-4-1-development-essentials-kotlin-edition),
the book I am going by. All page references are to this book and this
edition.

Note that there are [errata](https://www.ebookfrenzy.com/errata/as41kotlin.html)
for the book. Also, there is a page for the [source code](https://www.ebookfrenzy.com/retail/as41kotlin/index.php).

Where necessary, I complement what is in the book with material from
around the web. First stop, of course, is always the [Android
developer pages](https://developer.android.com/).

## Installation

Installing [Android Developer
Studio](https://developer.android.com/studio/index.html) is pretty
straightforward, especially for someone who has already used IntelliJ.
One small complication is the process of installing and managing the
necessary Android SDKs, which I will describe below.

One note for users of Ubuntu: installing Android Studio via `snap` is
trivial but it does mean that `snap` will control when updates are
installed. You may or may not want this.

One thing to (probably) do on a machine with enough memory is to
increase the amount of memory available to Android Studio. On Linux,
go to `File > Settings > Appearance & Behavior > System Settings >
Memory Settings` and change the IDE heap size to something more
generous than the default 2GB.

### Android SDKs

The downloading and installation of the SDKs is managed by Android
Studio itself but it is up to you do decide which ones should be
installed. I went with the SDK version 11.

In addition to the SDK, a number of developer will be needed. These
are in the `SDK Tools` tab of the `Android SDK` settings. I added
`Google Play services` and `Layout Inspector image server for APIs
29-30` as recommended (p.7).

Also, you may want to make the commandline tools the chosen SDK
contains available on your commandline, which involves modifications
(p.8) to your `.bashrc` - or a local file. I keep my local adaptations
under version control in `~/avoss/config/dot.bash_local`. There, I
added:

```
export PATH=$PATH:/home/avoss/Android/Sdk/platform-tools:/home/avoss/Android/Sdk/tools:/home/avoss/Android/Sdk/tools/bin
```

*Note*: unfortunately, some of the command names may clash with other
tools installed. It remains to be seen if this becomes a problem.
 
## Mixed Platform Development

In addition to the Android app, I am interested in developing a
library that can be used on Android but also in iOS and desktop
operating systems. Android Studio does not support this. So, is the
right longer-term plan to use IntelliJ with the Android plugin(s)
installed?


## Keyboard Shortcuts

[Keyboard
shortcuts](https://developer.android.com/studio/intro/keyboard-shortcuts)
do make life easier...

| Shortcut | Description                                   |
|:---------|:----------------------------------------------|
| `Ctrl-B` | Goto XML, e.g., when in propterty entry field |
