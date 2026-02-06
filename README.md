# 🧹 AI Code Standardizer

A modern desktop application that uses **Local LLMs (Large Language Models)** to automatically refactor and standardize legacy C/C++ code. It turns "Spaghetti Code" into readable "Clean Code" without changing the underlying logic—**100% locally and offline** for maximum source code security.

---

## 📸 Screenshots

<p align="center">
<img src="img/screen_main.png" width="30%" alt="Main Interface" />
<img src="img/screen_processing.png" width="30%" alt="AI Processing" />
<img src="img/screen_result.png" width="30%" alt="Result" />
</p>

---

## ✨ Features

* **🛡️ Logic Preservation:** The AI is strictly instructed to format code and rename variables *without* altering the program's logic or functionality.
* **🧠 Intelligent Refactoring:** Uses **Qwen 2.5 Coder**, a model specialized in programming, to understand context.
* Renames variables (e.g., `int x` → `int loop_counter`).
* Fixes indentation and bracket styles (Google/K&R Style).
* Adds comments to complex logic blocks.


* **🔒 100% Privacy:** No code is sent to the cloud (unlike ChatGPT). Perfect for proprietary or sensitive source code.
* **⚡ Modern UI:** Built with `CustomTkinter` for a professional dark-mode experience.
* **📂 Auto-Save:** Automatically creates a new file (e.g., `main_standardized.c`) next to the original one.

---

## 🛠️ Prerequisites

Before running the application, you need to set up the AI Engine.

### 1. Install Ollama

This application relies on **Ollama** to run the AI model locally.

1. Download Ollama from [ollama.com](https://ollama.com/download).
2. Install it and ensure it is running (check for the icon in your taskbar).

### 2. Download the Coding Model

Open your terminal (CMD/PowerShell) and pull the specific coding model:

```bash
ollama pull qwen2.5-coder:3b

```

*(Note: You can also use `qwen2.5-coder:7b` for even better results if you have >16GB RAM. Just update `core/analyzer.py` accordingly.)*

---

## 🚀 Installation & Usage

### 1. Clone the Repository

```bash
git clone https://github.com/code-standardizer.git
cd code-standardizer

```

### 2. Install Dependencies

```bash
pip install -r requirements.txt

```

### 3. Run the App

```bash
python main.py

```

### 4. How to use

1. Click **"C-Datei wählen"** and select a messy `.c` or `.cpp` file.
2. Click **"Code formatieren"**.
3. Wait for the AI to process (Progress bar will run).
4. The cleaned file will be saved automatically (e.g., `legacy_code_standardized.c`).

---

## 📦 Building an Executable (.exe)

If you want to share this tool with your team without requiring them to install Python:

1. Make sure you have installed the requirements.
2. Run the build command:

```bash
pyinstaller --noconsole --onefile --add-data "PATH_TO_CUSTOMTKINTER;customtkinter/" main.py

```

*Note: The user of the .exe still needs Ollama installed on their machine!*

---

## 📂 Project Structure

```text
AI-Code-Standardizer/
├── core/                   # Business Logic
│   ├── analyzer.py         # AI Interaction (Qwen Coder)
│   ├── exporter.py         # File Saving Logic
│   └── file_handler.py     # C-File Reading & Encoding Fixes
├── ui/                     # User Interface
│   └── main_window.py      # Main GUI (CustomTkinter)
├── img/                    # Screenshots for README
├── main.py                 # Entry Point
├── config.py               # App Configuration
└── requirements.txt        # Python Dependencies

```

---

## 🛡️ Disclaimer

While the AI model is highly capable, **always review the standardized code** before deploying it to production. The tool is designed to assist developers, not replace them.

---

## 📝 License

This project is open source under the [MIT License](https://www.google.com/search?q=LICENSE).

---
