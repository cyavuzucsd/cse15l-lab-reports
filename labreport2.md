# Lab Report 2 - Servers and Bugs (Week 3)

These are the screenshots and explanations for what I did for lab 3. 

---

## Part 1: String Server

The image below is my code for the StringServer. I used what I learned from the second week of lab to write this code.

<img width="753" alt="Screenshot 2023-01-29 at 2 33 30 PM" src="https://user-images.githubusercontent.com/122561946/215359730-0c3ba12a-68dd-4bfd-9c79-77320c5b2200.png">

Now here is the first example of using /add-message:

<img width="753" alt="Screenshot 2023-01-29 at 2 33 30 PM" src="https://user-images.githubusercontent.com/122561946/215359830-83de88c1-ea74-475b-a34a-2ca44649d10c.png">

In the image above the only method that is called is the handleRequest method which takes the URL in as an input. In the method there is an if statement which determines what to do based on what is put into the URL which is the important argument. Using the URL argument the method decides what to do and what message to display. If it is the first time entry into the server it will display "No words added". However for this usage of /add-message it uses the second condition which is only employed when /add-message is used. 

Immediately when this condition is called the system prints out which path we are in and it says in the terminal that we are in the /add-message path. Afterwards this method splits the URl from the = sign. Once split there are two elements in the array. The method assigns the second element of the array into the newString variable which becomes "Part 1 of lab report 2". Then the variable returnAll, which is a string, gets added to with the newString and a new line to fit the format required for the next calls of /add-message. Then the returnAll variable which now has "Part 1 of lab report 2" + "\n" is returned to be displayed on the web server. 

The image below is what happens when /add-message is used again:

<img width="538" alt="Screenshot 2023-01-29 at 2 48 49 PM" src="https://user-images.githubusercontent.com/122561946/215360298-fe2c726a-33c6-4f51-8f3e-205c57f2b402.png">

In the image above the only method that is called is the handleRequest method which takes the URL in as an input. In the method there is an if statement which determines what to do based on what is put into the URL which is the important argument. The argument and its importance does not change from the first time /add-message is called. 

Immediately when this condition is called the system prints out which path we are in and it says in the terminal that we are in the /add-message path. Afterwards this method splits the URl from the = sign. Once split there are two elements in the array again. The method assigns the second element of the array into the newString variable which becomes "Second line". Then the variable returnAll gets added to with the newString and a new line to fit the format required for the next calls of /add-message. Then the returnAll variable which now has ""Part 1 of lab report 2" + "\n" + "Second line"" is returned to be displayed on the web server. In the second calling of /add-message all the variables are changed but only returnAll is added upon since it needs to display the previous messages as well. 

## Part 2: Bugs from lab

## Part 3: What I have learned from week 2 or week 3

One thing I learned that I did not know before was creating web servers. Before this class and especially beofre week 2 I thought that it was very complex and difficult to create web servers. I thought it required multiple people and a domain you had to buy along with extra costs to maintain the server. I did not know that we could create the server in our local host. After learning that it was not that difficult another thing that surprised me was the code required for it. I thought it would be way longer and I did not think that I had the knowledge to understand what was going on. Through the lab and revising now I know how to create a server class and use a URL interface. I think these new skills will be essential for me in the future. I want to go into software development and I think it will a good foundation for me as well. One thing I am proud of is for example in this lab report I could create the /add-message web server. If I am able to do these simple tasks, I feel like the momentum will allow meto create bigger projects. 
