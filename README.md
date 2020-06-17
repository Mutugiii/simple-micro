# Microservices
Microservices using [nameko](https://github.com/nameko/nameko)

Usage
- Clone/Download the repository
- Create a .env file and add tokens/secrets for twitter to use the Twitter bot microservices, twilio to use sms messaging microservice & google using sign-in with app password to use the email microservice.(More info on app passwords [here](https://support.google.com/accounts/answer/185833))
- Update/Replace the email message templates based on your preference. They are located in the `mailer/templates` directory
- Run the command `docker compose up` to build & run the app
- Visit port 8000 and specify the target url with the relevant data passed.

---

#### Endpoints
* /sms -> Send a text message to a phone number of choice with a message you specify
* /mailer -> Sends an email to an email address of choice with a name & message
* /tweet  -> Post a tweet to the specified account

**All the endpoints only accept POST requests**

---

##### Running app
Examples commands using curl to run via the command line:
```
curl -i -d "{\"receiver_email\": \"test@test.com\", \"receiver_name\": \"test\" ,\"mail_message\": \"Hello this is a test Email\"}" localhost:8000/mailer

curl -i -d "{\"tweet_message\": \"Hello World\"}" localhost:8000/tweet

curl -i -d "{\"receiver_number\": \"+254728104485\", \"sms_message\": \"Test sms\"}" localhost:8000/sms
```
