<h1>Lab Report 2:</h1>

<h2>Part 1:</h2> 

<h3>StringServer</h3>
<code>
public class StringServer implements URLHandler{
    String messages = "";
    public static void main(String[] args){
        try{
            Server.start(Integer.parseInt(args[0]), new StringServer());
        }
        catch(IOException e){
            e.printStackTrace();
        }
    }

    @Override
    public String handleRequest(URI url) {
        if(url.getPath().equals("/add-message")){
            String[] queryParams = url.getQuery().split("=");
            if(queryParams[0].equals("s")){
                if(!messages.equals("")){
                    messages += "\n";
                }
                messages += queryParams[1];
            }
            return messages;
        }
        return "404 Path Not Found";
    }
}
</code>

<img width="394" alt="Screen Shot 2023-01-30 at 6 44 25 PM" src="https://user-images.githubusercontent.com/122490447/215649862-f6b5d4f3-b418-40ea-8fc1-d8b6e98ad732.png">

<code>handleRequest</code> 
is called, where the url passed in has the query <code>"s=hi"</code>
Prior to calling the function, the StringServer class instance running the server has it's messages instance variable set to an empty string.
After the request, <code>"hi"</code>, the second query parameter, is concatenated to the messages instance variable and returned by the method for display on the page.

<img width="421" alt="Screen Shot 2023-01-30 at 6 45 45 PM" src="https://user-images.githubusercontent.com/122490447/215649872-74f299de-230e-412e-a1ff-baccaa658c48.png">

<code>handleRequest</code> 
is called, where the url passed in has the query <code>"s=hello3"</code>
Prior to calling the function, the StringServer class instance running the server has it's messages instance variable contains "hello1\nhello2\n", where each \n is a newline.
After the request, <code>"hello3"</code>, the second query parameter, is concatenated to the messages instance variable and returned by the method for display on the page.

<h2>Part 2:</h2>

Failure-inducing input:
<img width="704" alt="Screen Shot 2023-01-30 at 6 59 23 PM" src="https://user-images.githubusercontent.com/122490447/215652800-a215b9f1-1eee-44a3-a17a-9d5c3c8e0403.png">

Success-inducing input:
<img width="547" alt="Screen Shot 2023-01-30 at 7 01 13 PM" src="https://user-images.githubusercontent.com/122490447/215652811-c6a3839d-94ce-437e-9e36-5c90f12e4eb6.png">

Failure symptom:
<img width="534" alt="Screen Shot 2023-01-30 at 7 02 38 PM" src="https://user-images.githubusercontent.com/122490447/215652825-12abf933-4da7-45ad-8fcf-9845c4981c1b.png">

Success symptom:
<img width="537" alt="Screen Shot 2023-01-30 at 7 03 08 PM" src="https://user-images.githubusercontent.com/122490447/215652859-51e32343-cef9-492b-a29e-2c6ce6003e53.png">

Bug before fix:
<img width="491" alt="Screen Shot 2023-01-30 at 7 03 58 PM" src="https://user-images.githubusercontent.com/122490447/215652868-cc57cb3f-697a-43b4-ba62-948b894ce91a.png">

Bug after fix:
<img width="491" alt="Screen Shot 2023-01-30 at 7 04 25 PM" src="https://user-images.githubusercontent.com/122490447/215652875-f494ed76-1195-4af1-859d-ab2f7989c9d9.png">

The fix addresses the issue, which is that the order of elements filtered is incorrect, by changing the filtered list adding behavior from prepending each element by adding to the 0th index to appending it by removing the index argument entirely. This causes the filtered list's order to match that of the inputted list, fixing the issue.

<h3>Part 3:</h3>

I didn't know Java could so readily act as a web server at such a low-level, I figured it would require relatively robust libraries to get such a framework in place because when I think about web server programming I tend to think of JavaScript, not Java. Thus a lot of the requestHandling was novel and I found it genuinely made me appreciate Java's versatility as an object-oriented language more, as I find I am oftened annoyed when working in JavaScript whereas Java is such a breeze to work in. Class instances work pretty elegantly when it comes to managing state for servers, which was surprising and delightful, as such state solutions for less object-oriented languages can be somewhat painful when it comes to frameworks like React or Angular for JavaScript.
