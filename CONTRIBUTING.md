# building forktune

if you want to contribute, you actually need to know what you are doing. don't submit a pr if you don't understand coroutines, and if you put ui logic inside the audio service, i will close your pr without leaving a comment.

## what you need
- android studio ladybug (2024.2.1) or newer.
- jdk 17. 
- android sdk api 34+.
- basic reading comprehension.

## the stack
- kotlin. don't write java here.
- jetpack compose. know how state hoisting works.
- media3 for the audio engine.
- room and retrofit.
- clean architecture. ui, domain, and data layers are separate. keep them that way.

## how to build
1. `git clone https://github.com/theyh4t3-ashlxy/ForkTune.git` (or whatever you renamed the fork to)
2. if you need discord rich presence, put your keys in `local.properties`.
3. open it in android studio and let gradle do its thing.

build commands:
- `./gradlew assembleDebug` (to test your broken code)
- `./gradlew assembleRelease` (to build the apk)
- `./gradlew clean` (run this when gradle inevitably corrupts its own cache)

## before you open a pr
run `./gradlew ktlintCheck` and `./gradlew lintDebug`. if your code fails linting, your pr gets ignored. test your stuff.

## troubleshooting
if gradle throws a `GC overhead limit exceeded` error, your computer is weak. give gradle more ram in `gradle.properties` (`org.gradle.jvmargs=-Xmx4g`).

if the compose compiler fails, you probably messed up the kotlin version mismatch. fix it in the version catalog.
