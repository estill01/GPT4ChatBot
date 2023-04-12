# 👾 GPT4ChatBot

> Not keen on 25 GPT-4 prompts every 3 hours? Me neither! Welcome to the free world.

Like every other dev on the planet, I built a quick GPT4 chat bot to get around the extreme ChatGPT web ui rate limiting.
Feel free to use this package, or go build your own bot (it's a modern dev rite of passage you know).

## Features
🤹‍♀️ Conduct and manage multiple chat threads

🌲 Branch chat threads wherever and whenever you want

- Now you can zig _AND_ zag

✅ Save all data locally in an easy to parse structure.

🧠 Auto chat content summary generation

- "What you've been talking about recently" breakpoint summaries
- Multi-level auto higher-order summaries

📐 Chat telemetry
- duration, msg count, context length, ...

🚿  Block and streaming output to file or `stdout`

🤖 Preliminary support for `modes` to change system behaviors
- E.g. overwrite changes in doc vs append-only


## Usage
Initialize it with your OpenAI API key and start creating and managing chats


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

## TODO

These are individually pretty trivial to implement; Will add them as I have time.

### 🔎 Search

#### Keyword

Allow users to search for specific keywords or phrases within the chat messages across all branches. The chatbot can then display a list of matching branches or conversations, along with a brief summary or relevant excerpt for each.

#### Chronological

Enable users to navigate the chat history based on time or events, such as "go back to before we branched" or "go to the branch created on [date]". The chatbot can analyze the chat metadata to identify the appropriate branch or conversation and switch to it.

#### Topic-based / Semantic 

Implement a topic detection system that identifies the main topic or subject of each chat branch or conversation. Users can then search for chats based on these topics, such as "go to the branch where we explored xyz".

#### Emotion-based

Search by how you felt at the time. "It was a lively conversation", "I remember being upset at the time", ...

#### Event-based

"We had recently been talking about ...", "{External world event} had just happened", ...   

### 🗣 Speech UI
Integrate microphone + speaker access and run Text-to-Speech and Speech-to-Text.

### 👨‍👩‍👦‍👦 Profiles

#### User Profiles
Create and manage User profiles which store preferences, chat history, and other personalization settings.

#### Bot Profiles
Dynamically switch between 'fine tuning' bot profiles. Manage multiple instances of the bot.


### 😊 Sentiment analysis

Implement sentiment analysis to gauge the mood of the user during the conversation. The chatbot could adjust its responses accordingly to maintain a positive and engaging experience, or other objectives.

### 🌏 Language translation

Add a translation feature that allows users to communicate with the chatbot in their preferred language + enables the bot to translate content. Auto-detect and translate messages into the desired language.

### 🎯 Topic-based suggestions

Detect the topic of conversation and offers relevant suggestions or information to the user. 

### 👻 Bot-initiated prompts
Enable the bot to start conversations. (Hype don this / I should implement this..)

### 🎉 Multi-user conversations

Enable the bot to handle multi-user conversations where multiple people can interact with the bot and each other in the same chat thread. I.e. give it the ability to spawn an IRC / Discord server and jump in it.

### 🏋️‍♂️ Chatbot training

Enable the bot to process user-input and update it's `system` prompts to improve its informatation processing and response genreation.

### ⏰ Cron-style scheduled prompts

Schedule prompts to be sent at specific times or intervals. Useful for reminders, follow-ups, periodic check-ins, etc.

### 🛠 Integration with external services

Load it up with APIs / Integrate the auto-API finder project so it can do all the things.

### 🫠 Emotion-aware responses

Augment sentiment analysis with 'emotion detection' to better navigate user-interactions. Probably go all-in and also give the bot emotions. (lol?)
