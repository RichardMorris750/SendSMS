# SendSMS
Simple example of sending SMS messages

The project contains a routine called send_sms_message which will send a message to the assigned phone number.

To enable the service you must purchase a subscription from Informatica.  You can get demonstration licenses for testing.

This is how to send an MSM message:

The first argument is the fully qualified destination number.  Use a + followed  by the country code and the number
The second argument is the "from" number although this is not presented to the destination phone.
Third argument is the name of the person to receive the message.
Forth argument is the message body.  the "name" argument is prepended to this string
The final argument is returned with the call status message.  "Message Queued" is a success.


Send a message, a response of 0 is a success:

result = send_sms_message("+11234561234", "+11234561234", "Richard", "Synergy calling...", errText)

As well as sending the message the web services will also check the number of messages you have left
as part of your subscription.  the CheckSMS routine will send out an email if the number of available
messages falls below a certain level - please review the code in CheckSMS for details of the logical
variables that should be set to enable this.

The routine will also log each transmission attempt to temp:SMSProcess.log
