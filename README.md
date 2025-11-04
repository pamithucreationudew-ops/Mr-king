

```python
from flask import Flask, request
from twilio.twiml.messaging_response import MessagingResponse

app = Flask(_name_)

@app.route('/bot', methods=['POST'])
def bot():
    incoming_msg = request.values.get('Body', '').lower()
    resp = MessagingResponse()
    msg = resp.message()

    if 'hi' in incoming_msg:
        msg.body('Hello pami 💕! How can I help you today?')
    else:
        msg.body('Sorry, I did not understand that.')

    return str(resp)

if _name_ == '_main_':
    app.run()
```

 Mr-king
