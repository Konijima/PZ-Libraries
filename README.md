# PZ-Libraries

If you have trouble with the tutorial you can contact me on discord `Konijima#9279` or **open an issue**.  
If you have **suggestion** you can **fork** and create a **pull request**.

Hopefully I made this as easy as possible to understand.

## Tutorial 

- Easy and fast source decompilation  
- Intellisense using global libraries  
- Easy source update
- Quick search Java and Lua source

<br>

# A) IntelliJ IDEA Community Edition
|[Windows](https://www.jetbrains.com/idea/download/#section=windows)|[MacOS](https://www.jetbrains.com/idea/download/#section=mac)|[Linux](https://www.jetbrains.com/idea/download/#section=linux)|
|---|---|---|

Install the IDE on your computer. Find resource online how to install on your specific OS if needed.

<br>

# B) Pre-Setup
Install Capsid and run the configuration.

<details>
<summary><b>1) Create a new project</b> (used for decompiling only)</summary>
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

<details>
<summary><b>4) Expand the gradle tab</b></summary>
Click on the gradle tab on the right side of the window.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_createNewProject_expandgradletab.png?raw=true" /><br>
</details>

<details>
<summary><b>5) Create Run Configurations</b></summary>
Expand the <b>Tasks > build setup</b> in the tree view.<br>
Double click <b>createRunConfigurations</b> task to execute it.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_createNewProject_createRunConfiguration.png?raw=true" /><br>
</details>

<details>
<summary><b>6) Enter path to game installation directory</b></summary>
During the create run configuration you will be prompt to enter the game installation directory.<br>Find and paste the full path to where the game is installed on your machine.<br>This should be the same directory that contains the executable to run the game.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_setGameInstallDir.png?raw=true" /><br>
Then press enter and wait for the task to complete.
<pre>BUILD SUCCESSFUL in 9s
2 actionable tasks: 2 executed
1:50:45 PM: Execution finished 'createRunConfigurations'.</pre>
In the case that you made a mistake, you can delete the file <b>local.properties</b> and run the task again.
</details>

<details>
<summary><b>7) Install Emmylua plugin</b></summary>
Select <b>File > Settings...</b><br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/install_emmylua_1.png?raw=true" /><br>
Then go to <b>Plugins</b> and search for <b>Emmylua</b>.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/install_emmylua_2.png?raw=true" /><br>
Install it and <a href="https://emmylua.github.io/">check the documentation to learn how it work</a>
</details>

<br>

# C) Decompiling
Let's get decompiling in a single step.

<details>
<summary><b>1) Run Setup Workspace config</b></summary>
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

<br>

# D) Versioning
Let's organise a little bit before we get to modding.

<details>
<summary><b>1) Know the stuff that you need</b></summary>
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

<br>

# E) Setup a new/existing Project Zomboid Mod
Alright we are almost there, you will be typing code soon i swear.

<details>
<summary><b>1a) Create a new mod</b></summary>
Select <b>File > New > Project...</b><br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/CreateNewMod1.png?raw=true" /><br>
Now select the zomboid local workshop directory and enter your new mod name.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/CreateNewMod2.png?raw=true" /><br>
You should now have an empty project ready to be setup.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/CreateNewMod3.png?raw=true" /><br>
You can delete the <b>src</b> directory and create your default workshop mod structure.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/CreateNewMod4.png?raw=true" /><br>
</details>

<details>
<summary><b>1b) Use an existing mod</b></summary>
Select <b>File > Open...</b><br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/ExistingMod1.png?raw=true" /><br>
Select the mod you want to open with IntelliJ and click <b>Trust Project</b> when prompted.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/ExistingMod2.png?raw=true" /><br>
Press <b>Ctrl + S</b> to save the project and you are ready for the final step.
</details>

<details>
<summary><b>2) Setup the global libraries</b> (per version)</summary>
Select <b>File > Project Structure...</b><br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/setup_libs_1.png?raw=true" /><br>
Then select <b>Platform Settings > Global Libraries</b><br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/setup_libs_2.png?raw=true" /><br>
Press the <b>+</b> icon and add both <b>zdoc-lua.jar</b> and <b>zomboid.jar</b> to your global libraries.<br>
Then select <b>zomboid.jar</b> and press the other <b>+</b> icon and add <b>zomboid-sources.jar</b>.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/setup_libs_3.png?raw=true" /><br>
</details>

<details>
<summary><b>3) Setup the mod project modules</b></summary>
Select <b>File > Project Structure...</b><br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/setup_libs_1.png?raw=true" /><br>
Then select <b>Project Settings > Modules</b> then <b>Dependencies</b> tab.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/project_modules.png?raw=true" /><br>
Add both global libraries.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/project_modules_2.png?raw=true" /><br>
Check both library boxes and apply.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/project_modules_3.png?raw=true" /><br>
You now have intellisense working in your project.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/Intelisense_1.png?raw=true" /><br>
</details>

<br>

# F) Search/Find tools
Now you can search into the source and figure for yourself how things work.

<details>
<summary><b>Search in the Java source code</b></summary>
Right-click the zomboid.jar root library in the external libraries part of your project file tree.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/search-java.png?raw=true" /><br>
Then click <b>Find in files</b><br>
</details>

<details>
<summary><b>Search in the Lua source code</b></summary>
Right-click the zdoc-lua.jar root library in the external libraries part of your project file tree.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/search-lua.png?raw=true" /><br>
Then click <b>Find in files</b><br>
</details>

<br>

# G) Project Zomboid has updated
But what if PZ updated to a new version?

<details>
<summary><b>Decompiling a new PZ version</b></summary>
Make sure your Project Zomboid game has been updated.<br>
Open the <b>capsid project</b> we used for decompiling the first time.<br>
Run the <b>setupWorkspace</b> configuration again.<br>
<img src="https://github.com/Konijima/PZ-Libraries/blob/Tutorial-v2/Images/SetupCapsid_createNewProject_setupWorkspace.png?raw=true" />
</details>

<details>
<summary><b>Updating global libraries for the new version</b></summary>
Go back to <b>section E step 2 & 3</b> and do it again with the new generated jar files.
</details>
