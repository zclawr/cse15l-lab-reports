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

<hr>
<img width="394" alt="Screen Shot 2023-01-30 at 6 44 25 PM" src="https://user-images.githubusercontent.com/122490447/215649862-f6b5d4f3-b418-40ea-8fc1-d8b6e98ad732.png">
<hr>

<code>handleRequest</code> is called, where the url passed in has the query <code>"s=hi"</code>
Prior to calling the function, the <code>StringServer</code> class instance running the server has it's messages instance variable set to an empty string.
After the request, <code>"hi"</code>, the second query parameter, is concatenated to the messages instance variable and returned by the method for display on the page.
<hr>
<img width="421" alt="Screen Shot 2023-01-30 at 6 45 45 PM" src="https://user-images.githubusercontent.com/122490447/215649872-74f299de-230e-412e-a1ff-baccaa658c48.png">
<hr>

<code>handleRequest</code> is called, where the url passed in has the query <code>"s=hello3"</code>
Prior to calling the function, the <code>StringServer</code> class instance running the server has it's messages instance variable set to <code>"hello1\nhello2\n"</code>, where each <code>\n</code> is a newline.
After the request, <code>"hello3"</code>, the second query parameter, is concatenated to the messages instance variable and returned by the method for display on the page.

<h2>Part 2:</h2>

<h3>Failure-inducing input:</h3>
<code>
    
    @Test
    public void testFilter(){
        List<String> ls = new ArrayList();
        ls.add("Apple");
        ls.add("Pear");
        ls.add("Orange");
        ls.add("Grape");
        List<String> filtered = ListExamples.filter(ls, new StringChecker() {
            public boolean checkString(String s){
                return s.contains("r");
            }
        });
        ls.remove("Apple");
        assertArrayEquals(ls.toArray(), filtered.toArray());
    }
</code>

<h3>Success-inducing input:</h3>
<code>
    
    @Test
    public void testFilter2(){
        List<String> ls = new ArrayList();
        ls.add("Pear");
        ls.add("Apple");
        List<String> filtered = ListExamples.filter(ls, new StringChecker() {
            public boolean checkString(String s){
                return s.contains("r");
            }
        });
        ls.remove("Apple");
        assertArrayEquals(ls.toArray(), filtered.toArray());
    }
</code>

<h3>Failure symptom:</h3>
<img width="534" alt="Screen Shot 2023-01-30 at 7 02 38 PM" src="https://user-images.githubusercontent.com/122490447/215652825-12abf933-4da7-45ad-8fcf-9845c4981c1b.png">

<h3>Success symptom:</h3>
<img width="537" alt="Screen Shot 2023-01-30 at 7 03 08 PM" src="https://user-images.githubusercontent.com/122490447/215652859-51e32343-cef9-492b-a29e-2c6ce6003e53.png">

<h3>Bug before fix:</h3>
<code>
    
    static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0, s);
      }
    }
    return result;
    }
</code>

<h3>Bug after fix:</h3>
<code>
    
    static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(s);
      }
    }
    return result;
    }
</code>

The fix addresses the issue, which is that the order of elements filtered is incorrect, by changing the filtered list adding behavior from prepending each element by adding to the 0th index to appending it by removing the index argument entirely. This causes the filtered list's order to match that of the inputted list, fixing the issue.

<h2>Part 3:</h2>

I didn't know Java could so readily act as a web server at such a low-level, I figured it would require relatively robust libraries to get such a framework in place because when I think about web server programming I tend to think of JavaScript, not Java. Thus a lot of the requestHandling was novel and I found it genuinely made me appreciate Java's versatility as an object-oriented language more, as I find I am oftened annoyed when working in JavaScript whereas Java is such a breeze to work in. Class instances work pretty elegantly when it comes to managing state for servers, which was surprising and delightful, as such state solutions for less object-oriented languages can be somewhat painful when it comes to frameworks like React or Angular for JavaScript.
