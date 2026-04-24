# ⚡ Discord Rizzler

A sophisticated (and slightly chaotic) Discord bot ecosystem designed to automate "rizz" and roasts using both simple randomization and advanced Markov Chain text generation.

---

## 🎯 Project Aim
The **Discord Rizzler** aims to provide a modular framework for creating interactive Discord bots that can respond to users with generated text. Whether you want to deliver perfectly timed roasts using pre-defined word lists or generate surreal, context-aware replies using Markov Chains, this project provides the foundation.

---

## 📂 File Breakdown

### 1. `markov.py`
The brain behind the generation. This is a standalone utility class that implements a **Markov Chain** algorithm.
- **Functionality**: It reads a source text file (training data), builds a probability map of character sequences (n-grams), and generates new text that mimics the style of the input data.
- **Core Logic**: Uses a hash map to store possibilities for each gram and selects the next character randomly based on those possibilities.

### 2. `markovGeneratedreplyBot.py`
A Discord bot implementation that leverages the Markov Chain brain.
- **Functionality**: Listens for a specific trigger command and replies with a message generated on-the-fly by the Markov utility.
- **Customization**: Highly dependent on the quality and quantity of your `trainingData`.

### 3. `replyBot.py`
A lighter, faster, and more direct "rizz/roast" bot.
- **Functionality**: Uses simple list-based randomization to construct sentences.
- **Classic Use-Case**: Combines names and words from external files to create funny (or insulting) replies like: *"Chup kar [Name] ke [Word]"*.

---

## 🚀 Local Setup (No Docker)

Follow these steps to get the bot running on your local machine.

### 1. Prerequisites
- **Python 3.8+** installed.
- A **Discord Bot Token** (Get it from the [Discord Developer Portal](https://discord.com/developers/applications)).
- Necessary text files for data (e.g., `training.txt`, `names.txt`, `words.txt`).

### 2. Install Dependencies
Run the following command in your terminal:
```bash
pip install discord.py
```
*(Alternatively, use the `requirements.txt` if provided)*

### 3. Configuration
You **must** edit the script files to include your specific details. Look for the following placeholders:

#### For `markovGeneratedreplyBot.py`:
- `trainingData`: Path to your text file for training.
- `INSERT_TRIGGER`: The command that makes the bot reply.
- `INSERT_API_TOKEN`: Your Discord bot token.

#### For `replyBot.py`:
- `INSERT_WORD_LIST_LOCATION`: Path to your words file.
- `INSERT_NAME_LIST_LOCATION`: Path to your names file.
- `INSERT_API_TOKEN_KEY`: Your Discord bot token.

### 4. Running the Bot
Open your terminal in the project directory and run:

**To run the Markov Bot:**
```bash
python markovGeneratedreplyBot.py
```

**To run the Simple Reply Bot:**
```bash
python replyBot.py
```

---

## 🛠️ Requirements
- `discord.py`

---

## ⚠️ Disclaimer
This project is for educational and entertainment purposes. Ensure your bot's behavior complies with Discord's Terms of Service and the rules of the servers it joins.
