# Whatsapp-API
 Recently Whatsapp opened for businesses. Scheduling is much more useful for businesses.
That's why I created an API to schedule whatsapp messages which contains CRUD
functionality(Create(post),Read(get),Update(put),Delete(delete)).
Firstly I will take the message scheduled time and phone number from User and I will store them
in mySQL database.
3. Then For every two minutes I will poll unsent messages from the database and i will send
them to whatsapp API which instantly send messages to the end user
Challenges faced:
1. If the message request fails then I will resend it 3 times and if it still fails I will ignore that
message.
2. If messages are large in number then if we call all at a time then the java program will break.
So for that we will use LIMIT in mySQL to poll messages for 25 or 50 messages at a
time.
Workflow of the Project First We will send POST request to my API(URL) which contains
message,scheduled time and phone number and i will check whether the user is authorized or
not using the header present in the request(token = reference value which is) If the user is not
authorized then I will send corresponding response(Unauthorized).next i will validate the given
data like whether phone number contains 10 digits or not and message size is > O or not.
If any of the validation fails i will send the corresponding response(validation error)
Next will store that messages in the MySQL database. For every 2 min i will poll/retrieve that
message present in my database. Then will send the POST request to the Whatsapp API and
stores the corresponding response
in mySQL database.
And Customer/user will automatically get the messages at the scheduled time.
Database
Phone number(int),scheduled time messages(var)
