# GPT Commit Message Generator

A shell script that leverages OpenAI's GPT models to generate descriptive Git commit messages based on your staged changes. Enhance your Git workflow by automating commit message creation, with options to accept, edit, or regenerate messages as needed.

---

## 🌟 Features

- **AI-Powered Commit Messages**: Generates concise and meaningful commit messages using OpenAI's GPT models.
- **Interactive Workflow**: Allows you to accept, edit, or regenerate commit messages before committing.
- **Customizable**: Adjust the prompt, model parameters, and editor to suit your preferences.
- **Error Handling**: Includes checks for API errors and ensures you have staged changes before proceeding.

---

## 🚀 Getting Started

### 📋 Prerequisites

- **Git**: Ensure Git is installed and initialized in your repository.
- **Bash**: The script is written for Bash shell environments.
- **OpenAI API Key**: Obtain an API key from [OpenAI](https://platform.openai.com/signup/).
- **jq**: Command-line JSON processor.
  - **macOS**: `brew install jq`
  - **Ubuntu/Debian**: `sudo apt-get install jq`
- **curl**: For making HTTP requests (usually pre-installed).

### 🔐 Secure Your OpenAI API Key

1. **Set Your API Key as an Environment Variable**

   ```bash
   export OPENAI_API_KEY="your-openai-api-key"
   ```

   - Replace `"your-openai-api-key"` with your actual OpenAI API key.
   - **Note**: Do not share or commit your API key to any repositories.

2. **Add to Shell Configuration**

   - Add the export command to your `~/.bashrc` or `~/.bash_profile` to persist the variable.

   ```bash
   echo 'export OPENAI_API_KEY="your-openai-api-key"' >> ~/.bashrc
   ```

   - Reload your shell configuration:

     ```bash
     source ~/.bashrc
     ```

---

## 📥 Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/strathausen/gpt_commit.git
   ```

2. **Navigate to the Directory**

   ```bash
   cd gpt_commit
   ```

3. **Make the Script Executable**

   ```bash
   chmod +x gpt_commit
   ```

4. **Add the Script to Your PATH**

   - Option 1: Copy or symlink the script to a directory that's already in your `PATH`, such as `/usr/local/bin`.

     ```bash
     sudo ln -s "$(pwd)/gpt_commit" /usr/local/bin/gpt_commit
     ```

   - Option 2: Add the script's directory to your `PATH`.

     ```bash
     echo 'export PATH="$PATH:'"$(pwd)"'"' >> ~/.bashrc
     source ~/.bashrc
     ```

---

## 🛠 Usage

### 1. **Stage Your Changes**

```bash
git add .
```

*Or add specific files:*

```bash
git add filename.py
```

### 2. **Run the Script**

```bash
gpt_commit
```

*If you added the script to your `PATH` as `gpt_commit`, you can run:*

```bash
gpt_commit
```

### 3. **Interact with the Script**

- The script will generate a commit message based on your staged changes.
- You'll be presented with options:

  ```
  Generated commit message:
  "Add input validation to prevent null pointer exceptions"

  Options:
    (y) Accept and commit
    (e) Edit message
    (r) Regenerate message
    (q) Abort
  Choose an option [y/e/r/q]:
  ```

- **(y) Accept and commit**: Commits with the generated message.
- **(e) Edit message**: Opens your default editor to modify the message.
- **(r) Regenerate message**: Gets a new message from the OpenAI API.
- **(q) Abort**: Exits without committing.

---

## ⚙️ Configuration

### 🔧 Customize the Script

- **Model Parameters**:
  - Modify `max_tokens` to control the message length.
  - Adjust `temperature` for creativity (range: 0 to 1).

- **Change the Prompt**:
  - Edit the `prompt` variable in the script to alter the AI's instructions.

    ```bash
    prompt="As an expert developer, generate a clear and concise Git commit message for the following changes:\n\n$diff"
    ```

### 🖊 Set Your Preferred Editor

- The script uses the `EDITOR` environment variable.

- **Set `EDITOR` in your shell configuration**:

  ```bash
  export EDITOR="vim"  # or "nano", "code --wait", etc.
  ```

- **Reload Configuration**:

  ```bash
  source ~/.bashrc
  ```

---

## 🔒 Security Considerations

- **API Key Safety**:
  - Keep your OpenAI API key private.
  - Do not share or commit it to version control systems.

- **Review Messages**:
  - Always review generated commit messages for accuracy and appropriateness.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork the Repository**

   ```bash
   git fork https://github.com/strathausen/gpt_commit.git
   ```

2. **Create a Feature Branch**

   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Commit Your Changes**

   ```bash
   git commit -am "Add new feature"
   ```

4. **Push to the Branch**

   ```bash
   git push origin feature/your-feature-name
   ```

5. **Open a Pull Request**

---

## 📞 Support

If you encounter any issues or have questions, please open an [issue](https://github.com/strathausen/gpt_commit/issues) on GitHub.

---

## 🌐 References

- **OpenAI API Documentation**: [https://platform.openai.com/docs/api-reference](https://platform.openai.com/docs/api-reference)
- **jq Manual**: [https://stedolan.github.io/jq/manual/](https://stedolan.github.io/jq/manual/)

---

## 🎉 Acknowledgments

- Inspired by the need to streamline Git workflows and write better commit messages effortlessly.
- Thanks to the OpenAI community for their continuous support and innovation.

---

*Note: Replace `strathausen` with your actual GitHub username in the repository URLs.*
