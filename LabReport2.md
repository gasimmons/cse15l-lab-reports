# Lab Report 2 - Servers and SSH Keys

**Part 1**
Code for the String Server implementation:
![image](https://github.com/gasimmons/cse15l-lab-reports/blob/main/Screenshot%202023-10-22%20at%2010.00.11%20AM.png)

First Instance of /add-message:
![image](https://github.com/gasimmons/cse15l-lab-reports/blob/main/FirstAddMessage.png)

This instance of /add-message calls the method handleRequest. The relevant argument for this method is the url. Within the url, the /add-message is important for saying what command is being used, and the string part following s= is important for identifying what /add-message is going to add. Implementing URLHandler is necessary in making this class function. Within the StringHandler class, List<String> messages, will change as more string messages are added to it.

Second Instance of /add-message:
![image](https://github.com/gasimmons/cse15l-lab-reports/blob/main/SecondAddMessage.png)
This instance of /add-message also calls the method handleRequest. The relevant argument for this method is the url. Within the url, the /add-message is important for saying what command is being used, and the string part following s= is important for identifying what /add-message is going to add. Implementing URLHandler is necessary in making this class function. Within the StringHandler class, List<String> messages, will change as more string messages are added to it.


**Part 2**

Path to Private Key:
![image](https://github.com/gasimmons/cse15l-lab-reports/blob/main/PrivateKey.png)

Path to Public Key:
![image](https://github.com/gasimmons/cse15l-lab-reports/blob/main/PublicKey.png)

IENG6 Login Without a Password:
![iamge](https://github.com/gasimmons/cse15l-lab-reports/blob/main/NoPasswordSSH.png)

**Part 3**

This week I learned a lot about http requests alongside starting both a local and remote server. I had known about remote access to computers, like with the UCSD super computer, but this was the first time I had learned the ssh command used to access these computers. Also the basic understanding of URLs to be able to use commands like /add-message, or /increment were brand new to me, and interesting to see work.
