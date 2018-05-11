Simple example of how to build Java code on the command line

# Dependencies

Assumes you have Java 8 and Gradle installed.

## Install with [Homebrew](https://brew.sh/)

```
brew tap caskroom/versions
brew cask install java8
brew install gradle
```

# Plain (javac) Example

Based on this Stackoverflow post https://stackoverflow.com/questions/1279542/how-to-execute-a-java-class-from-the-command-line

```
mkdir javac-example
echo "public class Echo {
    public static void main (String[] arg) {

            System.out.println(String.join(" ", arg));
    }
}" > Echo.java

# build
javac Echo.java

# run
java -cp . Echo hello
```

# Gradle Example

Based on this tutorial https://spring.io/guides/gs/gradle/

```
mkdir gradle-example && cd gradle-example
mkdir -p src/main/java/hello

echo "package hello;

public class HelloWorld {
  public static void main(String[] args) {
    Greeter greeter = new Greeter();
    System.out.println(greeter.sayHello());
  }
}" > src/main/java/hello/HelloWorld.java

echo "package hello;

public class Greeter {
  public String sayHello() {
    return "Hello world!";
  }
}" > src/main/java/hello/Greeter.java

echo "apply plugin: 'java'" > build.gradle

# build
gradle build

# run 
java -cp ./build/classes/java/main hello.HelloWorld 
```

# License

Original authors rights reserved otherwise this software is free to use under the terms of the MIT License

> The path of life leads upward for the prudent 
> to keep them from going down to the realm of the dead.
> -- Proverbs 15:24

