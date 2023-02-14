# Lab Report 2 - Servers and Bugs (Week 3)

These are the screenshots and explanations for what I did for lab 3. 

---

## Part 1: String Server

The code below is my code for the StringServer. I used what I learned from the second week of lab to write this code.

```
import java.io.IOException;
import java.net.URI;

class Handler1 implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String returnAll = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("No words added");
        }else if(url.getPath().equals("/add-message")){
            System.out.println("Path: " + url.getPath());
            String[] parameters = url.getQuery().split("=");
            String newString = parameters[1];
            returnAll = returnAll + newString + "\n";
            return returnAll;
        }
        return "404 Not Found!";
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler1());
    }
}
```

Now here is the first example of using /add-message:

<img width="707" alt="Screenshot 2023-01-29 at 2 39 46 PM" src="https://user-images.githubusercontent.com/122561946/218338170-30ee5ab9-1158-4f1c-8cf9-6f89631a67fc.png">

In the image above the only method that is called is the handleRequest method which takes the URL in as an input. In the method there is an if statement which determines what to do based on what is put into the URL which is the important argument. Using the URL argument the method decides what to do and what message to display. If it is the first time entry into the server it will display "No words added". However for this usage of /add-message it uses the second condition which is only employed when /add-message is used. 

Immediately when this condition is called the system prints out which path we are in and it says in the terminal that we are in the /add-message path. Afterwards this method splits the URl from the = sign. Once split there are two elements in the array. The method assigns the second element of the array into the newString variable which becomes 

"Part 1 of lab report 2"

Then the variable returnAll, which is a string, gets added to with the newString and a new line to fit the format required for the next calls of /add-message. Then the returnAll variable which now has 

"Part 1 of lab report 2" + "\n" 

is returned to be displayed on the web server. 

The image below is what happens when /add-message is used again:

<img width="538" alt="Screenshot 2023-01-29 at 2 48 49 PM" src="https://user-images.githubusercontent.com/122561946/215360298-fe2c726a-33c6-4f51-8f3e-205c57f2b402.png">

In the image above the only method that is called is the handleRequest method which takes the URL in as an input. In the method there is an if statement which determines what to do based on what is put into the URL which is the important argument. The argument and its importance does not change from the first time /add-message is called. 

Immediately when this condition is called the system prints out which path we are in and it says in the terminal that we are in the /add-message path. Afterwards this method splits the URl from the = sign. Once split there are two elements in the array again. The method assigns the second element of the array into the newString variable which becomes "Second line". Then the variable returnAll gets added to with the newString and a new line to fit the format required for the next calls of /add-message. Then the returnAll variable which now has ""Part 1 of lab report 2" + "\n" + "Second line"" is returned to be displayed on the web server. In the second calling of /add-message all the variables are changed but only returnAll is added upon since it needs to display the previous messages as well. 

## Part 2: Bugs from lab

For this lab report I chose the array bug which was the first bug we covered in lab.

A failure inducing input for the program is:

```
public void testReversed1() {
    int[] input2 = {3, 4, 5, 6};
    assertArrayEquals(new int[]{6, 5, 4, 3}, ArrayExamples.reversed(input2));
  }
```

The code associated with it is:

```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
  
An input that does not induce failure is:

```
public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```

The code associated with it is the same as before.

The symptom of the bug is as shown in the image below: 

<img width="637" alt="Screenshot 2023-02-12 at 2 08 00 PM" src="https://user-images.githubusercontent.com/122561946/218340406-731b837c-3ea2-44d0-9834-cf83beefa4a2.png">

As seen from the image above the symptom of the bug is that it has a 0 intead of a 6 in the array. This can just be one of the many errors in the output but since it is the first one the test fails there and only shows that one to us. The reason why this error occurs is because there are no values in the   newArray array. As seen from the code every index of the array that is to be returned gets assigned with values from newArray. This means that it is only applying 0s to the array that is going to be returned. This makes the returned array `[0,0,0,0]`. The fix includes copying the contents of the inputted array into the newArray so when the reversing code runs it actually does it based on the numbers in the inputted array rather than an empty int array with zeros. Another fix for this bug is replacing `arr[i] = newArray[arr.length - i - 1];` with `newArray[i] = arr[arr.length - i - 1];` and for the return statement writing `return newArray;`. This way we also get rid of the problem of a zero array being returned since it does the operation using the values from `arr`. Both are fixes for the bug but the temporary array method can also be utilized for other methods. 

The before-and-after of the bug:

In the code snippet below you can see the method with the bug. It is the same one as the code block that the tests were associated with. 

Now here is the after version of the same method that includes a fix for the bug:

```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for (int j = 0; j < arr.length; j++){
      newArray[j] = arr[j];
    }
    
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

Here is the tests passing:

<img width="626" alt="Screenshot 2023-02-12 at 2 18 48 PM" src="https://user-images.githubusercontent.com/122561946/218340682-3840eeea-7181-45ac-a4d9-42a2aa133f2b.png">

As you can see in the code block above there is one significant change that fixes the bug. The bug was that there was not a temporary array which held the original data along with their indexes. This resulted in the new reversed array to use itself to reverse which then messed up the values and their indexes. By having a temp array we can ensure that we have a copy of the original array and use that to reverse into our new array. This way the bug is fixed and the JUnit test that did not pass passes. 


## Part 3: What I have learned from week 2 or week 3

One thing I learned that I did not know before was creating web servers. Before this class and especially beofre week 2 I thought that it was very complex and difficult to create web servers. I thought it required multiple people and a domain you had to buy along with extra costs to maintain the server. I did not know that we could create the server in our local host. After learning that it was not that difficult another thing that surprised me was the code required for it. I thought it would be way longer and I did not think that I had the knowledge to understand what was going on. Through the lab and revising now I know how to create a server class and use a URL interface. I think these new skills will be essential for me in the future. I want to go into software development and I think it will a good foundation for me as well. One thing I am proud of is for example in this lab report I could create the /add-message web server. If I am able to do these simple tasks, I feel like the momentum will allow meto create bigger projects. 
