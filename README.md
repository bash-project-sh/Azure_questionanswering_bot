# Azure_questionanswering_bot

This is a simple chatbot using Python & Azure cloud services(Speech, QuestionAnswering)

# How to use
1. Python 3.11.4
```
pip install azure-ai-language-questionanswering, azure-cognitiveservices-speech, azure-core
```
2. Azure account
3. Replace <> with required information
```
endpoint = "<cognitiveservices_language_url>"
key = "<cognitiveservices_language_key>"

AZURE_SPEECH_KEY = "<key>"
AZURE_SPEECH_REGION = "<region>"

speech_config.speech_recognition_language = "<language>"
speech_config.speech_synthesis_language = "<language>"

project_name="<project_name>"
deployment_name="<depolyment_name>"
```

# Reference
https://youtu.be/c2jt6vZgsAQ \
https://github.com/Azure/azure-sdk-for-python/tree/main/sdk/cognitivelanguage/azure-ai-language-questionanswering \
https://learn.microsoft.com/en-us/python/api/azure-cognitiveservices-speech/azure.cognitiveservices.speech?view=azure-python
