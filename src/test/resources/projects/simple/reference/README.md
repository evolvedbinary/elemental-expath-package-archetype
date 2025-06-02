# Example EXPath Package Application for Elemental

This is a simple skeleton example application for Elemental which will be built as an EXPath Package using Maven.

You can use this as a base for your own Elemental EXPath applications or libraries.

## Contents

The application contains:
 
1. An example XQuery Library Module of user defined functions written in Java.

2. A example XQuery Library Module of user defined functions written in XQuery.

3. A simple Web landing page for the application itself.   


## Modifying the Example for your own purposes

1. By default the project is setup to place the code under an Apache 2.0 licensing scheme. You should decide if that is appropriate and if not, make the following modifications:

  1. Modify the `licenses` section in `pom.xml`.
  
  2. Override the `configuration` of the license-maven-plugin` in `pom.xml`. See: http://code.mycila.com/license-maven-plugin/
  
  3. Run `mvn license:check` and `mvn license:format` appropriately. 

2. You should modify the `pom.xml` changing at least the `groupId` and `artifactId` to coordinates that are suitable for your organisation.

3. You should modify, remove, or append to, the files in:

  * `src/main/java` for any XQuery library modules written in Java.

  * `src/main/xquery` for any XQuery library modules written in XQuery.

  * `src/main/xar-resources` for all other files that are shipped as part of your application. 

NOTE: You will also need to modify `xar-assembly.xml` to reflect any changes you make to any User Defined XQuery Library Modules (written either in Java or XQuery).

## Building

* Requirements: Java 8 (or newer) and Git.

To create an EXPath Package for your application, follow the platform specific instructions below. You will then find a `.xar` file in the `target/` sub-folder.

### macOS/Linux/Unix:

```bash
$ mvnw package
```

### Windows:

```cmd
> mvnw.cmd package
```

## Publication
If you wish, you can use the Maven Release plugin to publish your applications or libraries **publicly** to [Maven Central](https://central.sonatype.com/).

1. To be able to publish to Maven Central, you first need to signup and register to manage the `groupId` of your organisation, see: https://central.sonatype.org/register/central-portal/.

2. Assuming your local Git repository is in-sync with your remote repository, you can run the following to create a new release and publish to Maven Central:


### macOS/Linux/Unix:
    
```bash
$ mvnw release:prepare
$ mvnw release:perform
```
    
### Windows:
    
```cmd
> mvnw.cmd release:prepare
> mvnw.cmd release:perform
```

3. Finally, you need to sign-in to Maven Central Portal and approve the publication of your artefacts via this webpage: https://central.sonatype.com/publishing.
