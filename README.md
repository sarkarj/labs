# Build and publish in AWS ECS (Elastic Container Service) a microservice on sentiment analysis using python and [flair](https://pypi.org/project/flair/) NLP library

There are several models on NLP (natural language processing) based sentiment analysis, which can determine if a particular block of text has a positive, negative, or neutral sentiment. There are off-the-shelf rule-based models like [TextBlob](https://pypi.org/project/textblob/) or embedding-based like [Flair](https://pypi.org/project/flair/), which is a PyTorch-based framework for state-of-the-art NLP library that supports sequence tagging, embeddings, and classification.

## Comparing [Textblob](https://pypi.org/project/textblob/) and [Flair](https://pypi.org/project/flair/) models

[Textblob](https://pypi.org/project/textblob/) provides a simple rule-based API for sentiment analysis that returns a polarity score within the range of (1.0 to -1.0), and a subjectivity score within the range of (0.0 to 1.0). Positive sentiment has a positive polarity number, and negative sentiment has a negative polarity number. A score 0 indicates the text is very objective and returns a higher score when the text is fairly subjective.

To install using pip (Python Package Installer)
  
    pip3 install textblob

    from textblob import TextBlob
    blob = TextBlob("The book was engaging, enjoyed reading, definitely recommending")
    for sentence in blob.sentences:
        print(sentence.sentiment)
  
[Flair](https://pypi.org/project/flair/) provides the API that utilizes a pre-trained model to detect positive or negative comments and provides the response in terms of positive or negative with a prediction confidence score in the range of (0.0 - 1.0)

To install using pip (Python Package Installer)

    pip3 install flair
    
    from flair.models import TextClassifier
    from flair.data import Sentence
    classifier = TextClassifier.load('en-sentiment')
    sentence = Sentence("The book was engaging, enjoyed reading, definitely recommending")
    classifier.predict(sentence)
    print('Sentence Score : ', sentence.labels)

<img src>
## Selecting [flair](https://pypi.org/project/flair/) model and build an API

## Building [AWS EC2](https://console.aws.amazon.com/ec2/) model 
