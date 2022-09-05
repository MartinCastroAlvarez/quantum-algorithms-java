# Quantum Computing
Quantum Algorithms with Java and Strange

![wall](./wallpaper.jpg)

## References

- [Strange](https://github.com/redfx-quantum/strange)
- [StrangeFX](https://github.com/redfx-quantum/strangefx)
- [Quantum Computing samples in Java](https://github.com/johanvos/quantumjava)
- [How to Install Maven on Linux (Ubuntu)](https://www.digitalocean.com/community/tutorials/install-maven-linux-ubuntu)
- [Quantum Logic Gate](https://en.wikipedia.org/wiki/Quantum_logic_gate)

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

## Quantum Algorithms

### Quantum Superposition

Putting a Qubit into superposition using a `Hadarmard` gate.

![wall](./images/hadamard.png)

```bash
mvn clean javafx:run --quiet --file superposition.xml
```
```bash
Qubit | Probability: 0.4999999701976776, Mesured: 0
```

![wall](./images/superposition.png)

### Quantum Entanglement

Entangling 2 Qubits using a `CNOT` gate.

![wall](./images/cnot.png)

```bash
mvn clean javafx:run --quiet --file entanglement.xml
```
```bash
Qubit | Probability: 0.0, Mesured: 0
Qubit | Probability: 0.0, Mesured: 0
```

![wall](./images/entanglement.png)

### Bell State

Entangling 2 Qubits in superposition to create a Bell state using a `Hadamard` gate and a `CNOT` gate.

```bash
mvn clean javafx:run --quiet --file bell.xml
```

This results on both Qubits being either 0 or 1 50% of the time.

```bash
Qubit | Probability: 0.4999999701976776, Mesured: 0
Qubit | Probability: 0.4999999701976776, Mesured: 0
```
```bash
Qubit | Probability: 0.4999999701976776, Mesured: 1
Qubit | Probability: 0.4999999701976776, Mesured: l
```

![wall](./images/bell.png)

Adding an additional `X` gate to the second Qubit.

![wall](./images/xgate.png)

```bash
mvn clean javafx:run --quiet --file bell2.xml
```

It causes the Qubits to be measures as either 0 and 1 or 1 and 0 50% of the time.

```bash
Qubit | Probability: 0.4999999701976776, Mesured: 0
Qubit | Probability: 0.4999999701976776, Mesured: 1
```
```bash
Qubit | Probability: 0.4999999701976776, Mesured: 1
Qubit | Probability: 0.4999999701976776, Mesured: 0
```

![wall](./images/bell2.png)

### Quantum Teleportation

Teleporting a Qubit from Alice to Bob by combining `Hadamard` and `CNOT` gates as well as a `CZ` gate.

![wall](./images/cz.png)

```bash
mvn clean javafx:run --quiet --file teleport.xml
```

The last Qubit is guaranteed to always be 0. That means the 0 was teleported from Alice to Bob.

```bash
Qubit | Probability: 0.4999999403953552, Mesured: 0
Qubit | Probability: 0.4999999403953552, Mesured: 1
Qubit | Probability: 0.0, Mesured: 0
```

![wall](./images/teleport.png)

Now, initializing the first Qubit to 1.

```bash
mvn clean javafx:run --quiet --file teleport1.xml
```

Now, the value 1 has been teleported from Alice to Bob.

```bash
Qubit | Probability: 0.4999999403953552, Mesured: 1
Qubit | Probability: 0.4999999403953552, Mesured: 0
Qubit | Probability: 0.9999998807907104, Mesured: 1
```

![wall](./images/teleport1.png)

Now, initializing the first Qubit to 53%.

```bash
mvn clean javafx:run --quiet --file teleport53.xml
```

Now, the value 0.53 has been teleported from Alice to Bob after applying the formula `1 - 0.53 * 0.53 = 0.719`.

```bash
Qubit | Probability: 0.4999999403953552, Mesured: 1
Qubit | Probability: 0.4999999403953552, Mesured: 0
Qubit | Probability: 0.7190999388694763, Mesured: 0
```

![wall](./images/teleport53.png)

### Quantum Network

Creating a network of Qubits by concatenating multiple Quantum Teleporters.

```bash
mvn clean javafx:run --quiet --file network.xml
```

The message `0.21` is teleported from Alice to Bob across a larger distance after applying the formula `1 - 0.21 * 0.21 = 0.9558`

```bash
Qubit | Probability: 0.4999998528510332, Mesured: 1
Qubit | Probability: 0.4999998528510332, Mesured: 1
Qubit | Probability: 0.4999998528510332, Mesured: 1
Qubit | Probability: 0.4999998528510332, Mesured: 1
Qubit | Probability: 0.4999998528510332, Mesured: 1
Qubit | Probability: 0.4999998528510332, Mesured: 1
Qubit | Probability: 0.4999998528510332, Mesured: 1
Qubit | Probability: 0.4999998528510332, Mesured: 1
Qubit | Probability: 0.4999998528510332, Mesured: 0
Qubit | Probability: 0.4999998528510332, Mesured: 0
Qubit | Probability: 0.955899715423584, Mesured: 1
```

![wall](./images/network.png)

### Quantum Inverter

Inverting the state of 2 Qubits by applying 3 consecutive `CNOT` gates.

```bash
mvn clean javafx:run --quiet --file inverter.xml
```

The message `0.2` and `0.5` have been inverted after applying the formulas: `1 - 0.2 * 0.2 = 0.96` and `1 - 0.5 * 0.5 = 0.75`.

```bash
Qubit | Probability: 0.9599999040365219, Mesured: 1
Qubit | Probability: 0.7499999087303877, Mesured: 1
```

![wall](./images/inverter.png)

The inverter can be used to teleport a Qubit while only applying the `CNOT` and `CZ` gates to contiguous gates so that they can be easily calculated mathematically.

![wall](./images/sgate.png)

```bash
mvn clean javafx:run --quiet --file swap.xml
```

The message `0.r1` is teleported from Alice to Bob after swapping the state of the first 2 Qubits.

```bash
Qubit | Probability: 0.5, Mesured: 0
Qubit | Probability: 0.5, Mesured: 0
Qubit | Probability: 0.8319000005722046, Mesured: 1
```

![wall](./images/swap.png)
