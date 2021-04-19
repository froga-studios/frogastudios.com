### Dalek API
[Daleks](https://github.com/froga-studios/daleks) contains a built-in API for creating custom Daleks, or Arm Attachments.

** WARNING: DALEKS IS HEAVILY INDEV, THIS IS SUBJECT TO CHANGE **


**Gradle**
Adding [Daleks](https://github.com/froga-studios/daleks) to your mod's "build.gradle"
```gradle
repositories {
	maven {
		url 'https://jitpack.io'
	}
	
	// Daleks will eventually have compat with Galacticraft. As of now, only the api for Galacticraft is released. This maven is needed to download the api.
	maven {
		url 'https://maven.galacticraft.dev'
	}
}

dependencies {
	modImplementation  'com.github.froga-studios:daleks:release-tag'
}
```
releases can be found [here](https://github.com/froga-studios/daleks/releases) or [here](https://jitpack.io/#froga-studios/daleks)

*Jitpack may not download on the first try! (Looking into getting a maven)*

