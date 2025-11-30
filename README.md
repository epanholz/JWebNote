📝 JWebNote – Java Swing App Running in Browser (via CheerpJ)

JWebNote is a simple Java Swing notes application that runs directly inside the browser using CheerpJ 3.0.
The goal of this project is to demonstrate how traditional Java desktop applications can be modernized and executed on the web without rewriting them.

🚀 Inspiration

Many companies still depend on legacy Java Swing desktop applications that are difficult to distribute, upgrade, and run on modern systems (no JDK installed, OS compatibility issues, etc.).

Rewriting these applications into JavaScript/React/Web apps takes a lot of time and money.

CheerpJ solves this by letting Java bytecode (JAR files) run inside any browser using WebAssembly — without changing a single line of Java code.

JWebNote is a minimal working example proving that your existing Java Swing app can run on the web instantly.

📌 What It Does

Loads a Java Swing notes application from a JAR file

Runs it in Chrome/Safari/Firefox without Java installed

Uses the CheerpJ WebAssembly runtime

Works fully client-side

Demonstrates Java UI rendering inside the browser

Supports simple file operations (within sandbox limits)

🛠️ How We Built It
1. Java Swing Application

A small Java Swing app was built with:

JFrame → main window

JTextArea → text input for notes

JScrollPane → scrollable text area

JMenuBar → Save + Load options

Main class to launch the UI

We packaged it as:

target/JWebNote.jar

2. HTML + CheerpJ Integration

Inside

src/main/java/org.example/index.html


We load CheerpJ:

<script src="https://cjrtnc.leaningtech.com/3.0/loader.js"></script>


Run the application:

async function runApp() {
    await cheerpjInit();
    cheerpjRunJar("/JWebNote.jar");
}


When the user clicks Run Notes App, the Java Swing window appears inside the browser.

📂 Project Structure
JWebNote/
 ├── src/
 │   └── main/
 │       ├── java/
 │       │   └── org.example/
 │       │       └── index.html
 │       └── resources/
 ├── target/
 │   └── JWebNote.jar
 ├── pom.xml
 └── README.md

▶️ How to Run the Project (Mac / Windows / Linux)
Step 1 — Build the JAR

In IntelliJ terminal:

mvn clean package


Your JAR appears here:

target/JWebNote.jar

Step 2 — Start Local Server
cd JWebNote
python3 -m http.server 8080

Step 3 — Open Browser

Go to:

http://localhost:8080/src/main/java/org.example/index.html


Click Run Notes App →
Your Java Swing UI loads inside the browser 🎉

😤 Challenges We Ran Into

Mapping desktop Java UI into a browser sandbox

Handling correct relative paths for JAR loading

CheerpJ async initialization (cheerpjInit)

Understanding browser security for file dialogs

Ensuring Maven packaging produces a runnable JAR

Getting Java GUI to behave inside HTML canvas

🏆 Accomplishments

Successfully ran a native Java Swing app inside a browser

Zero changes to Java source code

Entirely client-side execution

Clean project structure ready for Devpost

Demonstrated real-world migration of desktop apps → web apps

Proved CheerpJ is a powerful modernization tool

📚 What We Learned

How CheerpJ converts JVM bytecode → WebAssembly

Differences between JVM runtime vs browser runtime

Browser sandbox limitations for Java desktop apps

How to embed Java applications inside HTML pages

How Maven packages JARs for cross-platform usage

Basics of modernizing legacy UI using WebAssembly

🔮 What's Next for JWebNote

Add dark mode

Auto-save notes using IndexedDB

Support multiple note tabs

Deploy to GitHub Pages

Add keyboard shortcuts (Ctrl+S, Ctrl+O)

Build a PWA (makes it installable like a desktop app)

Add drag-and-drop file importing

Add cloud sync using Firebase or Supabase

🧑‍💻 Author

Anshika Singh

⭐ Conclusion

JWebNote demonstrates that even legacy Java Swing desktop applications can run seamlessly inside modern web browsers using CheerpJ — without rewriting code.

This project is a clean, simple, and practical example of how Java applications can be modernized for the web with minimal effort.
