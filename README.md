# Task2_ABSA_Assessment
Maven & Jenkins with Selenium: Complete Tutorial
http://www.guru99.com/maven-jenkins-with-selenium-complete-tutorial.html

Step1) In Eclipse IDE, select Help | Install New Software from Eclipse Main Menu.

Step 2) On the Install dialog, select Work with and m2e plugin as shown in the following screenshot:

http://cdn.guru99.com/images/5-2015/050115_1023_MavenJenkin1.png

Step 3)Click on Next button and finish installation.

Configure Eclipse with Maven

With m2e plugin is installed, we now need create Maven project.

Step 1) In Eclipse IDE, create a new project by selecting File | New | Other from Eclipse menu.

Step 2) On the New dialog, select Maven | Maven Project and click Next

http://cdn.guru99.com/images/5-2015/050115_1023_MavenJenkin2.png

Step 3) On the New Maven Project dialog select the Create a simple project and click Next

http://cdn.guru99.com/images/5-2015/050115_1023_MavenJenkin3.jpg

Step 4) Enter WebdriverTest in Group Id: and Artifact Id: and click finish

http://cdn.guru99.com/images/5-2015/050115_1023_MavenJenkin4.jpg

Step 5) Eclipse will create WebdriverTest with following structure:

http://cdn.guru99.com/images/5-2015/050115_1023_MavenJenkin5.jpg

Step 6) Right-click on JRE System Library and select the Properties option from the menu.

http://cdn.guru99.com/images/5-2015/050115_1023_MavenJenkin6.jpg

On the Properties for JRE System Library dialog box, make sure Workspace default JRE is selected and click OK

http://cdn.guru99.com/images/5-2015/050115_1023_MavenJenkin7.jpg

Step 7). Select pom.xml from Project Explorer..

http://cdn.guru99.com/images/5-2015/050115_1023_MavenJenkin8.jpg

pom.xml file will Open in Editor section

http://cdn.guru99.com/images/5-2015/050115_1023_MavenJenkin9.jpg

Step 8).Add the Selenium and TestNG dependencies to pom.xml in the node:

         <dependencies>           
        <dependency>              
            <groupId>org.seleniumhq.selenium</groupId>                              
            <artifactId>selenium-java</artifactId>                              
            <version>2.45.0</version>                               
        </dependency>             
        <dependency>              
            <groupId>org.testng</groupId>                               
            <artifactId>testng</artifactId>                             
            <version>6.8</version>                              
            <scope>test</scope>                                     
       </dependency> 

<dependency>
  		<groupId>org.apache.maven.plugins</groupId>
  		<artifactId>maven-compiler-plugin</artifactId>
  		<version>3.8.0</version>
  		<type>maven-plugin</type>
  	</dependency>
  	<dependency>
  		<groupId>org.apache.maven.plugins</groupId>
  		<artifactId>maven-dependency-plugin</artifactId>
  		<version>3.1.1</version>
  		<type>maven-plugin</type>
  	</dependency>
  	
  	<!-- https://mvnrepository.com/artifact/org.apache.poi/poi -->
<dependency>
    <groupId>org.apache.poi</groupId>
    <artifactId>poi</artifactId>
    <version>4.0.0</version>
</dependency>
  	<!-- https://mvnrepository.com/artifact/org.apache.poi/poi-ooxml -->
<dependency>
    <groupId>org.apache.poi</groupId>
    <artifactId>poi-ooxml</artifactId>
    <version>4.0.0</version>
</dependency>


  	<dependency>
  		<groupId>commons-collections</groupId>
  		<artifactId>commons-collections</artifactId>
  		<version>3.2.2</version>
  	</dependency>
  </dependencies>  
           

Step 9) Create a New TestNG Class. Enter Package name as "Assessment2" and "TaskTwo" in the Name: textbox and click on the Finish button as shown in the following screenshot:

Step 10). Eclipse will create the NewTest class:

Step 11) Add another package by right clicking on the name of the fisrt package "Assessment2";

Step 12) add your excel file that contain data by Right-click on the new package and select paste then click ok. Eclipse will create the excel file which which you will use to parameterize:


Update the project and make sure that file appears in the tree Package Explorer (right click on the project - Refresh).

Step 13) Now you need to run test through this testng.xml.

So, go to the Run Configurations and create a new launch TestNG, select the project and field Suite as testng.xml and click Run

http://cdn.guru99.com/images/5-2015/050115_1023_MavenJenkin14.jpg

Make sure that build finished successfully.

Step 14). Additionally, we need to add as showed above in this document:

maven-compiler-plugin
maven-surefire-plugin
testng.xml
to pom.xml.

The maven-surefire-plugin is used to configure and execute tests. Here plugin is used to configure the testing.xml for TestNG test and generate test reports.

The maven-compiler-plugin is used to help in compiling the code and using the particular JDK version for compilation. Add all dependencies in the following code snippet, to pom.xml in the node:

Step 15) To run the tests in the Maven lifecycle, Right-click on the WebdriverTest and select Run As | Maven test. Maven will execute test from the project.

Make sure that build finished successfully.

Read more in the source link

After step 15, test it:

Go to the project directory and run mvn test
Check it:

mvn clean install

At this time, I can make a jar executable file by run mvn install but it can't run with the test classes.

Workaround:

In Eclipse

Right click our project
Export
Runnable JAR file
Package required libraries into generated JAR
Copy our App.jar and testng.xml to aonother machine and run

java -jar App.jar
