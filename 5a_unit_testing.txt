"""This script performs unit testing for EmotionDetection.emotion_detection"""
import unittest
from EmotionDetection.emotion_detection import emotion_detector

# Define unitests
class TestEmotionDetector(unittest.TestCase):
    """Class implementing unittests for emotion_detector"""
    def test_emotion_detector(self):
        """Function that defines test cases for emotion_detector"""
        # Test case for dominant emotion joy
        result = emotion_detector('I am glad this happened')
        self.assertEqual(result['dominant_emotion'],'joy')

        # Test case for dominant emotion anger
        result = emotion_detector('I am really mad about this')
        self.assertEqual(result['dominant_emotion'],'anger')

        # Test case for dominant emotion disgust
        result = emotion_detector('I feel disgusted just hearing about this')
        self.assertEqual(result['dominant_emotion'],'disgust')

        # Test case for dominant emotion sadness
        result = emotion_detector('I am so sad about this')
        self.assertEqual(result['dominant_emotion'],'sadness')

        # Test case for dominant emotion fear
        result = emotion_detector('I am really afraid that this will happen')
        self.assertEqual(result['dominant_emotion'],'fear')

unittest.main()
