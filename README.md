# ☕ Task 8: Java Maven Build Job in Jenkins

This project demonstrates how to set up a **Jenkins Freestyle job** to build a simple Java application using **Apache Maven**, all running inside a Docker-based Jenkins container.

---

## 🎯 Objective

To configure Jenkins to build a Java Maven application and show a successful build output using `mvn clean package`.

---

## 🛠 Tools & Technologies Used

- Jenkins (Docker container)
- Apache Maven (3.8.6)
- Java JDK 8
- Linux (Ubuntu)
- Freestyle Jenkins Job
- Git (optional)
- Local project directory

---

## 📁 Project Structure

```
hello-java-maven/
├── pom.xml
└── src/
    └── main/
        └── java/
            └── HelloWorld.java
```

---

## 🧩 Step-by-Step Setup

### ✅ 1. Create Java Project

**HelloWorld.java**
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, Jenkins + Maven!");
    }
}
```

**pom.xml**
```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" 
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
         http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.example</groupId>
    <artifactId>hello</artifactId>
    <version>1.0</version>
    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.8.1</version>
                <configuration>
                    <source>1.8</source>
                    <target>1.8</target>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>
```

---

### ✅ 2. Run Jenkins in Docker

Mount your local Java project folder into Jenkins container:

```bash
docker run -d --name jenkins-maven \
  -p 8080:8080 \
  -v jenkins_home:/var/jenkins_home \
  -v /home/ubuntu/hello-java-maven:/mnt/hello-java-maven \
  jenkins/jenkins:lts
```

---

### ✅ 3. Configure Jenkins Job

1. Open Jenkins at `http://localhost:8080`
2. Go to `Manage Jenkins → Global Tool Configuration`
   - Add Maven (e.g. Maven 3.8.6)
3. Create new **Freestyle project**
   - Name: `hello-java-maven-Build`
   - Build Step: **Invoke top-level Maven targets**
   - Goals:  
     ```
     -f /mnt/hello-java-maven/pom.xml clean package
     ```

---

### ✅ 4. Run and Validate

- Click **Build Now**
- Check **Console Output**
- Confirm it shows:
  ```
  [INFO] BUILD SUCCESS
  ```

---

## 📸 Screenshots

- Jenkins build console showing `BUILD SUCCESS`
- Jenkins job configuration with Maven goal
- Project structure on local machine

---

## ✅ Outcome

Successfully automated a Java Maven build using Jenkins via a Docker container. This task taught the basics of continuous integration with Jenkins and Maven.

---

## 🔗 Resources

- [Jenkins](https://www.jenkins.io/)
- [Apache Maven](https://maven.apache.org/)
- [Docker Hub - Jenkins](https://hub.docker.com/r/jenkins/jenkins)
