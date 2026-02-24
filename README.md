# TASK-8-Run-a-Simple-Java-Maven-Build-Job-in-Jenkins


## 📌 Project Overview

This project demonstrates how to configure Jenkins to build a simple Java application using Maven.

The goal of this task was to understand the basics of Continuous Integration (CI) by automating the Java build process using Jenkins running inside Docker.

---

## 🛠️ Tools & Technologies Used

- Jenkins (Docker container)
- Docker
- Java (JDK 11)
- Maven (Configured inside Jenkins)
- Git & GitHub
- AWS EC2 (Ubuntu)

---

## 📂 Project Structure

```
hello-java-maven/
│
├── pom.xml
└── src/
    └── main/
        └── java/
            └── HelloWorld.java
```

---

## 💻 Java Application Code

### HelloWorld.java

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, Jenkins + Maven!");
    }
}
```

---

## 📦 Maven Configuration (pom.xml)

This file defines:
- Project metadata
- Java version
- Maven compiler plugin

It allows Maven to compile and package the application.

---

## ⚙️ Jenkins Setup Process

### 1️⃣ Installed Docker on EC2
```bash
sudo apt update
sudo apt install docker.io -y
```

### 2️⃣ Ran Jenkins Container
```bash
docker run -d -p 8080:8080 --name jenkins --restart=always jenkins/jenkins:lts
```

### 3️⃣ Accessed Jenkins
```
http://<EC2-Public-IP>:8080
```

### 4️⃣ Installed Maven Integration Plugin

Manage Jenkins → Plugins → Installed Maven Integration Plugin

### 5️⃣ Configured Maven Tool

Manage Jenkins → Tools → Add Maven

- Name: Maven-3
- Install automatically ✔

---

## 🏗️ Jenkins Job Configuration

### Job Type:
Freestyle Project

### Build Step:
Invoke top-level Maven targets

### Goal:
```
clean package
```

---

## 🔄 What Happens During Build?

When "Build Now" is clicked:

1. Jenkins reads `pom.xml`
2. Maven runs `clean package`
3. Java files are compiled
4. A `.jar` file is generated inside `target/` folder
5. Console displays `BUILD SUCCESS`

---

## ✅ Successful Build Output

Console Output shows:

```
[INFO] BUILD SUCCESS
```

---

## 🎯 Key Concepts Learned

- What is Jenkins and how it works
- What is Continuous Integration (CI)
- How Maven builds Java projects
- How Jenkins integrates with build tools
- Docker-based Jenkins setup
- Jenkins workspace concept
- Debugging build failures

---

## 📸 Screenshots Included

- Jenkins Dashboard
- Maven Tool Configuration
- Job Configuration
- Console Output (BUILD SUCCESS)


## 👨‍💻 Author

**Nityam Raj**

GitHub: https://github.com/Nityam0

---
