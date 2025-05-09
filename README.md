# WhatsChat - WhatsApp Terminal Interface

A powerful command-line interface for WhatsApp messaging using the Green API.

## Features

- 📥 View incoming messages
- 📤 View outgoing messages 
- 📊 Filter messages by contact
- 👥 Full contact management
- 🔍 Search by name or phone number
- 📱 Send messages from terminal
- 🤖 Integrate with GPT for AI-assisted replies
- 📡 Real-time message monitoring
- 👪 Group message support

## Installation

### Requirements

```bash
pip install -r requirements.txt
```

### API Configuration

WhatsChat requires Green API credentials to function. You need to:

1. Create an account on [Green API](https://green-api.com/en)
2. Set up your WhatsApp instance
3. Export your credentials as environment variables:

```bash
export GREENAPI_ID_INSTANCE='YOUR_INSTANCE_ID_HERE'
export GREENAPI_API_TOKEN='YOUR_API_TOKEN_HERE'
```

For AI integration, set your OpenAI API key:

```bash
export OPENAI_API_KEY='your-api-key-here'
```

## Usage

### Basic Message Viewing

```bash
# Get all messages from the last 20 minutes (default)
./whatschat -c

# Get messages from the last hour
./whatschat -c -t 60

# Show only outgoing messages
./whatschat -o

# Show only incoming messages
./whatschat -r
```

### Filtering Messages

```bash
# Filter by contact name
./whatschat -c -i "John"

# Filter by phone number
./whatschat -c -i 1234567890

# Include messages from groups
./whatschat -c -g
```

### Real-Time Message Monitoring

```bash
# Monitor all messages in real-time
./whatschat -m

# Monitor messages from a specific contact
./whatschat -m -i "Alice"
```

### Sending Messages

```bash
# Send a message to a contact
./whatschat -s -i "Bob" --text "Hello Bob!"
```

### AI Integration

```bash
# Send text to GPT and forward the response to a contact
./whatschat -a -i "Charlie" --text "Write a professional excuse for being late"
```

## Command Line Options

```
-c, --chat       Show chat history (incoming and outgoing)
-o, --outgoing   Show only outgoing messages
-r, --receiving  Show only incoming messages
-m, --monitor    Monitor for new messages in real-time
-s, --send       Send a message to a specific contact
-a, --ai         Use GPT to generate and send a message

-t, --time       Time in minutes to fetch messages for (default: 20)
-i, --identifier Filter or target contact (name or number)
-g, --groups     Include group messages (default: exclude groups)
--text           Message text to send (used with -s/--send or -a/--ai)
```

## Advanced Usage

### Contact Selection

If multiple contacts match your query, WhatsChat will display a list for you to choose from:

```
Multiple contacts found matching 'John':
[1] John Smith (1234567890)
[2] John Doe (0987654321)

Please enter the number of the correct contact (or 'q' to quit):
```

### Error Handling

WhatsChat provides helpful error messages and graceful handling of issues like:
- Missing API credentials
- Network connectivity problems
- API rate limiting
- Invalid contacts
- Missing command arguments

## Author

Created by [Yaniv Haliwa](https://github.com/YanivHaliwa) for security testing and educational purposes.
