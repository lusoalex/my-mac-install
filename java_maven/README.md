# Install java and maven

## Install java

Install newer version of adoptopenjdk

```bash
brew cask install adoptopenjdk
```

According to your needs, install previous version
```bash
brew tap AdoptOpenJDK/openjdk
brew cask install adoptopenjdk8
brew cask install adoptopenjdk11
brew cask install adoptopenjdk13
```

### Add java alias

In order to easily switch between java version, I add this in my ~/.profile

**/!\ 2020 November, Macos Big Sur breaking changes:** since the upgrade, /usr/libexec/java_home -v xx will always return the content of the JAVA_HOME if already set. So I set it as last step and add un unset on each alias.

```bash
# Java Settings
export JAVA_8_HOME=$(/usr/libexec/java_home -v1.8)
export JAVA_11_HOME=$(/usr/libexec/java_home -v11)
export JAVA_13_HOME=$(/usr/libexec/java_home -v13)
export JAVA_14_HOME=$(/usr/libexec/java_home -v14)
export JAVA_15_HOME=$(/usr/libexec/java_home -v15)
export JAVA_HOME=$(/usr/libexec/java_home)
alias java8='unset JAVA_HOME; export JAVA_HOME=$JAVA_8_HOME'
alias java11='unset JAVA_HOME; export JAVA_HOME=$JAVA_11_HOME'
alias java13='unset JAVA_HOME; export JAVA_HOME=$JAVA_13_HOME'
alias java14='unset JAVA_HOME; export JAVA_HOME=$JAVA_14_HOME'
alias java15='unset JAVA_HOME; export JAVA_HOME=$JAVA_15_HOME'
# default to Java 13
java13
```
To switch, you just need to type java8 or java11, etc...

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
    ...
    <!--Allow to download snapshot from the sonatype snapshot repository-->
    <profile>
      <id>allow-snapshots</id>
      <activation><activeByDefault>true</activeByDefault></activation>
      <repositories>
        <repository>
          <id>snapshots-repo</id>
          <url>https://oss.sonatype.org/content/repositories/snapshots</url>
          <releases><enabled>false</enabled></releases>
          <snapshots><enabled>true</enabled></snapshots>
        </repository>
      </repositories>
    </profile>
  </profiles>
```