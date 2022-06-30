# PZ-Libraries

### Tutorial to help you setup a workspace to create Project Zomboid mods.  
- Easy Decompiling  
- Global Libraries  
- No redundancies  
- Complete Intelisense
- Easy Search Java and Lua source

---

# - Download IntelliJ IDEA Community Edition
|[Windows](https://www.jetbrains.com/idea/download/#section=windows)|[MacOS](https://www.jetbrains.com/idea/download/#section=mac)|[Linux](https://www.jetbrains.com/idea/download/#section=linux)|
|---|---|---|

---

# - Install IntelliJ IDEA
Install the IDE on your computer. Find resource online how to install on your specific OS if needed.

---

# - Install CAPSID
<details>
    <summary><b>1) Create a new project</b></summary>
    Select <b>File > New > Project...</b>
    <img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_createNewProject.png?raw=true" />
</details>

<details>
    <summary><b>2) Setup the new project</b></summary>
    We will install Capsid in this new project to get the jar libraries and decompiled source.<br>
    So first, select <b>Groovy</b> & <b>Gradle</b>.
    Then make sure to use Java 17, it should be default when installing IntelliJ.
    <img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_createNewProject_groovygradle.png?raw=true" />
</details>

<details>
    <summary><b>3) Installing Capsid with build.gradle</b></summary>
    Once the project is set, it should automatically open <b>build.gradle</b>.<br>
    Add this line to the plugins table <pre>id 'io.pzstorm.capsid' version '0.4.2'</pre>.
    <img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_createNewProject_addCapsid.png?raw=true" />
    Then click on the Load Gradle Icon or press <b>Ctrl + Shift + O</b> to apply the changes.
</details>

---

# - Setup CAPSID

<details>
    <summary><b>1) Expand the graddle tab</b></summary>
    Click on the graddle tab on the right side of the window.
    <img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_createNewProject_expandgradletab.png?raw=true" />
</details>

<details>
    <summary><b>2) Create Run Configurations</b></summary>
    Expand the <b>Tasks > build setup</b> in the tree view.<br>
    Double click <b>createRunConfigurations</b> task to execute it.
    <img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_createNewProject_createRunConfiguration.png?raw=true" />

</details>

---

# - Sources Organising


---

# - Setup a new/existing Project Zomboid Mod


---
