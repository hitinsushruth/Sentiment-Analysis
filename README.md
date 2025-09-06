# Sentiment-Analysis
#This code takes a text input from the user and assess its sentiment using Textblob module.

#installing textblob module
pip install -U textblob

#import textblob library
from textblob import TextBlob

#Function to assess sentiment
def sentiment_analysis(input_text):
    blob = TextBlob(input_text)
    polarity_score = blob.sentiment.polarity
    #determine the sentiment based on the polarity score
    if polarity_score > 0:
        return "Positive", polarity_score
    elif polarity_score == 0:
        return "Neutral", polarity_score
    elif polarity_score < 0:
        return "Negative", polarity_score


def main():
    print("Lets Analyze the sentiment")
    print("Type end to exit the program")
    
    # Keep asking user for the next input until user enters end
    while True:
        #Ask for User's input
        user_input = input("Enter the Text: ")
        
        #Check if the User wants to end the program
        if user_input.lower().strip() == "end":
            print("Until next time...GoodBye!")
            break
            
        #Analyze the sentiment of the text
        sentiment, polarity_score = sentiment_analysis(user_input)
        
        print("And the Sentiment is: ", sentiment)
        print("Polarity score is: ", polarity_score)
    

    # Check if the script is being run directly (not imported as a module)
if __name__ == "__main__":
    # Call the main function to start the program
    main()
