# Install java and maven

## Install java

### Download and install jdk

Go to https://adoptium.net/ and follow the links. _Or go directly to [release selection](https://adoptium.net/temurin/releases/?os=mac&arch=aarch64)_  

Once downloaded, untar them and install into `/Library/Java/JavaVirtualMachines`. 

Folder tree should look like this:
```
/Library/Java/JavaVirtualMachines  
 /jdk-19.0.2+7  
 /jdk-21.0.5+11  
```

### Add java alias

In order to easily switch between java version, I add this in my ~/.profile

**/!\ 2020 November, Macos Big Sur breaking changes:** since the upgrade, /usr/libexec/java_home -v xx will always return the content of the JAVA_HOME if already set. 
So I set it as last step and add un unset on each alias.

```bash
# Java Settings (list available versions : /usr/libexec/java_home -V)
#export JAVA_8_HOME=$(/usr/libexec/java_home -v1.8)
#export JAVA_11_HOME=$(/usr/libexec/java_home -v11)
#export JAVA_14_HOME=$(/usr/libexec/java_home -v14)
#export JAVA_17_HOME=$(/usr/libexec/java_home -v17)
export JAVA_19_HOME=$(/usr/libexec/java_home -v19)
export JAVA_21_HOME=$(/usr/libexec/java_home -v21)
export JAVA_HOME=$(/usr/libexec/java_home)
#alias java8='unset JAVA_HOME; export JAVA_HOME=$JAVA_8_HOME'
#alias java11='unset JAVA_HOME; export JAVA_HOME=$JAVA_11_HOME'
#alias java14='unset JAVA_HOME; export JAVA_HOME=$JAVA_14_HOME'
#alias java17='unset JAVA_HOME; export JAVA_HOME=$JAVA_17_HOME'
alias java19='unset JAVA_HOME; export JAVA_HOME=$JAVA_19_HOME'
alias java21='unset JAVA_HOME; export JAVA_HOME=$JAVA_21_HOME'
# default to Java 21
java21
```
To switch according the version you installed, you need to type java8 or java11, etc...

## Install maven

```bash
brew  install maven
mvn --version
```

### Maven Settings

If you have some personal open source projects, do not forget to add your settings:

```XML
<server>
    <id>ossrh</id>
    <username>lusoalex</username>
    <password>XXXXXXXX</password>
</server>

<server>
    <id>sonatype-nexus-staging</id>
    <username>8WG0k+aR</username>
    <password>XXXXXXXX</password>
</server>

<server>
    <id>sonatype-nexus-snapshots</id>
    <username>8WG0k+aR</username>
    <password>XXXXXXXX</password>
</server>
```

```XML
  <profiles>
    <!--Allow to download snapshot (sonatype and spring snapshot repository)-->
    <profile>
      <id>allow-snapshots</id>
      <activation>
        <activeByDefault>true</activeByDefault>
      </activation>
      <repositories>
        <repository>
          <id>snapshots-repo</id>
          <url>https://oss.sonatype.org/content/repositories/snapshots</url>
          <releases><enabled>false</enabled></releases>
          <snapshots><enabled>true</enabled></snapshots>
        </repository>
        <repository>
          <id>repository.spring.snapshot</id>
          <name>Spring Snapshot Repository</name>
          <url>https://repo.spring.io/snapshot</url>
          <releases><enabled>false</enabled></releases>
          <snapshots><enabled>true</enabled></snapshots>
        </repository>
      </repositories>
      <pluginRepositories>
        <pluginRepository>
          <id>spring-snapshots</id>
          <url>https://repo.spring.io/snapshot</url>
        </pluginRepository>
      </pluginRepositories>
    </profile>

    <!--Allow to download spring release candidate from the spring repository-->
    <profile>
      <id>spring-milestones</id>
      <activation>
        <activeByDefault>false</activeByDefault>
      </activation>
      <repositories>
        <repository>
          <id>repository.spring.milestone</id>
          <name>Spring Milestone Repository</name>
          <url>https://repo.spring.io/milestone</url>
        </repository>
      </repositories>
      <pluginRepositories>
        <pluginRepository>
          <id>spring-milestones</id>
          <url>https://repo.spring.io/milestone</url>
        </pluginRepository>
      </pluginRepositories>
    </profile>
  </profiles>
```
