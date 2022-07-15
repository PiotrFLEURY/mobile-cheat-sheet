
# Toolkit language

Each toolkit can use one or several languages. Make sure to know it or to be able to learn it easily with your team.

```mermaid
flowchart LR
    android(Android)
    ios(IOS)
    flutter(Flutter)
    reactn(React native)
    kmm(Kotlin Multiplatform Mobile)
    composemulti(Compose multi platform)
    netmaui(.Net MAUI)

    objectivec(Objective C)
    swift(Swift)
    swiftui(SwiftUI)
    java(Java)
    kotlin(Kotlin)
    jetpackcompose(Kotlin Jetpack Compose)
    dart(Dart)
    javascript(Javascript)
    csharp(C#)

    
    ios --> objectivec
    ios --> swift
    ios --> swiftui

    android --> java
    android --> jetpackcompose
    android --> kotlin

    kmm --> kotlin
    composemulti --> kotlin

    flutter --> dart

    reactn --> javascript

    netmaui --> csharp

```


# Toolkit supported target platforms


## Android native

```mermaid
flowchart TD
    nativeandroid(Android native)
    
    android(Android)
    wearos(Google wear OS)
    androidtv(Android TV)
    androidforcars(Android for cars)

    nativeandroid --> android & wearos & androidtv & androidforcars

```


## IOS native

```mermaid
flowchart TD
    nativeios(IOS native)
    
    ios(IOS)
    watchos(Apple watch OS)
    applecarplay(Apple car play)
    appletv(Apple TV)

    nativeios --> ios & watchos & applecarplay & appletv

```


## Flutter

```mermaid
flowchart TD
    flutter(Flutter)
    
    android(Android)
    wearos(Google wear OS)
    androidtv(Android TV)
    androidforcars(Android for cars)
    
    ios(IOS)
    watchos(Apple watch OS)
    applecarplay(Apple car play)
    appletv(Apple TV)
    
    web(Web)
    
    desktop(desktop)
    windows(windows)
    linux(linux)
    macos(macos)
    
    iot(IOT)

    flutter --> android
    android --> wearos
    android --> androidtv
    android --> androidforcars
    
    flutter --> ios
    ios --> applecarplay
    ios --> appletv
    ios --> watchos
    
    flutter --> web

    flutter --> desktop
    desktop --> windows
    desktop --> linux
    desktop --> macos

    flutter --> iot

```


## React native

```mermaid
flowchart LR
    reactn(React native)
    
    android(Android)
    ios(IOS)
    web(Web)
    windows(windows)
    macos(macos)
    linux(linux)
    androidtv(Android TV)
    appletv(Apple TV)
    desktop(desktop)

    
    reactn --> android --> androidtv
    reactn --> ios --> appletv
    reactn --> web
    reactn --> desktop --> macos & windows & linux

```


## KMM - Kotlin Multiplatform Mobile

```mermaid
flowchart LR
    kmm(KMM)
    
    android(Android)
    ios(IOS)
    watchos(Apple watch OS)

    
    kmm --> android
    kmm --> ios --> watchos

```


## Compose multi platform

```mermaid
flowchart LR
    compose(Compose multi platform)
    
    web(Web)
    
    desktop(desktop)
    windows(windows)
    linux(linux)
    macos(macos)

    compose --> web
    compose --> desktop
    desktop --> windows & linux & macos

```


## .Net MAUI
```mermaid
flowchart LR
    netmaui(.Net MAUI)
    
    android(Android)
    ios(IOS)
    desktop(desktop)
    macos(macos)
    windows(windows)

    netmaui --> android & ios & desktop
    desktop --> macos & windows
```