# TP1 - Dependency Injection

This workspace contains two Maven modules that illustrate dependency injection approaches in Java.

## Modules

- `dependency_injection`: manual wiring, reflection-based wiring, and Spring wiring.
- `mini-framework`: a small XML-based IoC container prototype.

## dependency_injection

### Key entry points

- `com.enset.pres.PresStatique`: manual (static) wiring.
- `com.enset.pres.PresDynamique`: reflection-based wiring using `config.txt`.
- `com.enset.pres.PresSpringXML`: Spring XML wiring using `applicationContext.xml`.
- `com.enset.pres.PresSpringAnnotation`: Spring annotation-based wiring by scanning `com.enset`.

### Run

From `tp1-injection-dependances/dependency_injection`:

```bash
mvn -q -DskipTests package

# Static
mvn -q -DskipTests exec:java -Dexec.mainClass=com.enset.pres.PresStatique

# Dynamic (uses config.txt)
mvn -q -DskipTests exec:java -Dexec.mainClass=com.enset.pres.PresDynamique

# Spring XML
mvn -q -DskipTests exec:java -Dexec.mainClass=com.enset.pres.PresSpringXML

# Spring annotations
mvn -q -DskipTests exec:java -Dexec.mainClass=com.enset.pres.PresSpringAnnotation
```

If you do not have the Maven exec plugin configured, run the classes from your IDE instead.

### Configuration

- `config.txt` contains the class names used by `PresDynamique`.
- `src/main/resources/applicationContext.xml` defines Spring beans for the XML example.

## mini-framework

### Configuration

- `src/main/resources/config.xml` defines beans and their wiring for the mini IoC container.

### Run

From `tp1-injection-dependances/mini-framework`:

```bash
mvn -q -DskipTests package
```

Then run the relevant main class from your IDE (the main class depends on the specific exercise).

---

**Author**: Saad AIT SAIDOU-ALI  
**Email**: saadaitsaidouali@gmail.com  
**Repository**: https://github.com/saadaitsaid26/tp1-injection-dependances.git  
**Last Updated**: May 2026