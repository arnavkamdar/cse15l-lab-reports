# __Servers and Bugs (Lab Report 2)__
---
## __Part 1:__

To design the StringServer class, I built upon the NumberServer class that we had previously used in the lab. I implemented a method that searched for the word to be added and displayed it in the form of one continuous, concatenated string with line breaks. Following is the code I used for StringServer, as well as the code for the Handler class that performs all the operations. 


```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler 
{
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String listToDisplay = "";

    public String handleRequest(URI url) 
    {
        if (url.getPath().contains("/add")) 
        {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) 
            {
                listToDisplay += (parameters[1] + "\n");
                return listToDisplay;
            }
        }
        return "404 Not Found!";
    }
}


class StringServer 
{
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```

Running the following commands on my terminal set up the server: 
```
javac Server.java StringServer.java
java StringServer
```

After this, I used the following messages in the search bar: 
![Image](https://media.discordapp.net/attachments/794151037766336524/1068779889232199730/image.png?width=1440&height=356)
* For this message, the method called in my code was `handleRequest`, under the `Handler` class. 
* The argument used in calling this method was the URI that was typed into the search bar, 'http://localhost:1306/add-message?s=Never%20Gonna%20Give%20You%20Up'. 
* From this, the method extracted the query `s?Never%20Gonna%20Give%20You%20Up` and separated the string "Never Gonna Give You Up" from it. 
* The instance variable `listToDisplay` keeps a track of what is displayed on the screen, and is duly updated with the query and a linebreak after the string is extracted. 

![Image](https://media.discordapp.net/attachments/794151037766336524/1068782579488141352/image.png?width=1440&height=358)
* For this message, the method called in my code was once again `handleRequest`, under the `Handler` class. 
* The argument used in calling this method was the URI typed into the search bar, 'http://localhost:1306/search?s=Never%20Gonna%20Let%20You%20Down'. 
* From this, the method attempted to find the query after `/add` but could not find it, since the phrase `/add` does not exist in the url. 
* As a result, no instance variables are updated (since the if statement is not executed) and the phrase `404 Not Found!` is returned. 

---

## __Part 2:__ 

- For this part, I chose to use the `ArrayExamples` class and the method `averageWithoutLowest`. This method is meant to return the average of a set of numbers, excluding the single lowest number. 

- The failure inducing input I used was an array of doubles: `{2.0, 2.0, 10.0}`. This was the JUnit test I wrote on Java:
```
  @Test
  public void testLowest()
  {
    double[] input1 = {2.0, 2.0, 10.0};
    assertEquals(6.0, ArrayExamples.averageWithoutLowest(input1), 0.000001);
  }
```

- This was an input that did NOT induce a failure: `{2.0, 4.0, 10.0}`. This was the JUnit test I wrote on Java:
```
  @Test
  public void testLowest()
  {
    double[] input1 = {2.0, 4.0, 10.0};
    assertEquals(7.0, ArrayExamples.averageWithoutLowest(input1), 0.000001);
  }
```
- When running the two inputs, the first one induces a failure where the expected value was 6.0 and the actual value was 5.0. The second one runs correctly, where the expected and actual values were 7.0. 
![Image](https://media.discordapp.net/attachments/794151037766336524/1068783120037462027/JUnit_tests.JPG)

- The bug that I noticed was that the minimum value is always omitted from the calculations, regardless of how many times it is present in the array. To fix this, I implemented a boolean minFound value that overrides the loop if the minimum has already been found. This fixed the issue in testing.

This was the code before fixing the bug:
```
  // Averages the numbers in the array (takes the mean), but leaves out the
  // lowest number when calculating. Returns 0 if there are no elements or just
  // 1 element in the array
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }		//bug
    }
    return sum / (arr.length - 1);
  }
```

This was the code after fixing the bug: 
```
  // Averages the numbers in the array (takes the mean), but leaves out the
  // lowest number when calculating. Returns 0 if there are no elements or just
  // 1 element in the array
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    boolean minFound = false;
    for(double num: arr) 
    {
        if (num != lowest)
            sum += num;
        else 
        {
            if (minFound)
                sum += num;
            else 
                minFound = true;
        }
    }
    return sum / (arr.length - 1);
  }
```

- This fix addresses the issue as it creates a boolean `minFound` variable, which describes whether the minimum has been found. When it has been found, the code will add all subsequent doubles, regardless of their value. 


---
## __Part 3:__

While I did know JUnit Testing due to prior experience with the PA, one new thing I learnt during the lab sessions was how to set up an online server using Java. I intially did not understand a lot of what was taught in class, but working at the lab made it much easier to break down the code into parts I could understand. These lab sessions were particularly unique because this was the first time I saw Java interact with another platform. 

