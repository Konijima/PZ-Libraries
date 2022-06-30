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
Select <b>File > New > Project...</b><br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_createNewProject.png?raw=true" /><br>
</details>

<details>
<summary><b>2) Setup the new project</b></summary>
We will install Capsid in this new project to get the jar libraries and decompiled source.<br>
So first, select <b>Groovy</b> & <b>Gradle</b>.
Then make sure to use Java 17, it should be default when installing IntelliJ.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_createNewProject_groovygradle.png?raw=true" /><br>
</details>

<details>
<summary><b>3) Installing Capsid with build.gradle</b></summary>
Once the project is set, it should automatically open <b>build.gradle</b>.<br>
Add this line to the plugins table <pre>id 'io.pzstorm.capsid' version '0.4.2'</pre><br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_createNewProject_addCapsid.png?raw=true" /><br>
Then click on the Load Gradle Icon or press <b>Ctrl + Shift + O</b> to apply the changes.
</details>

---

# - Setup CAPSID

<details>
<summary><b>1) Expand the graddle tab</b></summary>
Click on the graddle tab on the right side of the window.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_createNewProject_expandgradletab.png?raw=true" /><br>
</details>

<details>
<summary><b>2) Create Run Configurations</b></summary>
Expand the <b>Tasks > build setup</b> in the tree view.<br>
Double click <b>createRunConfigurations</b> task to execute it.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_createNewProject_createRunConfiguration.png?raw=true" /><br>
</details>

<details>
<summary><b>3) Enter path to game installation directory</b></summary>
During the create run configuration you will be prompt to enter the game installation directory.<br>Find and paste the full path to where the game is installed on your machine.<br>This should be the same directory that contains the executable to run the game.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_setGameInstallDir.png?raw=true" /><br>
Then press enter and wait for the task to complete.
<pre>BUILD SUCCESSFUL in 9s
2 actionable tasks: 2 executed
1:50:45 PM: Execution finished 'createRunConfigurations'.</pre>
In the case that you made a mistake, you can delete the file <b>local.properties</b> and run the task again.
</details>

<details>
<summary><b>4) Run Setup Workspace config</b></summary>
Select the new configuration <b>setupWorkspace</b> created from the previous step then Run it.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_createNewProject_setupWorkspace.png?raw=true" /><br>
This step will take some time, it will decompile, annotate and create everything we need to start making mods.
</details>

---

# - Sources Organising


---

# - Setup a new/existing Project Zomboid Mod


---
