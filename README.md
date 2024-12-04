```markdown
# Installing and Uninstalling JDK on Kali Linux WSL

This guide explains how to install and uninstall the Java Development Kit (JDK) on Kali Linux in Windows Subsystem for Linux (WSL).

---

## **1. Installing JDK**

### **Step 1: Update the System**
Run the following commands to ensure your system is up-to-date:
```bash
sudo apt update && sudo apt upgrade -y
```

### **Step 2: Install JDK**
Install the OpenJDK package using the following command:
```bash
sudo apt install openjdk-17-jdk -y
```
> **Note**: Replace `openjdk-17-jdk` with another version like `openjdk-11-jdk` or `openjdk-8-jdk` if required.

### **Step 3: Verify the Installation**
Check the Java installation by running:
```bash
java -version
```
You should see an output like:
```
openjdk version "17.x.x"...
```

Verify the Java compiler:
```bash
javac -version
```

---

## **2. Uninstalling JDK**

If you need to uninstall JDK, follow these steps:

### **Step 1: Remove the JDK Package**
Use the `apt` command to remove the JDK package:
```bash
sudo apt remove --purge openjdk-17-jdk -y
```
> Replace `openjdk-17-jdk` with the version you installed (e.g., `openjdk-11-jdk`).

### **Step 2: Clean Up Residual Files**
Remove any configuration or residual files:
```bash
sudo apt autoremove -y
sudo apt autoclean
```

### **Step 3: Verify Uninstallation**
Check if Java is completely removed:
```bash
java -version
```
If uninstalled successfully, the system will display:
```
Command 'java' not found
```

---

## **3. Setting Environment Variables (Optional)**

If you had set the `JAVA_HOME` environment variable during installation, you can remove it:

1. Open the `.bashrc` file for editing:
   ```bash
   nano ~/.bashrc
   ```
2. Remove the lines related to `JAVA_HOME`:
   ```bash
   export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
   export PATH=$JAVA_HOME/bin:$PATH
   ```
3. Save the file and apply changes:
   ```bash
   source ~/.bashrc
   ```

---

## **4. Test a Java Program (Optional)**

If you reinstalled Java, test the installation:

1. Create a Java file:
   ```bash
   nano HelloWorld.java
   ```
2. Add the following code:
   ```java
   public class HelloWorld {
       public static void main(String[] args) {
           System.out.println("Hello, World!");
       }
   }
   ```
3. Compile the program:
   ```bash
   javac HelloWorld.java
   ```
4. Run the program:
   ```bash
   java HelloWorld
   ```
   The output should be:
   ```
   Hello, World!
   ```

---

## **Conclusion**
This guide covers the steps for installing and uninstalling JDK on Kali Linux WSL. If you encounter any issues, feel free to raise an issue or ask for help!

---
