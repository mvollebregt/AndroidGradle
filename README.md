Building an existing project
----------------------------
These are instructions for building an existing Android project using gradle.  
If you want to create a new Android project using gradle, please proceed to *Creating a new project*

### Setting the Android SDK dir
1. `cd` into the _`AndroidProject`_ folder
2. create a file called `local.properties`
3. in the file, enter your local android sdk dir:
    `sdk.dir=/path/to/sdk/dir`

### Building from gradle
1. `cd` to the root folder
2. type `gradle androidPackage` to do a complete build (including tests)
3. type `gradle androidInstall` to install the application in a device or a running emulator
4. type `gradle tasks` to see a list of all gradle tasks

### Importing into Eclipse
1. `cd` to the root folder
2. type `gradle eclipse`
3. start Eclipse
4. select File - Import - Existing Projects into Workspace
5. select the root folder containing the _AndroidProject_ and the _AndroidProjectTest_ projects
6. right click on the _AndroidProject_
7. select Android Tools - Fix Project Properties

### Setting up Eclipse test configuration
1. in the project explorer, select the _AndroidProjectTest_ project
2. select Run - Run Configurations...
3. select JUnit and click the yellow + button
4. select Test Runner - JUnit 4
4. go the the tab 'Arguments'
5. select Working directory - Other
6. select Workspace... - _AndroidProject_ and click OK
7. click Multiple launchers available - Select one...
8. choose the Eclipse JUnit Launcher (NOT the Android JUnit Test Launcher)


Creating a new project
----------------------
These are instructions for using the gradle build files from this project in a new Android project.

1. Copy the following folder structure from this project:
   * .gitignore  
   * build.gradle  
   * README.md  
   * settings.gradle  
   * _AndroidProject_  
   * _AndroidProject_/build.gradle  
   * _AndroidProjectTest_  
   * _AndroidProjectTest_/build.gradle  

2. Create a new Android project in the _AndroidProject_ folder. You can use Eclipse for this.
   * Make sure the target folder for the new Eclipse project is the _AndroidProject_ folder.
   * Do NOT create an android Test Project.

3. Follow the steps in *Setting the Android SDK dir* as described above

4. Go to the root folder (containing README.md) and type `gradle _AndroidProjectTest_:eclipse`

5. In Eclipse: import the generated existing project into the workspace
   
6. Follow the steps *Setting up Eclipse test configuration*

### Attention
* You can change the project names _AndroidProject_ and _AndroidProjectTest_ into _XXX_ and _XXX_Test.
* It is possible to use _AndroidProject_/build.gradle without the test project.
* Make sure you do NOT check in files specified in .gitignore in version control. This will cause problems.