"""This script performs emotion detection analysis"""
import requests

# Function that runs emotion detection on input text text_to_analyse
def emotion_detector(text_to_analyse):
    """Function for emotion detection using Emotion Predict function of the Watson NPL library"""
    url = (
        "https://sn-watson-emotion.labs.skills.network/v1/watson.runtime.nlp.v1/"
        "NlpService/EmotionPredict"
    )

    # Create a dictionary with the text to be analyzed header
    header = {"grpc-metadata-mm-model-id": "emotion_aggregated-workflow_lang_en_stock"}

    # Define object with the text and headers return
    myobj = { "raw_document": { "text": text_to_analyse } }

    # Make a POST request to the API with the payload and header
    response = requests.post(url, json=myobj, headers=header, timeout=5)

    return response.text
