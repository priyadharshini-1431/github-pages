mport nltk
from nltk.sentiment import SentimentIntensityAnalyzer

# Download the VADER lexicon
nltk.download('vader_lexicon')

# Initialize the sentiment analyzer
sia = SentimentIntensityAnalyzer()

# Function to analyze sentiment
def analyze_sentiment(text):
    sentiment_scores = sia.polarity_scores(text)
    if sentiment_scores['compound'] >= 0.05:
        return "Positive 😀"
    elif sentiment_scores['compound'] <= -0.05:
        return "Negative 😞"
    else:
        return "Neutral 😐"

# Example usage
social_media_post = "I love this new feature! It's amazing."
print(f"Sentiment: {analyze_sentiment(social_media_post)}")
