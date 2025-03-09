#### [Go Back ↩](../README.md)

## Java Handbook

### File Handling in Java

- In Java, file handling is done with the help of the File class of the java.io package.

- Java uses streams to accomplish I/O operations. A stream is a sequence of data. Java supports two types of streams:

    1. **Byte Streams**: Handle data in raw binary format. It is mainly involved with byte data.
    2. **Character Streams**: Manage data in the form of characters. It is mainly involved with character data.

<img src="https://images.tpointtech.com/core/images/file-operations-in-java.png">

### Java File Class Methods:

| **Method Name**       | **Description**                                 | **Return Type** |
| --------------------- | ----------------------------------------------- | --------------- |
| **canRead()**         | It tests whether the file is readable or not.   | Boolean         |
| **canWrite()**        | It tests whether the file is writable or not.   | Boolean         |
| **createNewFile()**   | It creates an empty file.                       | Boolean         |
| **delete()**          | It deletes a file.                              | Boolean         |
| **exists()**          | It tests whether the file exists or not.        | Boolean         |
| **length()**          | Returns the size of the file in bytes.          | Long            |
| **getName()**         | Returns the name of the file.                   | String          |
| **list()**            | Returns an array of the files in the directory. | String[]        |
| **mkdir()**           | Creates a new directory.                        | Boolean         |
| **getAbsolutePath()** | Returns the absolute pathname of the file.      | String          |


### File Operations in Java:

1. **Creating a new file** - To create a file in Java, you can use the `createNewFile()` method.

```java
import java.io.File;  // Import the File class
import java.io.IOException;  // Import the IOException class to handle errors

public class CreateFile {
  public static void main(String[] args) {
    try {
      File myObj = new File("filename.txt");
      if (myObj.createNewFile()) {
        System.out.println("File created: " + myObj.getName());
      } else {
        System.out.println("File already exists.");
      }
    } catch (IOException e) {
      System.out.println("An error occurred.");
      e.printStackTrace();
    }
  }
}
```

2. **Writing in a file** - The `FileWriter` class along with its `write()` method is used in order to write some text to the file.

```java
import java.io.FileWriter;   // Import the FileWriter class
import java.io.IOException;  // Import the IOException class to handle errors

public class WriteToFile {
  public static void main(String[] args) {
    try {
      FileWriter myWriter = new FileWriter("filename.txt");
      myWriter.write("Files in Java might be tricky, but it is fun enough!");
      myWriter.close();
      System.out.println("Successfully wrote to the file.");
    } catch (IOException e) {
      System.out.println("An error occurred.");
      e.printStackTrace();
    }
  }
}
```

3. **Reading an existing file** - We use the `Scanner` class in order to read contents from a file.

```java
import java.io.File;  // Import the File class
import java.io.FileNotFoundException;  // Import this class to handle errors
import java.util.Scanner; // Import the Scanner class to read text files

public class ReadFile {
  public static void main(String[] args) {
    try {
      File myObj = new File("filename.txt");
      Scanner myReader = new Scanner(myObj);
      while (myReader.hasNextLine()) {
        String data = myReader.nextLine();
        System.out.println(data);
      }
      myReader.close();
    } catch (FileNotFoundException e) {
      System.out.println("An error occurred.");
      e.printStackTrace();
    }
  }
}
```

4. **Getting File Information** - To get more information about a file, use any of the `File` methods.

```java
import java.io.File;  // Import the File class

public class GetFileInfo { 
  public static void main(String[] args) {
    File myObj = new File("filename.txt");
    if (myObj.exists()) {
      System.out.println("File name: " + myObj.getName());
      System.out.println("Absolute path: " + myObj.getAbsolutePath());
      System.out.println("Writeable: " + myObj.canWrite());
      System.out.println("Readable " + myObj.canRead());
      System.out.println("File size in bytes " + myObj.length());
    } else {
      System.out.println("The file does not exist.");
    }
  }
}
```
5. **Deleting a file** - To delete a file in Java, use the `delete()` method.

```java
import java.io.File;  // Import the File class

public class DeleteFile {
  public static void main(String[] args) { 
    File myObj = new File("filename.txt"); 
    if (myObj.delete()) { 
      System.out.println("Deleted the file: " + myObj.getName());
    } else {
      System.out.println("Failed to delete the file.");
    } 
  } 
}
```

--- 
- **YouTube Tutorial** → [Detailed explanation(Java File Handling)](https://youtu.be/b35mlSPOlJg?si=0JcQwxBi7oYHFgc7) || [Short explanation (Java File Handling)](https://youtu.be/Vy2l3lGAb2I?si=raLEXEGk7IGAbXcI)