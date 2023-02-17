# -amazon-lex - Chatbot

AWS Practice tutorial 

With the current climate and the rise of even more automation, I thought it would be great to learn how to build a chat bot. Looking at call centres, NHS helplines and ordering in general, there's more automation. The first step would be build a chat bot then link it using Lambda and an API.

In this part of the tutorail we're going to create a Chatbot that helps us order a pizza a drink. 

So in the AWS console, hop to Amazon Lex. Then click create bot.
Then you want to select blank bot.

Bot name - OrderingPizza
Description (optional) - helps us order pizza and a drink
IAM Permission - Create a role with basic amazon Lex permissions  
COPPA - select no

<img width="1792" alt="Screenshot 2023-02-16 at 11 15 55" src="https://user-images.githubusercontent.com/71371405/219657132-611c8191-7663-4a71-9df8-42c3055757b6.png">

The hit next page. 

<img width="1792" alt="Screenshot 2023-02-16 at 11 21 52" src="https://user-images.githubusercontent.com/71371405/219658048-c72f296b-760a-4d8a-8028-7203222a1730.png">

This is where you can select a region and the accent will change to. There's also a male or female. option. I selected English (GB) and the voice of Arthur. 

Then hit done.

<img width="1792" alt="Screenshot 2023-02-16 at 11 29 10" src="https://user-images.githubusercontent.com/71371405/219660030-d96855ad-02bf-438a-9169-83050aff3bd2.png">

At the top where it says the language, if you click, will take you back to the main page. This will be a good default to return to, as it can sometimes be confusing, having different intent, slots and segments to go with it. 

 So firstly we need to create an Intent - think of an intent like a category / topic of the conversation. 1) Hello - 2) I want a pizza - 3) I want a drink. 
 
 So click on Language at the top - then use the left-hand side option to click Intent. The click the big orange Add Intent
 
 <img width="1792" alt="Screenshot 2023-02-17 at 11 04 54" src="https://user-images.githubusercontent.com/71371405/219663881-5a0bcced-b3d0-44b5-afad-dff7803f64f2.png">
 
 Starting the conversation we'll add our first intent as Greetings.
 
 <img width="1792" alt="Screenshot 2023-02-17 at 11 05 03" src="https://user-images.githubusercontent.com/71371405/219664273-0b969f44-4609-4992-a1d3-623d47653974.png">
 
 We will add Utterances - This is from the prospective of the user - so we would assume the users will start by saying hello or a similar greeting. Hence why I have typed more varied greetings. 
 
 So now we want the user greeting to be replied to by the chatbot. On the same page go to Closing responce. Say hello to the user - and then ask them if the would like to order pizza
<img width="1792" alt="Screenshot 2023-02-17 at 11 05 15" src="https://user-images.githubusercontent.com/71371405/219676360-d66180df-04c7-41b3-b94d-e94593246ed7.png">

And save intent. If you want you can click build and test, just to see if it's working. 

<img width="1792" alt="Screenshot 2023-02-17 at 11 08 32" src="https://user-images.githubusercontent.com/71371405/219676947-18a514cb-fe56-4f26-a145-21e0fe2718bb.png">

So we have said hello and are now done with the greeting. We need to move onto the next topic of conversation. Click language - then Intent on the left side - the add intent - call it PizzaOrdering

<img width="1792" alt="Screenshot 2023-02-17 at 11 10 50" src="https://user-images.githubusercontent.com/71371405/219678797-3b9d5561-f54e-4eb3-b2c5-9500503f61c8.png">

We'll add the utterance
<img width="1792" alt="Screenshot 2023-02-17 at 11 12 48" src="https://user-images.githubusercontent.com/71371405/219679240-1e3f6706-5695-4bce-9dab-fd9656bd806d.png">

When we respond we to ask them what size of pizza do they want; and give them the provided options. For this we need to add a slot type within PizzOrdering. Click the Language at the top - on the left-hand side under intents click Slot Types. Then add a blank Slot Type. Name the slot type as SizeType
<img width="1792" alt="Screenshot 2023-02-17 at 15 05 16" src="https://user-images.githubusercontent.com/71371405/219691269-890c41a0-25bb-46c1-8613-9826d53c91a6.png">
Then add the values - Small - Medium - Large. Once we have done this click save - bottom right. Then click the PizzaSize on the left side - then add slot. 
<img width="1792" alt="Screenshot 2023-02-17 at 11 27 35" src="https://user-images.githubusercontent.com/71371405/219692987-0d4664af-28b0-4eb7-bd53-986ab2652888.png">

Now we can repeat the same process for the PizzaOrdering. Add Slot type (PizzaType) - add slot (ToppingType)

<img width="1792" alt="Screenshot 2023-02-17 at 11 17 55" src="https://user-images.githubusercontent.com/71371405/219681091-ba7b5656-8f94-42d6-95d3-c430c73d1ae2.png">
<img width="1792" alt="Screenshot 2023-02-17 at 11 24 42" src="https://user-images.githubusercontent.com/71371405/219683982-7b65310a-b9a9-4e49-b5cb-8008649f734c.png">

Then we will add then confirmation
<img width="1792" alt=" " src="https://user-images.githubusercontent.com/71371405/219699009-19cca15d-bd7a-4bbe-9db2-3a54e46cacc2.png">

Confirming to go through with the order or not.
<img width="1792" alt=" " src="https://user-images.githubusercontent.com/71371405/219701198-72593cf4-b073-4ffe-be18-e913025c82f2.png">




 Then we need to add a Fulfillment, which is a reaction to the order, was it successful or not. This is where I added, is there anyithing else to add to the order, like drinks. Once again repeating the process. Intent - Slot type -add slot - confirm - fulfillment - and finally - closing, "Thanks, see you next time"<img width="1792" alt="Screenshot 2023-02-17 at 11 47 08" src="https://user-images.githubusercontent.com/71371405/219700965-763b238c-133c-48a4-8f0d-f3941dbb926e.png">
 
 once this completed you should have a successful chatbot. So click Build then Test!
<img width="1792" alt="Screenshot 2023-02-17 at 11 51 39" src="https://user-images.githubusercontent.com/71371405/219701672-c5f9fa1e-5872-42b8-b933-9299101d7e38.png">

<img width="1792" alt="Screenshot 2023-02-17 at 11 52 25" src="https://user-images.githubusercontent.com/71371405/219701722-94acc53b-4b46-46f0-9b78-acec3e4e0f2e.png">
<img width="1792" alt="Screenshot 2023-02-17 at 15 53 39" src="https://user-images.githubusercontent.com/71371405/219701976-89638285-fcd9-4655-b973-e23092bb4126.png">


The next stage would be to add a Lambda function, which connects to an API.

For now, 

Happy Clouding! 
