## Issue
```
java.lang.IllegalArgumentException: Cannot serialize Kotlin type my.package.CensoredClass$CensoredSubclass. 
  Reflective serialization of Kotlin classes without using kotlin-reflect has undefined and unexpected behavior. 
  Please use KotlinJsonAdapter from the moshi-kotlin artifact or use code gen from the moshi-kotlin-codegen artifact.
```
### Steps to Reproduce
  - Add Moshi's KotlinJsonAdapterFactory to retrofit builder
  - Enable `minifyEnabled` to `true` in app's `build.gradle`
  - Build and run project
  
### Fix
 Add the below pro-guard rule to app's `build.gradle`
 ```
 -keep class kotlin.Metadata { *; }
 ```
 
### Related Git Issues
  - https://github.com/square/moshi/issues/1095
