## java_project-1-Hotel Management System
# Hotel Management System

This is a JAVA application which is a hotel management system.

## How to Use
- Use Windows
- Open src/Students/Credentials.java
- Edit the sqlPassword to match the password of sql in your system
- Run dist/Result

## Entity Relationship Diagram

![img](ERD.png)

## Implementation

### About the Framework:

Swing is a GUI widget toolkit for Java. It is part of Oracle’s Java Foundation Classes (JFC) – an API for providing a graphical user interface (GUI) for Java programs. Swing API is set of extensible GUI Components to ease developer’s life to create JAVA based Front End/ GUI Applications. It is built upon top of AWT API and acts as replacement of AWT API as it has almost every control corresponding to AWT controls.

### Database Used:

This project uses MySQL as its database. MySQL is an open source relational database management system (RDBMS). MySQL is free and open-source software under the terms of the GNU General Public License, and is also available under a variety of proprietary licenses. MySQL runs on virtually all platforms, including Linux, UNIX and Windows. Although it can be used in a wide range of applications, MySQL is most often associated with web applications and online publishing.

### Connecting with the Database:

`try{`  
`Class.forName("com.mysql.jdbc.Driver");`              
`Connection con;`  
`con=DriverManager.getConnection("JDBC:mysql://localhost:3306/mysql","root",Credentials.sqlPassword);`  
`Statement stmt;`  
`stmt = con.createStatement();`  
`stmt.executeUpdate("USE hotelsystem");`  
`stmt.executeUpdate("insert into staff(name,contact,aadhar,username,password,work)`  
`values('"+name+"','"+contact+"','"+aadhar+"','"+usr+"','"+pass+"','"+work+"');");`  
`JOptionPane.showMessageDialog(frame, "Staff Added");`  
`new MainScreen().setVisible(true);`  
`this.setVisible(false);`  
`        }`  
`catch(  Exception e){`  
`System.out.println(“Exception: “+e);`  
`}`  

Here, JDBC is used to connect the program with the database. The JDBC standard defines an application program interface (API) that Java programs can use to connect to database servers. The word JDBC stands for Java Database Connectivity.
  
Each database product that supports JDBC provides a JDBC driver that must be dynamically loaded in order to access the database from Java. This is done by invoking Class.forName with one argument specifying a concrete class implementing the java.sql.Driver interface. This interface provides for the translation of product-independent JDBC calls into the product-specific calls needed by the specific database management system being used. The driver is available in a .jar file at vendor Web sites and should be placed within the classpath so that the Java compiler can access it.  
  
The Java program must import java.sql.*, which contains the interface definitions for the functionality provided by JDBC. The first step in accessing a database from a Java program is to open a connection to the database. This step is required to select which database to use, here mysql. Only after opening a connection can a Java program execute SQL statements. A connection is opened using the getConnection method of the DriverManager class (within java.sql). This method takes three parameters.  
  
- The first parameter to the getConnection call is a string that specifies the URL, or machine name, where the server runs (here, mysql://localhost:3306/mysql), along with possibly some other information such as the protocol to be used to communicate with the database, the port number the database system uses for communication, and the specific database on the server to be used.  
- The second parameter to getConnection is a database user identifier, which is a string.  
- The third parameter is a password, which is also a string and is stored in Credentials.java file.  
  
Once a database connection is open, the program can use it to send SQL statements to the database system for execution. This is done via an instance of the class Statement. To execute a statement, we invoke either the executeQuery method or the executeUpdate method, depending on whether the SQL statement is a query (and, thus, returns a result set) or non-query statement such as update, insert, delete, create table, etc. 
































## java_project-2-calculator
java internship in code clause project 2 is calculator
## Calculator
```bash
Very basic calculator application created by Java Swing.
```
#### Screenshots

![screenshots](https://github.com/Akash-Deep-Das/java_project-2-/blob/master/Screenshots/Screenshot.jpg)

#### Requirements 🔧
```
-Java version 8 or higher.
-Installation 
-Press the Fork button (located on the top right corner of the page) to save copy of this project on your account.
```



> Download the repository files (project) from the download section or clone this project by typing in the bash the following command: git (https://github.com/Akash-Deep-Das/java_project-2-/new/master?readme=1)

































## java intern Golden project 

Docs to PDF Converter
=====================

**(I'm not maintaining this code as I neither have personal resources nor am I still using this project. I'll be happy to oblige if you have any pull requests or even if you wish to be a co-maintainer.)**
```
![word to pdf](https://github.com/Akash-Deep-Das/java_project-2-/blob/master/docs-to-pdf-converter-master/image%20convert.jpg)

A standalone Java library/command line tool that converts DOC, DOCX, PPT, PPTX and ODT documents to pdf files. (Requires JRE 7)

The v1.7 release has not been updated for about 2 years although it seems quite reliable for me. In response to an [issue request](https://github.com/yeokm1/docs-to-pdf-converter/issues/1) to update the libraries, I have done so with the new v1.8. I now use Maven to managed the libraries in the pom.xml file.

I have not tested v1.8 much so if you face any issues, you can still use v1.7 in the Releases section.
````
![word to pdf convert](https://github.com/Akash-Deep-Das/java_project-2-/blob/master/docs-to-pdf-converter-master.jpg)

# Table of content

  + [Why?](#why)
  + [Command Line Usage](#command-line-usage)
  + [Parameters](#parameters)
  + [Library Usage](#library-usage)
  + [Caveats and technical details](#caveats-and-technical-details)
    - [DOC](#doc)
    - [DOCX](#docx)
    - [PPT and PPTX](#ppt-and-pptx)
    - [ODT](#odt)
  + [Main Libraries](#main-libraries)
* [Compiling the code](#compiling-the-code)

### Why?  
I wanted a simple program that can convert Microsoft Office documents to PDF but without dependencies like LibreOffice or expensive proprietary solutions. Seeing as how code and libraries to convert each individual format is scattered around the web, I decided to combine all those solutions into one single program. Along the way, I decided to add ODT support as well since I encountered the code too.

### Command Line Usage:  

```
java -jar doc-converter.jar -type "type" -input "path" -output "path" -verbose
java -jar doc-converter.jar -input test.doc
java -jar doc-converter.jar -i test.ppt -o ~\output.pdf
java -jar doc-converter.jar -i ~\no-extension-file -o ~\output.pdf -t docx
```

### Parameters:  
```
-inputPath (-i, -in, -input) "path" : specifies a path for the input file

-outputPath (-o, -out, -output) "path" : specifies a path for the output PDF, use input file directory and name.pdf if not specified (Optional)

-type (-t) [DOC | DOCX | PPT | PPTX | ODT] : Specifies doc converter. Leave blank to let program infer via file  extension (Optional)

-verbose (-v) : To view intermediate processing messages. (Optional)
```

### Library Usage:  

1. Drop the jar into your lib folder and add to build path.  
2. Choose the converter of your choice, they are named DocToPDFConverter, DocxToPDFConverter, PptToPDFConverter, PptxToPDFConverter and OdtToPDFConverter.  
3. Instantiate with 4 parameters  
   - InputStream `inStream`: Document source stream to be converted  
   - OutputStream `outStream`: Document output stream  
   - boolean `showMessages`: Whether to show intermediate processing messages to Standard Out (stdout)  
   - boolean `closeStreamsWhenComplete`: Whether to close input and output streams when complete  
4. Call the "convert()" method and wait.  


### Caveats and technical details:  
This tool relies on Apache POI, xdocreport, docx4j and odfdom libraries. They are not 100% reliable and the output format may not always be what you desire.


#### DOC:
Generally ok but takes some time to convert.. I notice that after conversion, the paragraph spacing tends to increase affecting your page layout. Conversion is done using docx4j to convert DOC to DOCX then to PDF.(Cannot use xdocreport once the DOCX data is obtained as the intermediate data structure is docx4j specific.)

#### DOCX:
Very good results. Fast conversion too.  Conversion is done using xdocreport library as it seems faster and more accurate than docx4j.

#### PPT and PPTX:
Resulting file is a PDF comprising of a PNG embedded in each page. Should be good enough for printing. This is the limitation of the Apache POI and docx4j libraries.

#### ODT:
Quality and speed as good as DOCX. Conversion is done using odfdom of the Apache ODF Toolkit.

### Main Libraries  
Apache POI:  https://poi.apache.org/  
xdocreport: http://code.google.com/p/xdocreport/  
docx4j: http://www.docx4java.org/  
odfdom: https://incubator.apache.org/odftoolkit/odfdom/  
and others...  

## Compiling the code

### I just want the jar

```bash
# If you don't already have Maven in your Mac
brew install maven
mvn clean package
```

The output jar file can be found in the `target` folder.

### Development
I'm using Eclipse Mars IDE Java EE with the M2Eclipse plugin. Simply create a workspace and import my project into it. Let Maven do its work in downloading all the necessary dependencies. Once everything is downloaded, you should be able to run the MainClass.

More details can be found in the [Wiki section](https://github.com/yeokm1/docs-to-pdf-converter/wiki/Setting-up-your-IDE-to-compile-the-project).

The MIT License (MIT)
Copyright (c) 2013-2014 Yeo Kheng Meng

## Contributing 💡

If you want to contribute to this project and make it better with new ideas, your pull request is very welcomed. If you find any issue just put it in the repository issue section.


Thank You!
