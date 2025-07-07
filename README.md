---
title: career_conversation
app_file: app.py
sdk: gradio
sdk_version: 5.35.0
---

# IzzBot - AI Career Assistant

A personalized AI chatbot that represents Izzham Burhan for career-related interactions on his website. The bot uses OpenAI's GPT-4 to provide professional responses based on Izzham's background, experience, and credentials.

## 🚀 Features

- **Personalized AI Assistant**: Acts as Izzham Burhan, answering questions about his career, background, skills, and experience
- **Professional Interaction**: Designed to engage with potential clients or future employers professionally
- **Contact Management**: Automatically records user details when they express interest in getting in touch
- **Question Tracking**: Logs questions that couldn't be answered for future reference
- **Real-time Notifications**: Sends notifications via Pushover when users interact or provide contact information
- **Web Interface**: Clean Gradio-based chat interface for easy interaction

## 📋 Prerequisites

- Python 3.8 or higher
- OpenAI API key
- Pushover account (for notifications)
- Personal documents (resume, LinkedIn profile, summary)

## 🛠️ Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd cBots
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv cbot_env
   # On Windows
   cbot_env\Scripts\activate
   # On macOS/Linux
   source cbot_env/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   Create a `.env` file in the root directory:
   ```env
   OPENAI_API_KEY=your_openai_api_key_here
   PUSHOVER_TOKEN=your_pushover_token_here
   PUSHOVER_USER=your_pushover_user_key_here
   ```

5. **Prepare personal documents**
   Place your documents in the `me/` directory:
   - `Profile.pdf` - LinkedIn profile export
   - `Muhammad Ariff Izzham - resume.pdf` - Resume/CV
   - `summary.txt` - Personal summary and background

## 🚀 Usage

### Running the Application

```bash
python app.py
```

The application will start a local web server (usually at `http://127.0.0.1:7860`).

### Using the Chat Interface

1. Open your browser and navigate to the provided URL
2. Start chatting with the AI assistant
3. The bot will respond as Izzham Burhan, using information from your documents
4. When users provide contact information, it will be automatically recorded and you'll receive a notification

## 📁 Project Structure

```
cBots/
├── app.py                 # Main application file
├── requirements.txt       # Python dependencies
├── README.md             # This file
├── .env                  # Environment variables (create this)
├── .gitignore           # Git ignore rules
├── me/                   # Personal documents directory
│   ├── Profile.pdf       # LinkedIn profile
│   ├── Muhammad Ariff Izzham - resume.pdf  # Resume
│   └── summary.txt       # Personal summary
└── notebook/             # Development notebooks
    ├── 001_Linkedin_Profile.ipynb
    └── 100_izzbot_dev.ipynb
```

## 🔧 Configuration

### Environment Variables

- `OPENAI_API_KEY`: Your OpenAI API key for GPT-4 access
- `PUSHOVER_TOKEN`: Pushover app token for notifications
- `PUSHOVER_USER`: Pushover user key for notifications

### Customization

To customize the bot for a different person:

1. Update the `name` variable in the `Me` class
2. Replace the documents in the `me/` directory
3. Modify the system prompt in the `system_prompt()` method
4. Update the summary text to reflect the new person's background

## 🤖 How It Works

1. **Document Processing**: The bot extracts text from PDF documents (resume and LinkedIn profile) and reads the summary file
2. **Context Building**: All personal information is compiled into a comprehensive system prompt
3. **AI Interaction**: Uses OpenAI's GPT-4 to generate responses based on the provided context
4. **Tool Integration**: Implements custom tools for:
   - Recording user contact details
   - Logging unanswered questions
5. **Notification System**: Sends real-time notifications via Pushover when important events occur

## 📊 Tools and Functions

### `record_user_details`
- **Purpose**: Records when users provide contact information
- **Parameters**: email, name, notes
- **Action**: Sends notification with user details

### `record_unknown_question`
- **Purpose**: Logs questions the bot couldn't answer
- **Parameters**: question
- **Action**: Sends notification with the unanswered question

## 🔒 Security and Privacy

- API keys are stored in environment variables (not in code)
- Personal documents should be kept secure
- User data is only used for notification purposes
- No persistent storage of user conversations

## 🐛 Troubleshooting

### Common Issues

1. **"Invalid value for 'content': expected a string, got null"**
   - Check that all documents in the `me/` directory are readable
   - Ensure the summary.txt file exists and has content

2. **OpenAI API errors**
   - Verify your API key is correct and has sufficient credits
   - Check that you're using a supported model

3. **Pushover notifications not working**
   - Verify your Pushover credentials in the .env file
   - Check that the Pushover app is properly configured

## 📝 Development

### Development Notebooks

- `001_Linkedin_Profile.ipynb`: LinkedIn profile processing and analysis
- `100_izzbot_dev.ipynb`: Development and testing of the bot functionality

### Adding New Features

1. Create new tool functions in `app.py`
2. Add corresponding JSON schemas to the `tools` list
3. Update the `handle_tool_call` method to handle new tools
4. Test thoroughly before deployment

## 📄 License

This project is for personal use. Please ensure you have the right to use any personal information and documents included.

## 🤝 Contributing

This is a personal project, but suggestions and improvements are welcome. Please ensure any changes maintain the privacy and security of personal information.

## 📞 Support

For issues or questions related to this project, please check the troubleshooting section above or create an issue in the repository.

---

**Note**: This bot is designed to represent a specific individual professionally. Always ensure that the information provided is accurate and up-to-date, and that you have permission to use any personal information in this context.
