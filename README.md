# Tornado Chat demo using MongoDB

## Local development

    pip install --user pycurl
    pypm install -r requirements.
    python app.py

## Deploying to Stackato

    stackato push tornado-chat-mongo
    # NOTE: Be sure to add a MongoDB service
