## Issue
```
java.lang.LinkageError: Method void com.example.****.c() overrides final method in class Lq/r/s0; 
(declaration of 'com.example.*****.MyViewModel' appears in /data/app/com.mobicip.colegia.dev-xF1qRbdM6b73GynWjWqEaQ==/base.apk)
        at e.a.a.a.a.e.g.b.a(:1)
        at e.a.a.a.a.e.g.g.p(Unknown Source:8)
```
### Steps to Reproduce
  - Create a ViewModel and declare a clear() function
  - Enable `minifyEnabled` to `true` in app's `build.gradle`
  - Build and run project
  
### Fix
 Don't create a ViewModel with clear() function/method in it.
 
### Related SO Issues
  - https://stackoverflow.com/questions/58379564/java-lang-linkageerror-method-void-gamehistoryviewmodel-a-overrides-final-met
