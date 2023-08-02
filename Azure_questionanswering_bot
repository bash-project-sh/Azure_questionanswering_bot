from azure.core.credentials import AzureKeyCredential
from azure.ai.language.questionanswering import QuestionAnsweringClient
endpoint = "<cognitiveservices_language_url>"
key = "<cognitiveservices_language_key>"

client = QuestionAnsweringClient(endpoint, AzureKeyCredential(key))

import azure.cognitiveservices.speech as speechsdk
AZURE_SPEECH_KEY = "<key>"
AZURE_SPEECH_REGION = "<region>"

speech_config = speechsdk.SpeechConfig(subscription=AZURE_SPEECH_KEY, region=AZURE_SPEECH_REGION)
speech_config.speech_recognition_language = "<language>"
speech_config.speech_synthesis_language = "<language>"

def STT():
    audio_config = speechsdk.audio.AudioConfig(use_default_microphone=True)
    speech_recognizer = speechsdk.SpeechRecognizer(speech_config=speech_config, audio_config=audio_config)

    print("You can speak now, I am listening…")
    speech_recognition_result = speech_recognizer.recognize_once_async().get()
    output = speech_recognition_result.text
    return output

def TTS(Text):
    audio_config = speechsdk.audio.AudioOutputConfig(use_default_speaker=True)
    speech_synthesizer = speechsdk.SpeechSynthesizer(speech_config=speech_config, audio_config=audio_config)
    speech_synthesis_result = speech_synthesizer.speak_text_async(Text).get()

def KB(Text):
    output = client.get_answers(
    question=Text,
    project_name="<project_name>",
    deployment_name="<depolyment_name>"
    )
    for candidate in output.answers:
        return candidate.answer

def Main():
    Text = STT()
    print(KB(Text))
    TTS(KB(Text))

if __name__ == "__main__":
    Main()
