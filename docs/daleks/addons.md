## Daleks Addons

This mod contains a built in api for creating custom dalek variants

**Adding to gradle**
```java
repositories {
  maven {  url 'https://jitpack.io'  }
  
  // Daleks will eventually have compat with Galacticraft. As of now, only the api for Galacticraft is released. This maven is needed to download the api.
  maven {  url 'https://maven.galacticraft.dev'  }
}

dependencies {
  modImplementation  'com.github.froga-studios:daleks:*REPLACE WITH RELEASE*'
```}

**Jitpack may NOT download the pom on the first try! (I will look into getting my own maven)**

Releases can be found @ either
 https://github.com/froga-studios/daleks/releases or https://jitpack.io/#froga-studios/daleks

 
**Updating your fabric.mod.json**
```json
"depends": {  "daleks":  "*REPLACE WITH RELEASE*"  }
```
**Creating your variant**
```java
public class Example implements ModInitializer {
    public static Variant MY_VARIANT;

    @Override
    public void onInitialize() {
      MY_VARIANT = Registry.register(DaleksRegistries.VARIANT, new Identifier("modid", "variant_name"), new MyVariant());
    }
}
```

```java
import io.github.froga_studios.daleks.common.variant.Variant;

public class MyVariant implements Variant {

    @Override
    public boolean canTarget(LivingEntity target) {
        return true; // attacks everything, including other daleks. by default attacks everything, but daleks & endermen
    }
}
```

**Registering a texture & model for your variant**
```java
import io.github.froga_studios.daleks.client.graphics.render.Context;

@Environment(EnvType.CLIENT)
public class ExampleClient implements ClientModInitializer {

    @Override
    public void onInitializeClient() {
        Context.register(Example.MY_VARIANT, new Identifier("modid", "textures/entity/dalek/my_variant.png"), new SkaroModel(0));
    }
}
```