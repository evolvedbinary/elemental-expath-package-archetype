# Maven Archetype for EXPath Packages in Elemental

[![Build Status](https://dl.circleci.com/status-badge/img/gh/evolvedbinary/elemental-expath-package-archetype/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/evolvedbinary/elemental-expath-package-archetype/tree/main)
[![License](https://img.shields.io/badge/license-BSL%201.1-blue.svg)](https://mariadb.com/bsl11/)
[![Maven Central](https://img.shields.io/maven-central/v/xyz.elemental.expath/elemental-expath-package-archetype?logo=apachemaven&label=maven+central&color=green)](https://central.sonatype.com/search?namespace=xyz.elemental.expath)
[![Slack](https://img.shields.io/badge/elemental-slack-56b6f8.svg?logo=slack)](https://join.slack.com/t/elemental-xyz/shared_invite/zt-34r53san4-fzHCV0vDT9lYSMChUdn3cQ)
[![Code of Conduct](https://img.shields.io/badge/code%20of%20conduct-contributor%20covenant-5e0d73.svg?logo=contributorcovenant)](https://www.contributor-covenant.org/version/2/1/code_of_conduct.html)

This [archetype](https://maven.apache.org/guides/introduction/introduction-to-archetypes.html) can be used to generate a skeleton project for building an EXPath Package that is deployable to [Elemental](https://github.com/evolvedbinary/elemental).

Whilst this repository contains the source code for the archetype, you do not need that to just use the archetype.
The archetype has been deployed to Maven Central and will be downloaded for you when you invoke it.

## Usage
From your Terminal or Command Line, change into a directory on your system where you keep your projects,
and then run Maven with this archetype to create a Maven Project that you can use as a skeleton for your new EXPath Package.

```bash
$ cd my-projects
$ mvn archetype:generate \
    -DarchetypeGroupId=xyz.elemental.expath \
    -DarchetypeArtifactId=elemental-expath-package-archetype \
    -DarchetypeVersion=1.0.0
```

Maven will then prompt you for a `groupId`, `artifactId`, `version`, and `package` for your project.
You need only specify the `groupId` and `artifactId`, for the others you may accept the defaults (or modify them as you wish).

* `groupId` is similar to a Java package name. If you are going to publish your XAR publicly it should be some sub-coordinate of a domain name that you have responsibility for supplied in reverse order notation. For example, if your company is "*My Organisation Ltd*" you might own the domain name `myorganisation.com`, you might decide that a suitable subdomain for your EXPath Package might be `app.myorganisation.com`. **Note:** this subdomain does not have to be able to be de-referenced.

* `artifactId` is just a simple name without spaces for the App itself. Together the `groupId:appId` coordinate must be unique.

* `version` the version number of your package. In Maven terms `-SNAPSHOT` are development versions. Your first version should always be `1.0.0-SNAPSHOT`, whereby the first release subsequently becomes `1.0.0`.  


e.g.:

```bash
Define value for property 'groupId': : com.myorganisation.app
Define value for property 'artifactId': : my-app1
Define value for property 'version':  1.0.0-SNAPSHOT: : 
Define value for property 'package':  com.myorganisation.app: : 
Confirm properties configuration:
groupId: com.myorganisation.app
artifactId: my-app1
version: 1.0.0-SNAPSHOT
package: com.myorganisation.app
 Y: : y
```

After running this process, a new directory will have been created for you that matches the `artifactId` name that you specified above.

NOTE: The project has been set up to expect to be under Git version control. If you are not already in a Git repository, you should then create one:

```bash
$ cd my-app1
$ git init
$ git add .gitignore pom.xml src/ xar-assembly.xml xquery-license-style.xml LICENSE README.md
$ git commit -m "Start of my EXPath Package"
```

You should now consult the `README.md` of your `my-app1` for further instructions and documentation.
