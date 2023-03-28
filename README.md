This repository exists to make my life easier.
It basically will setup checkerframework for you, if you like.

One thing to note is though, that this will add my personal maven repository under the `<dependencyManagement>` and `<repositories>` tag.
So you probably do not want to use this package if you want to publish your projects.
This might change in the future!


If you want the checkerframework in a project, just add the following to your `pom.xml` file in the build plugin section (assuming that projects already has this project in its parent chain):

```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-compiler-plugin</artifactId>
</plugin>
```

If you use lombok you also need the following in the `pom.xml` build plugins section:
```xml
<plugin>
    <groupId>org.projectlombok</groupId>
    <artifactId>lombok-maven-plugin</artifactId>
</plugin>
```
and the following lombok properties set (defined in [lombok.config](lombok.config)):
```lombok.config
lombok.addLombokGeneratedAnnotation = true
lombok.addNullAnnotations = checkerframework
```
