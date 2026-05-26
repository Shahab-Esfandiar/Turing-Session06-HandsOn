# 👁️ AI Vision: Screen-to-Code Generator
This project is an advanced Vision-Language Model (VLM) engineering tool designed to demonstrate how multi-modal Large Language Models can bridge the gap between design and development. It acts as an automated "AI Frontend Engineer," analyzing uploaded UI screenshots or hand-drawn wireframes and dynamically generating pixel-perfect, production-ready HTML, CSS, and JavaScript.

<img width="1175" height="831" alt="image" src="https://github.com/user-attachments/assets/69f15919-cb86-47b8-96fe-55ebdfa214a2" />


## ✨ Key Features

**🧠 Vision-Powered Analysis:** Uses advanced multi-modal prompt engineering to analyze image pixels, extract layout structures, identify color palettes, and recreate exact typography and spacing.

**🎨 Multi-Framework Support:** Seamlessly generates frontend code using **Tailwind CSS**, **Bootstrap 5**, or **Vanilla CSS** based on user selection.

**🖥️ Interactive Dashboard & Dynamic Loader:** Features a modern `ipywidgets` interface complete with a non-blocking, CSS-animated loading spinner to provide real-time user feedback during heavy API processing.

**📊 Live Cost Analytics:** Transparently tracks multi-modal Prompt (image + text) and Completion tokens, rendering a real-time financial cost estimation table upon completion.

**🛡️ Robust Error Handling:** Features a custom exception management system with 180-second strict timeouts and exponential backoff retry logic, allowing the system to survive network drops during intensive vision tasks.

**🧩 Single-File Compilation:** Automatically structures the generated code into a single, ready-to-run `.html` file (with embedded `<style>` and `<script>` tags) for rapid prototyping.

## 🎨 Supported UI Frameworks (Generation Logic)

The AI categorizes and builds the frontend architecture using one of the following requested frameworks:

1. `Tailwind CSS` -> **Utility-First** (Injects Tailwind via CDN, uses arbitrary values for exact color matching)
2. `Bootstrap 5` -> **Component-Based** (Utilizes standard Bootstrap grids, cards, and utility classes via CDN)
3. `Vanilla CSS` -> **Pure CSS** (Builds custom, scoped CSS classes without any external dependencies)

---

## 🛠️ Main Services

* **Pixel-Perfect Replication:** Analyzes grid structures, visual hierarchy, and UI components to recreate the exact design presented in the source image.
* **Base64 Image Encoding:** Securely processes and converts raw uploaded binary image data into standard Base64 format for seamless multi-modal API integration.

### 🌐 Precision Image Processing
* **Deterministic Code Generation:** Utilizes a highly optimized, low-temperature (`0.2`) API configuration specifically designed to prevent LLM hallucination and ensure strict adherence to the visual source material.
* **Regex Sanitization:** Automatically detects and strips unwanted Markdown wrappers (e.g., ` ```html `) from the AI's response to ensure the output is pure, executable code.

### 📥 Automated Project Export
* **Rapid Prototyping Engine:** Bypasses manual copy-pasting by automatically compiling the AI-generated code and saving it directly as a formatted `.html` file into an isolated `Outputs/` directory.
* **Smart Naming Convention:** Dynamically names the output files based on the original image name and the selected framework (e.g., `UI_Code_Screenshot_TailwindCSS.html`).

### 🔒 Security & Standards
* **Environment Management:** Uses `python-dotenv` to keep API keys and server credentials completely secure and out of the version control system.
* **OOP Architecture:** Clean, object-oriented code encapsulated within the `VisionFrontendEngineer` class for enterprise-grade readability, developer experience, and maintainability.

---

## 🚀 How to Run

1. **Clone the Repo**
2. **Setup Virtual Environment & Install Requirements:**

   ```bash
   python -m venv venv
   # Windows: .\venv\Scripts\activate
   pip install openai ipywidgets python-dotenv
   ```
3. **Setup Environment:**
*Create a .env file in the root directory and add your credentials:*

   ```env
   # API Configurations
   AVALAI_API_KEY=your_api_key_here
   AVALAI_BASE_URL=[https://api.avalai.ir/v1](https://api.avalai.ir/v1)
   ```
4. **Launch Jupyter Notebook:** *Open the notebook, run the initialization cells, and use the interactive dashboard to upload your UI screenshot and generate code.*

---

## 🛠️ Tech Stack
* **Language:** Python 3.8+
* **AI Providers:** OpenAI API Interface (gpt-4o Vision capabilities via Avalai)
* **Core Libraries:** base64, re, os, ipywidgets, time
* **Environment & Security:** python-dotenv
* **Architecture Style:** Object-Oriented Programming (OOP), Multi-Modal AI Pipeline
