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
```

### Add java alias

In order to easily switch between java version, I add this in my ~/.profile

```bash
# Java Settings
export JAVA_HOME=$(/usr/libexec/java_home)
export JAVA_8_HOME=$(/usr/libexec/java_home -v1.8)
export JAVA_11_HOME=$(/usr/libexec/java_home -v11)
alias java8='export JAVA_HOME=$JAVA_8_HOME'
alias java11='export JAVA_HOME=$JAVA_11_HOME'
# default to Java 11
java11
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
