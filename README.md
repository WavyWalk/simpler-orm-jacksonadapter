# What's it?
A Jackson adapter for simpler-orm json serialization.
# how to install
It's not on the repo engines, so just clone it in your project PARENT folder.
In your project's settings.graddle add:
```groovy
include ':simpler-orm-jackson-adapter'  
project(':simpler-orm-jackson-adapter').projectDir = new File(settingsDir, "../simpler-orm-jackson-adapter")
```
In build.graddle:
```groovy
compile project(':simpler-orm-jackson-adapter')
```
# How to use with simpler-orm
When building `SimplerOrmDependenciesProvider`:
```kotlin

SimplerOrmDependenciesManager.provider = SimplerOrmDependenciesProvider(
            jsonObjectMapper = JacksonObjectMapperAdapter(), //Pass HERE
            defaultDslContext = dsl 
        )

```
```kotlin
SimplerDependencyManager.provider = SimplerDependenciesProvider(
            //servletRequestParametersWrapper =  ServletRequestParametersWrapper(
            //    jsonParametersParser = JacksonParametersParser(ObjectMapper())
            //),
            //assetsPathProvider = AssetsPathProvider(publicFolderConfig),
            templateProcessor = FreemarkerTemplateProcessor(configuration) //pass here/ configuration is the configuration object that your suposed to build on your own
        )
```

That's it. It does nothing on it's own