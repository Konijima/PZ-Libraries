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
This step will take some time (a couple minutes), it will decompile, annotate and create everything we need to start making mods.<br>
It will run these tasks in this order <pre>zomboidJar, decompileZomboid, annotateZomboid, compileZomboid, zomboidLuaJar</pre>
When everything is complete you should see
<pre>
BUILD SUCCESSFUL in 217ms
1 actionable task: 1 executed
2:06:28 PM: Execution finished.
</pre>
</details>

---

# - Sources Organising

<details>
<summary><b>1) The stuff that we want</b></summary>
So first of all, there is a couple things that we will need.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_stuffWeWant.png?raw=true" /><br>
<hr>
<b>build > generated > sources</b><br>
This directory contains both the java and lua source code. We don't need it but we might want it to do quick search using any search tools that we prefer.<br>
<hr>
<b>lib</b><br>
This directory contains the 3 jar files that we will need to get the full power out of IntelliJ while developping mods.
</details>

<details>
<summary><b>2) Create a directory to keep it organized</b></summary>
Anywhere in your computer, create a directory named <b>zomboid-decompiled</b>.<br>
In that directory create a new directory named with the current version of the game.<br><br>
Copy the 3 jar files into that new directory and optionally copy the <i>build/generated/sources</i> directory.<br>
You can rename the files to append the version for later.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_organize.png?raw=true" />
</details>

---

# - Setup a new/existing Project Zomboid Mod


---
