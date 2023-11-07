# hack4mini
hackathon code
To create event management system:	
event handling:
window.addEventListener('load', function() {
    console.log('The page has finished loading');
});
 {document.
querySelector    console('button.').logaddEventListener('('clickThe page', has function finished() { loading
   '); console
.});log
('```The button

 was2 clicked');
});

3. The `event
Here's an example:

```javascript
.documentpreventDefault.()`querySelectorAll method(' isbutton used'). to preventforEach(function the( defaultbutton action) of {
 an    event button..
addEventListener('
clickHere',' functions() an {
 example       : console
.log
```('javascriptButton
 clickeddocument:',. thisgetElementById.('innerHTML);myLink
   '). });addEventListener
('});
click```',
 function
(5event.) When { handling form
 subm   issions event, it.'preventDefaults(); important to
 access    the console form. datalog and(' validateThe it link before subm wasitting clicked it,. but

 the defaultHere' actions was an prevent exampleed:');


```});javascript

```document
.querySelector
('4form.'). The `addEventListener('submitevent', function.stop(eventPropag)ation {()`
    method event is. usedpreventDefault to(); stop
 the     propag
   ation let of formData an event =. new
 Form
Data(Hereevent'.targets an); example
    :

    for
(```letjavascript pair
 ofdocument form.Data.getElementByIdentries()) {
        console('.mylogButton(').pairaddEventListener[('0click] +', ' function:( 'event + pair)[ {1
    event]);
.   stop }
});

5. Custom events can be created and dispatched using the `CustomEvent()` constructor and the `dispatchEvent()` method.

Here's an example:

```javascript
document.getElementById('myButton').addEventListener('myCustomEvent', function(event) {
    console.log('The custom event was triggered');
});

var myCustomEvent = new CustomEvent('myCustomEvent');
document.getElementById('myButton').dispatchEvent(myCustomEvent);

html:
<!DOCTYPE html>
<html>
<head>
 <title>Event Management System</title>
 <link rel="stylesheet" href="styles.css">
</head>
<body>
 <div class="event-form">
    <h2>Create a new event</h2>
    <form id="event-form">
      <label for="event-name">Event Name:</label>
      <input type="text" id="event-name" name="event-name" required>
      
      <label for="event-date">Event Date:</label>
      <input type="date" id="event-date" name="event-date" required>
      
      <label for="event-time">Event Time:</label>
      <input type="time" id="event-time" name="event-time" required>
      
      <label for="event-location">Event Location:</label>
      <input type="text" id="event-location" name="event-location" required>
      
      <label for="event-description">Event Description:</label>
      <textarea id="event-description" name="event-description" required></textarea>
      
      <label for="event-image">Event Image:</label>
      <input type="file" id="event-image" name="event-image" required>
      
      <button type="submit">Create Event</button>
    </form>
 </div>
  
 <div class="ticket-form">
    <h2>Purchase Tickets</h2>
    <form id="ticket-form">
      <label for="event-id">Event ID:</label>
      <input type="text" id="event-id" name="event-id" required>
      
      <label for="quantity">Quantity:</label>
      <input type="number" id="quantity" name="quantity" min="1" required>
      
      <button type="submit">Purchase Tickets</button>
    </form>
 </div>
  
 <script src="
database created a table on tickets in my sql database
sql for ticket handling:
CREATE TABLE tickets (
 id INT AUTO_INCREMENT PRIMARY KEY,
 name VARCHAR(255) NOT NULL,
 email VARCHAR(255) NOT NULL,
 subject VARCHAR(255) NOT NULL,
 message TEXT NOT NULL,
 status ENUM('Open', 'Closed', 'Pending') NOT NULL DEFAULT 'Open'
);
html form for submit their support tickets
front end html:
<form id="support-form">
 <label for="name">Name:</label>
 <input type="text" id="name" name="name" required>

 <label for="email">Email:</label>
 <input type="email" id="email" name="email" required>

 <label for="subject">Subject:</label>
 <input type="text" id="subject" name="subject" required>

 <label for="message">Message:</label>
 <textarea id="message" name="message" required></textarea>

 <button type="submit">Submit</button>
</form>
js is used for submission and interact with backend code 
here it is js with ajax to send form data into server  
js:
document.getElementById('support-form').addEventListener('submit', function(event) {
 event.preventDefault();

 var name = document.getElementById('name').value;
 var email = document.getElementById('email').value;
 var subject = document.getElementById('subject').value;
 var message = document.getElementById('
payment python:
server side implementation:
from flask import Flask, request, jsonify
import stripe

app = Flask(__name__)

# Replace 'your_stripe_secret_key' with your actual Stripe secret key
stripe.api_key = 'your_stripe_secret_key'

@app.route('/charge', methods=['POST'])
def charge():
    amount = request.form['amount']
    token = request.form['stripeToken']

    try:
        charge = stripe.Charge.create(
            amount=int(amount),
            currency='usd',
            source=token,
            description='Charge for some amazing product'
        )

        return jsonify({'status': 'success', 'charge_id': charge.id}), 200

    except stripe.error.CardError as e:
        return jsonify({'status': 'error', 'message': str(e)}), 400

if __name__ == '__main__':
    app.run(port=5000)
client side implementation using html:
<!DOCTYPE html>
<html>
<head>
    <title>Payment</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script src="https://js.stripe.com/v3/"></script>
</head>
<body>
    <form id="payment-form">
        <div class="form-row">
            <label for="card-element">Credit or debit card</label>
            <div id="card-element"></div>
            <div id="card-errors" role="alert"></div>
        </div>
        <button id="submit">Submit Payment</button>
    </form>

    <script>
        // Replace 'your_stripe_publishable_key' with your actual Stripe publishable key
        var stripe = Stripe('your_stripe
