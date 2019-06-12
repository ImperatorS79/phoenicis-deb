# Phoenicis-deb
Phoenicis is currently only proposing flatpak and "standalone" deb pacakges. Since I do not like this, mainly because of duplications and dependency problems, I decided to upload here the previous jdeb way of creating a .deb.
The generated dep will depends on openjdk-12-jre, ~~openjfx~~ (ubuntu 19.04 does not provide openjfx 12 yet) instead of packaging it inside the .deb

## How does it work ?
First clone both Phoenicis and Phoenicis-deb repository
```
git clone https://www.github.com/PhoenicisOrg/phoenicis.git
git clone https://www.github.com/ImperatorS79/phoenicis-deb.git
```
First delete `phoenicis/phoenicis-dist`directory. Then you should merge the content of `phoenicis-deb` (`phoenicis-dist`) directory inside `phoenicis` directory. You can then follow the usual way of building phoenicis:
```
cd phoenicis/
export JAVA_HOME=<path_to_java_12_home>
mvn clean package
```
The generated .deb is located in `phoenicis/phoenicis-dist/target`

Currently only Ubuntu 19.04 is supported. You can look at the source and provides PR if you want to add other deb based operating system specific configuration.

There are also maven plugins for rpm, but I did not take a look at rhem yet. 
