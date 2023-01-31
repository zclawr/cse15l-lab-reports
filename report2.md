Lab Report 2:

Part 1: 

StringServer:
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

<img width="394" alt="Screen Shot 2023-01-30 at 6 44 25 PM" src="https://user-images.githubusercontent.com/122490447/215649862-f6b5d4f3-b418-40ea-8fc1-d8b6e98ad732.png">

handleRequest is called, where the url passed in has the query "s=hi".
Prior to calling the function, the StringServer class instance running the server has it's messages instance variable set to an empty string.
After the request, "hi", the second query parameter, is concatenated to the messages instance variable and returned by the method for display on the page.

<img width="421" alt="Screen Shot 2023-01-30 at 6 45 45 PM" src="https://user-images.githubusercontent.com/122490447/215649872-74f299de-230e-412e-a1ff-baccaa658c48.png">


handleRequest is called, where the url passed in has the query "s=hello3".
Prior to calling the function, the StringServer class instance running the server has it's messages instance variable contains "hello1\nhello2\n", where each \n is a newline.
After the request, "hello3", the second query parameter, is concatenated to the messages instance variable and returned by the method for display on the page.

Part 2:

