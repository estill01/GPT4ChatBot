# GPT4ChatBot

Interact with GPT-4 from the comfort of your Command Line.

- Save all data locally in an easy to parse structure.
- Manage and switch between multiple chat sessions contexts. 

## Usage
Initialize it with your OpenAI API key and start creating and managing chats:


### Basic Usage
```
gpt4_chat_bot = GPT4ChatBot(api_key="your_openai_api_key_here")

# Create a new chat
chat_id = gpt4_chat_bot.create_chat()

# Submit a prompt and receive a response
response = gpt4_chat_bot.submit_prompt(chat_id, "What is the weather like today?", max_tokens=50)
print(response)

# Switch between chats or create new chats as needed
```

### Stream Responses to `stdout` or file
```
# Example usage with streaming
gpt4_chat_bot = GPT4ChatBot(api_key="your_openai_api_key_here")
chat_id = gpt4_chat_bot.create_chat()

# Stream to stdout (default)
response = gpt4_chat_bot.submit_prompt(chat_id, "What is the weather like today?", max_tokens=50, stream=True)

# Stream to a file
gpt4_chat_bot.set_stream_callback_to_file("stream_output.txt")
response = gpt4_chat_bot.submit_prompt(chat_id, "What is the weather like today?", max_tokens=50, stream=True)
```

## Planned Features

### Search

**Keyword-based search**

Allow users to search for specific keywords or phrases within the chat messages across all branches. The chatbot can then display a list of matching branches or conversations, along with a brief summary or relevant excerpt for each.

**Chronological navigation** 

Enable users to navigate the chat history based on time or events, such as "go back to before we branched" or "go to the branch created on [date]". The chatbot can analyze the chat metadata to identify the appropriate branch or conversation and switch to it.

**Topic-based search**

Implement a topic detection system that identifies the main topic or subject of each chat branch or conversation. Users can then search for chats based on these topics, such as "go to the branch where we explored xyz".

**Semantic search**

Enhance the search functionality by using semantic similarity techniques to identify branches or conversations that are related to the user's query, even if they don't contain the exact keywords. This can help users find relevant chats more easily.

**User-friendly navigation**

Provide a simple and intuitive interface for users to navigate between branches and chats, either through text commands or a graphical interface. This can include commands like "go to the parent branch" or "list all sibling branches".

### Speech UI

Text-to-Speech and Speech-to-Text

## Possible Future Features
User profiles: 

Allow users to create and manage profiles, which store their preferences, chat history, and other personalization settings. This could help tailor the chatbot's responses to specific users.

Sentiment analysis: 

Implement sentiment analysis to gauge the mood of the user during the conversation. The chatbot could adjust its responses accordingly to maintain a positive and engaging experience.

Language translation: 

Add a translation feature that allows users to communicate with the chatbot in their preferred language. The chatbot could automatically detect and translate messages into the desired language.

Speech-to-text and text-to-speech: 

Integrate speech recognition and synthesis features to enable users to interact with the chatbot using voice commands and receive spoken responses.

Topic-based suggestions: 

Implement a system that detects the topic of conversation and offers relevant suggestions or information to the user. This could help the chatbot provide more engaging and useful responses.

Multi-user conversations: 

Enable the chatbot to handle multi-user conversations, where multiple people can interact with the chatbot and each other in the same chat thread.

Chatbot training: 

Implement a feature that allows users to provide feedback on the chatbot's responses, helping it improve over time. This feedback could be used to fine-tune the model or identify areas that need improvement.

Scheduled prompts: 

Add a feature that allows users to schedule prompts to be sent at specific times or intervals, which could be useful for reminders, follow-ups, or periodic check-ins.

Integration with external services: 

Enable the chatbot to interact with external services, such as email, calendar, or project management tools, to provide additional functionality and context-aware responses.

Emotion-aware responses: 

Implement emotion detection in the text to help the chatbot better understand the user's feelings and respond more empathetically.
