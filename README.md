Here’s a **ready‑to‑use `README.md`** for your GitHub repository at **[https://github.com/gayas5/gayas_simplecutomerapp](https://github.com/gayas5/gayas_simplecutomerapp)** that reflects your project structure and CI/CD setup:

```markdown
# Sabear Customer App

**Author:** Gayas  
**Package:** `com.gayas`  
**Repository:** https://github.com/gayas5/gayas_simplecutomerapp

A simple Java customer application built with **Maven** and configured for **CI/CD using Jenkins**.

---

## 📁 Project Structure

```

gayas_simplecutomerapp/
├─ src/
│  ├─ main/java/com/gayas/App.java
│  ├─ main/resources/
│  └─ test/java/com/gayas/AppTest.java
├─ pom.xml
├─ Jenkinsfile
└─ README.md

````

- **Main Class:** `App.java`  
- **Test Class:** `AppTest.java`  
- **Build Tool:** Maven  
- **CI/CD:** Jenkins Declarative Pipeline

---

## 🔧 Prerequisites

Before building or running:

- Java JDK 11 or higher  
- Maven 3.x  
- Git  
- Jenkins (with Maven and JDK configured)  

---

## 🚀 Maven Build Commands

Use these commands locally:

- **Build & compile the project**  
  ```bash
  mvn clean install
````

* **Run tests**

  ```bash
  mvn test
  ```

* **Build and skip tests**

  ```bash
  mvn clean install -DskipTests
  ```

* **Create package**

  ```bash
  mvn package
  ```

---

## 🧠 Jenkins CI/CD Pipeline

This project includes a **Declarative Jenkinsfile** that:

✔ Checks out source code from Git
✔ Builds using Maven
✔ Runs tests (optional)
✔ Packages the application
✔ Has placeholder for deployment stages

### ⚙ Build Parameters

| Parameter    | Type    | Default     | Description             |
| ------------ | ------- | ----------- | ----------------------- |
| `GIT_BRANCH` | string  | feature-1.1 | Git branch to build     |
| `ENV`        | choice  | dev         | Deployment environment  |
| `SKIP_TESTS` | boolean | false       | Skip unit tests if true |

---

## 📌 How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/gayas5/gayas_simplecutomerapp.git
   cd gayas_simplecutomerapp
   ```

2. Build with Maven:

   ```bash
   mvn clean install
   ```

3. Run tests:

   ```bash
   mvn test
   ```

4. Open Jenkins and configure a pipeline job pointing to this repo and branch.

---

## 💡 Notes

* Make sure **Maven tool** in Jenkins is named `M3`
* Make sure **JDK** in Jenkins is named `JDK11`
* Deployment logic can be added under the `Deploy` stage in the `Jenkinsfile`

---

## 📄 License

MIT License © Gayas

```

This README will show up automatically on your GitHub repo’s main page and helps others (and future you!) understand the project, how to build it, and how CI/CD works with Jenkins. :contentReference[oaicite:0]{index=0}

---

Want me to help you **add badges** (like build status, Maven Central, test coverage) to this README too? That can make it look even more professional! 🚀
::contentReference[oaicite:1]{index=1}
```
