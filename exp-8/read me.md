# 🕵️‍♀️ Ex.No.8 — Detect Hidden Data in Images Using StegExpose

---

## 🧭 Aim

To detect hidden data in image files using **StegExpose**, a steganography analysis tool.

---

## 🧩 Description

**StegExpose** is a Java-based forensic tool that identifies potential hidden data in images. It analyzes the **statistical properties** of image files to estimate a “suspect score,” helping investigators determine whether steganography is likely present.

The higher the suspect score, the more probable it is that hidden data exists.

---

## ⚙️ Prerequisites

Before starting, ensure the following software and files are prepared:

### 🪄 Software Requirements

1. **Java Development Kit (JDK 8 or higher)**
   StegExpose is Java-based, so `java` and `javac` must be installed.

   **Windows:**

   ```bash
   choco install openjdk
   ```

   **Ubuntu/Linux:**

   ```bash
   sudo apt update
   sudo apt install default-jdk
   ```

   **macOS:**

   ```bash
   brew install openjdk
   ```

   ✅ Verify installation:

   ```bash
   java -version
   javac -version
   ```

2. **Apache Commons Math Library**

   * Required dependency: `commons-math3-3.1.1.jar`
   * 📥 Download from: `https://archive.apache.org/dist/commons/math/binaries/commons-math3-3.1.1-bin.zip`

3. **StegExpose Source Code**

   * 📥 Clone or download from GitHub: `https://github.com/b3dk7/StegExpose`

   ```bash
   git clone https://github.com/b3dk7/StegExpose.git
   ```

### 🧰 Environment Setup

Place all files in a single working directory (e.g., `C:\StegExpose\`) and navigate there using Command Prompt (Windows) or Terminal (Linux/macOS):

```bash
cd C:\StegExpose-master
```

---

## 🧱 Step 1 — Compile the Source Code

Compile the Java files with the required dependency:

```bash
javac -cp commons-math3-3.1.1.jar -source 1.8 -target 1.8 *.java
```

![WhatsApp Image 2025-10-26 at 23 22 10_0148747c](https://github.com/user-attachments/assets/7b1b3c3a-2fce-4c03-a3df-a8b587582a5b)


💡 Note: Ignore warnings like `RSAnalysis.java uses unchecked or unsafe operations`. Compilation is successful if `.class` files are generated.

---

## 📦 Step 2 — Create the Executable JAR
By using Notepad
Create a file named `manifest.mf` in the same folder:

```
Main-Class: StegExpose
```
![WhatsApp Image 2025-10-26 at 23 22 55_b76bc861](https://github.com/user-attachments/assets/4baed3fc-593d-45ec-bad7-5ff56e567606)


Build the JAR:

```bash
jar cfm StegExpose.jar manifest.mf *.class
```

<img width="1478" height="96" alt="{32B41693-9868-4C22-A6F4-82C8DEDF50A2}" src="https://github.com/user-attachments/assets/294a780e-4fdf-463c-a34e-3fcea45cef52" />


✅ You now have `StegExpose.jar` ready to use.

---

## ▶️ Step 3 — Run StegExpose

```bash
java -jar StegExpose.jar "C:\Users\Sai Kumar\StegExpose\testFolder"
```

---

## 📊 Step 4 — Example Output


| Hidden Bytes   | Meaning                             |
| -------------- | ----------------------------------- |
| < 10,000       | Likely clean (no hidden data)       |
| 10,000–100,000 | Possibly contains hidden data       |
| > 100,000      | Highly likely steganography present |

---

## 🧠 Step 5 — Analyze and Verify Results

The tool lists images with potential hidden data and estimates the approximate size. Further validation can be done using tools such as:

* StegSolve
* OpenStego
* zsteg
* Binwalk

---

## 📁 Optional — Export Results Automatically

Generate a results file for easier review:

```bash
java -jar StegExpose.jar "C:\Users\Sai Kumar\StegExpose\testFolder" fast 0.3 results.csv



## 🏁 Conclusion

* ✅ Successfully compiled and executed StegExpose
* ✅ Detected images containing potential hidden data
* ✅ Interpreted results and exported findings

Hidden data in image files was successfully detected using StegExpose. 🕵️‍♂️💡
