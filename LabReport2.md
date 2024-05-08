Part 1: ChatServer
---
![Image](ChatServer_Code(smaller).png) <br>
![Image](ChatServer-1.png) <br>
This command for the URL calls the `public String handleRequest` method within the `handler` class. This method separates the different parts of the URL path into `String[] parametersArray` to assign the values "jpolitz" to `String user` and "yash" to `String message` based on the index of the string. The `String chatLog` field is then updated with the `message` and `user` formatted as "user: message \n". <br>
![Image](ChatServer-2.png) <br>
This next command also calls the `public String handleRequest` method in the `handler` class in same way to update a message to the webpage through `chatLog`. This separates the different parts of the URL path into `String[] parametersArray`, assigning values "yash" to `String user` and "How are you" to `String message`. However the difference between the two commands is that the previous command already added a message to `chatLog`, which causes the new message to be added onto a new line and displayed onto the webpage as seen in the screenshot. <br>

Part 2: ieng login
---
![Image](Part2-1.png) <br>
![Image](Part2-2.png) <br>
![Image](Part2-3.png) <br>


Part 3: Information learned
---
Something I learned from this lab was that we could open a seperate Visual Studio Code environment for our `ssh` machine. It was also interesting and helpful to learn about the different parts of a browser URL and how it can command code with certain methods.
