# 📝 JWebNote – Java Swing App Running in Browser (via CheerpJ)

JWebNote is a simple Java Swing notes application that runs directly inside the browser using CheerpJ 3.0.  
The goal of this project is to demonstrate how traditional Java desktop applications can be modernized and executed on the web without rewriting them.

---

## 🚀 Inspiration
Many companies still depend on legacy Java Swing applications that are hard to distribute, maintain, and run on modern systems. Rewriting them into JavaScript/React takes huge effort.

CheerpJ solves this by allowing original Java bytecode (JAR files) to run inside the browser.  
This project is a minimal working example showing that your existing Java application can run on the web instantly.

---

## 📌 What It Does
- Loads a Java Swing notes application from a `.jar` file  
- Runs it inside Chrome/Safari/Firefox without Java installed  
- Uses CheerpJ WebAssembly runtime  
- Works fully client-side  
- Demonstrates UI rendering and file operations in the browser  

---

## 🛠️ How We Built It

### 1. **Java Swing Application**
A simple Java Swing UI was created with:
- `JFrame` (main window)  
- `JTextArea` (typing notes)  
- `JMenu` (File → Save / Load)  
- A `Main` class to run the app  

The application is packaged as `JWebNote.jar` and placed inside:

