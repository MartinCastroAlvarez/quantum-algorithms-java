# Quantum Computing
Quantum Algorithms with Java and Strange

![wall](./wallpaper.jpg)

## References

- [Strange](https://github.com/redfx-quantum/strange)
- [Quantum Computing samples in Java](https://github.com/johanvos/quantumjava)
- [How to Install Maven on Linux (Ubuntu)](https://www.digitalocean.com/community/tutorials/install-maven-linux-ubuntu)

## Instructions

### Installing JDK on Linux

Downloading the JDK Binaries

```bash
wget https://download.java.net/java/GA/jdk13.0.1/cec27d702aa74d5a8630c65ae61e4305/9/GPL/openjdk-13.0.1_linux-x64_bin.tar.gz
tar -xvf openjdk-13.0.1_linux-x64_bin.tar.gz
sudo mv jdk-13.0.1 /opt/
```

Setting `JAVA_HOME` and Path Environment Variables

```bash
JAVA_HOME='/opt/jdk-13.0.1'
PATH="$JAVA_HOME/bin:$PATH"
export PATH
```

Verifing the Java Installation

```bash
java -version
```

### Installing Maven on Linux

Downloading the Maven Binaries

```bash
wget https://mirrors.estointernet.in/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz
tar -xvf apache-maven-3.6.3-bin.tar.gz
sudo mv apache-maven-3.6.3 /opt/
```

Setting `M2_HOME` and Path Variables

```bash
M2_HOME='/opt/apache-maven-3.6.3'
PATH="$M2_HOME/bin:$PATH"
export PATH
```

Verifing the Maven installation

```bash
mvn -version
```

## Algorithms

### Quantum Superposition

```bash
mvn clean javafx:run --file superposition.xml
```

### Quantum Entanglement

```bash
mvn clean javafx:run --file entanglement.xml
```

### Quantum Teleportation

```bash
mvn clean javafx:run --file teleportation.xml
```
