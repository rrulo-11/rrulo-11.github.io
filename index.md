## Personal Information

![Raul_Pic](https://user-images.githubusercontent.com/62734127/97199679-8f40be80-17b0-11eb-980a-6df9b569acbd.png)

Hello, my name is Raul Ramirez, I come from Mexico and currently I am living in Vienna, Austria. I got a Bachelor Degree in Computer Science with concentration in Information Security from Southern New Hampshire University. 

My chief areas of expertise are:

- Hardware Integration
- Software Design and Engineering
- Data Structures and Algorithms 
- Networking
- Cybersecurity and secure coding
- Penetration testing 
- Database management
- Statistical Analysis and Data Mining
- Computational Graphics and Visualization

I have experience working with the operating systems: Windows, macOS, Linux, UNIX, Ubuntu, and Kali Linux. 

I can code with the languages: Python, Java, C, C++, UML, and SQL.  

I can work with these Software and tools: Eclipse, NetBeans, MS Visual Studio, Xcode, Raspberry Pi, Arduino, MongoDB, MySQL, Wireshark, Snort, and several Firewalls and Anti-Malware.

I can speak: English, Spanish, and German. 

Here is a code review I made for the class, "CS-499 Computer Science Capstone."
![](https://www.youtube.com/watch?v=nEl5QBWh8cA&feature=youtu.be)

 <iframe width="560" height="315" 
src="https://www.youtube.com/embed/nEl5QBWh8cA" 
frameborder="0" 
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>


Here are the narratives and the artifacts for the class, "CS-499 Computer Science Capstone." In here, one can see the requested descriptions, justifications, and the reflections. 

[CS499_FinalProject_RR.docx](https://github.com/rrulo-11/rrulo-11.github.io/files/5439760/CS499_FinalProject_RR.docx)

Here is an example of the work I can do with Java. You can check my repository in order to find more examples.

### Authentication System Source Code (Artifact)
 
```markdown
package authenticationsystem;

//Importing the libraries 
import java.util.Scanner;
import java.io.File;
import java.security.MessageDigest;

//Creating a class named AuthenticationSystem and inserting the method main along with the IOException 
public class AuthenticationSystem {
    public static void main(String[] args) throws Exception {
        //Creating the scanner object to get data from the user
        Scanner readInput = new Scanner(System.in);
        //Declaring the variables 
        int numAttempts = 0;
/* Creating the while loop that makes the system stays on the login screen until three unsuccessful attempts are made, a successful attempt is made, or user exits intentionally */
        while(true) {
            // Prompting user to input the username and password
            System.out.println("Enter username: ");
            String userName = readInput.nextLine();
            System.out.println("Enter password: ");  
            String original = readInput.nextLine();
            /* Converting the password using a message digest five (MD5) hash so the 
            credentials are checked */
            MessageDigest md = MessageDigest.getInstance("MD5");
            md.update(original.getBytes());
            byte[] digest = md.digest();
            StringBuilder sb;
            sb = new StringBuilder();
            for (byte b : digest) {
                sb.append(String.format("%02x", b & 0xff));
            }
            //Declaring the boolean to check if the authentication system is true or false
            boolean authenticationBoolean = false;
            //Creating scanner object to open identifications file
            //Checking credentials against credentials in the credentials file
            //Passing the path to the file as a parameter
            File file = new File("/Users/raulramirez/Documents/credentials.txt");
            Scanner userCredentials = new Scanner(file);
            //Creating a while loop to retrieve the credentials in the file
            while(userCredentials.hasNextLine()) {
                String fileRecords = userCredentials.nextLine();
                String columns[] = fileRecords.split("\t");               
                if(columns[0].trim().equals(userName)) {
                    //Using the hashed passwords in the file
       //Checking if the password is valid
                    if(columns[1].trim().equals(sb.toString())) { 
                    authenticationBoolean = true;
                    //Displaying the role in the file
                    //Passing the path to the files as parameters
                    Scanner roleFile = new Scanner(new File("/Users/raulramirez/Documents/"+ columns[3].trim()+ ".txt"));
                    while(roleFile.hasNextLine()) {
                        System.out.println(roleFile.nextLine());
                    }
                    break;
                    }   
                }
            }
            //Allowing user to log out 
            if(authenticationBoolean) {
                System.out.println("Are you sure you want to log out? Yes (y) No (n): ");
                String confirmLogout  = readInput.nextLine();
                //If user types (y), then exit
                if(confirmLogout.toLowerCase().charAt(0) == 'y') {
                    System.out.println("Logged out successfully. ");
                    break;
                }
                else {
                    authenticationBoolean = false;
                }
            }
            //Else if password is not valid, increment the attempts
            else {
                numAttempts++;
                //If the password is not valid after three attempt, then print the following message
                if(numAttempts == 3) {
                    System.out.println("Unable to login. The system is shutting down");
                    break;
                }
                //Else stay on the login screen until successful attempt
                else {
                    System.out.println("Please sign in again entering valid credentials!");     
                }
            }
        }
    }
}

```


Thank you very much! I really appreciate your time. 

## Looking forward to working with you!

