# Tornado Chat with MongoDB

This is a multi-user chat application based on the Tornado Python
web framework.  It uses your Google account for login.

This version persists chat messages using the Mongo database.

## Local development

    pip install --user pycurl
    pypm install -r requirements.
    python app.py

## Deploying to Stackato

    stackato push tornado-chat-mongo
    # NOTE: Be sure to add a MongoDB service
