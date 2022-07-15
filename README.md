# The mobile cheat sheet

Today, make a mobile app can lost many people when they search how to build, test, maintaint and distribute theire app.

This repository aim to give some keys in some kind of cheat sheet to help people taking decisions about different aspects of an app.

## The global steps

First, make sure to understand the followin steps. Each mobile app development follows this steps.


```mermaid
flowchart TD
    entry(Make frontend app)
    
    toolkit(choose your toolkit)

    versioning(choose your source versioning platform)

    cicd(Choose your CI/CD)

    deploy(Deploy your app)

    prod(Congrats, you are in production !)

    entry --> toolkit
    
    toolkit --> versioning
    
    versioning --> cicd
    
    cicd --> deploy
    
    deploy --> prod
    
```

## The dev toolkit

This is maybe the most important choice. Select the correct dev toolkit regarding several criterias.

If your don't know which one to choose, start by asking yourself :

* do I need to deploy my app on several platforms or only one ?
* is my target audience only on android, ios, web ?
* do I require the most moble experience ?
* will I use the device's capabilities like accelerometer, vibrations, NFC, bluetooth ?
* do I want the same experience over the all platform or not ?
* can I code my app once per platform ? do I want it ?

If you need to deploy on several systems or platforms, you may need an cross-platform toolkit.

If you only need to mak an Android or IOS app without any possibility to change target platform later, just use the native toolkit for better experience.

If you need to use the device's capabilities, consider using a cross platform that can make it easily or the native toolkit if you can code your app once per platform.


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

## The pattern

### MVC

```mermaid
sequenceDiagram
    participant user
    participant controller
    participant model
    participant view
    user->>controller: Uses
    controller->>model: Manipulates
    model->>view: Updates
    view-->>user: Sees
```

### MVP
```mermaid
sequenceDiagram
    participant view
    participant presenter
    participant model

    view->>presenter: User action
    presenter->>model: Update model
    model-->>presenter: Model changed
    presenter-->>view: Update UI
    
```

### MVVM
```mermaid
sequenceDiagram
    participant view
    participant viewmodel
    participant model

    view-->viewmodel: Data binding
    viewmodel->>model: Changes
    model-->>viewmodel: Notify
    
```

### The clean architecture
```mermaid
sequenceDiagram
    participant ui
    participant presenter
    participant usecase
    participant entity
    participant repository
    participant datasource
    participant model

    ui->>presenter: user action
    presenter->>usecase: uses
    usecase-->entity: manipulates
    usecase->>repository: call
    repository->>datasource: fetch data model
    datasource-->model: manipulates
    datasource-->>repository: return data model
    repository-->>usecase: return entity
    usecase-->>presenter: return entity
    presenter-->>ui: update ui
    
```

### The onion architecture
```mermaid
sequenceDiagram
    participant presentation
    participant application
    participant domain

    presentation->>application: user action
    application->>domain: call business logic
    activate domain
    domain-->>application: return data
    deactivate domain
    application-->>presentation: updates ui
```

## The CI/CD

```mermaid
flowchart LR
   
    cicd(Choose your CI/CD)
    
    githubaction(Github Actions)
    gitlabci(Gitlab CI)
    fastlane(Fastlane)
    codemagic(Codemagic)
    circleci(Circle CI)
    travisci(Travis CI)
    jenkins(Jenkins)

    cicd --> githubaction
    cicd --> gitlabci
    cicd --> fastlane
    cicd --> codemagic
    cicd --> circleci
    cicd --> travisci
    cicd --> jenkins

```

## The deployment

```mermaid
flowchart LR
    deploy(Deploy your app)
    playstore(Google Play Store)
    appstore(App Store Connect)
    firebasehosting(Firebase hosting)
    githubpages(Github Pages)
    snap(Ubuntu Snap)
    microsoftstore(Microsoft store)

    deploy --> playstore
    deploy --> appstore
    deploy --> firebasehosting
    deploy --> githubpages
    deploy --> snap
    deploy --> microsoftstore

```