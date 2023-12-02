import pandas as pd
import matplotlib.pyplot as plt
import numpy as np

# Sample data for demonstration
data = {'Day': np.arange(1, 11), 'Temperature': [25, 27, 28, 30, 32, 35, 34, 31, 29, 26]}
df = pd.DataFrame(data)

def generate_temperature_plot():
    plt.plot(df['Day'], df['Temperature'])
    plt.xlabel('Day')
    plt.ylabel('Temperature (°C)')
    plt.title('Temperature Trend')
    plt.show()
    
def simple_chatbot(user_input):
    user_input = user_input.lower()

    greetings = ['hello', 'hi', 'hey', 'greetings']
    farewells = ['bye', 'goodbye', 'see you later']
    inquiries = ['how are you', 'what are you doing', 'how do you do']
    programming_topics = ['programming', 'coding', 'code', 'developer']
    python_topics = ['python', 'python programming', 'python language']
    AI_topics = ['artificial intelligence','ai','AI']
    funny_topics = ['joke','funny']
    plot = ['show me the temperature plot', 'temperature graph', 'plot']
    

    # Check user input against predefined rules
    if any(word in user_input for word in greetings):
        return "Hello! How can I help you today?"

    elif any(word in user_input for word in farewells):
        return "Goodbye! Have a great day!"

    elif any(word in user_input for word in inquiries):
        return "I'm just a computer program, but thanks for asking!"

    elif any(word in user_input for word in programming_topics):
        return "Programming is the process of creating a set of instructions that tell a computer how to perform a task. How can I assist you with programming?"

    elif any(word in user_input for word in python_topics):
        return "Python is a high-level programming language known for its readability and versatility. How can I assist you with Python?"

    elif any(word in user_input for word in AI_topics):
        return "AI, or Artificial Intelligence, is a field of computer science focused on creating systems that can perform tasks requiring human-like intelligence."

    elif any(word in user_input for word in funny_topics):
        return "that's great!, Why don't scientists trust atoms? :Because they make up everything!"

    elif any(word in user_input for word in plot):
        generate_temperature_plot()
        return "Here is the temperatue plot!"

    else:
        return "I'm sorry, I didn't understand that. Can you please rephrase or ask another question?"

while True:
    user_input = input("You: ")
    if user_input.lower() == 'exit':
        print("Chatbot: Goodbye!")
        break
    response = simple_chatbot(user_input)
    print("Chatbot:", response)

