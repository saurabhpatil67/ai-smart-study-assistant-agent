# 📚 AI Smart Study Assistant

### AI-Powered Lecture Notes & Quiz Automation System

Transform a lecture topic into AI-generated study notes, professional PDF materials, interactive quizzes, Google Forms, and automated student emails—all through a single n8n workflow powered by Gemini Pro.

> 🚀 Built with **n8n**, **Gemini Pro**, **PDF.co**, **Google Forms API**, **Gmail**, and **JavaScript**.

![n8n](https://img.shields.io/badge/n8n-Automation-EA4B71?style=for-the-badge&logo=n8n&logoColor=white)

![Gemini](https://img.shields.io/badge/Google-Gemini_Pro-4285F4?style=for-the-badge&logo=google&logoColor=white)

![JavaScript](https://img.shields.io/badge/JavaScript-ES6-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

![PDF.co](https://img.shields.io/badge/PDF.co-PDF_Generation-blue?style=for-the-badge)

![Google Forms](https://img.shields.io/badge/Google_Forms-Quiz_Automation-34A853?style=for-the-badge&logo=googleforms&logoColor=white)

![Gmail](https://img.shields.io/badge/Gmail-Email_Automation-EA4335?style=for-the-badge&logo=gmail&logoColor=white)

---

## 🚀 Project Overview

AI Smart Study Assistant is an end-to-end workflow automation system that simplifies lecture preparation and student assessment.

Instead of manually writing lecture notes, preparing quizzes, creating PDFs, building Google Forms, and emailing students, teachers only provide a subject and an optional subtopic.

The workflow then automatically:

- Generates structured lecture notes using Gemini Pro
- Creates quiz questions from the generated notes
- Converts notes into a professional PDF
- Builds a Google Form for the quiz
- Links responses to Google Sheets for tracking
- Emails the PDF and quiz link to every student

The entire workflow is orchestrated using n8n, eliminating repetitive manual tasks and significantly reducing preparation time.

---

## 📸 Project Preview

> *(Workflow image / Demo GIF will be added here.)*

---

## 🎯 Problem Statement

Preparing study materials after every lecture is a repetitive and time-consuming task for educators. Beyond teaching, instructors often spend significant time creating summarized notes, designing quizzes, formatting PDFs, distributing study materials, and tracking student participation.

This manual process can lead to:

- ⏳ Time-consuming lecture preparation
- 📝 Repetitive creation of study notes
- ❓ Manual quiz generation
- 📄 Formatting and exporting notes into PDFs
- 📤 Sending study materials individually to students
- 📊 Tracking quiz responses and performance manually

As the number of students and subjects increases, these repetitive tasks reduce the time available for teaching and personalized student support.

An automated solution was needed to streamline the entire post-lecture workflow while maintaining consistency and accuracy.

---

## 💡 Solution

AI Smart Study Assistant automates the complete lecture material preparation process using AI and workflow automation.

The teacher simply provides the lecture **subject** and an optional **subtopic**. From that single input, the workflow performs every remaining task automatically.

The system:

- 📚 Generates AI-powered summarized lecture notes using Gemini Pro
- ❓ Creates quiz questions based on the generated notes
- 📄 Converts the notes into a professionally formatted PDF
- 📝 Automatically creates a Google Form quiz
- 📊 Links the Google Form with Google Sheets for response tracking
- 📧 Emails the study notes and quiz link to all students

The entire pipeline is orchestrated using n8n, significantly reducing manual effort while ensuring every student receives consistent learning materials.

---

## ✨ Key Features

- 🤖 AI-generated lecture summaries using Gemini Pro
- 📚 Supports both subject and optional subtopic inputs
- ❓ Automatic quiz generation from summarized notes
- 📄 Professional PDF creation using PDF.co
- 📝 Automatic Google Form creation via API
- 📊 Google Sheets integration for quiz response tracking
- 📧 Bulk email delivery of study materials through Gmail
- 🔀 End-to-end workflow orchestration with n8n
- ⚡ Fully automated pipeline requiring minimal teacher input
- 📈 Scalable workflow for classrooms with multiple students

---

## 🛠️ Technology Stack

| Technology | Purpose |
|------------|---------|
| **n8n** | Orchestrates the complete workflow by connecting AI services, APIs, and automation steps into a single pipeline. |
| **Gemini Pro** | Generates AI-powered lecture summaries and creates quiz questions based on the generated notes. |
| **PDF.co** | Converts AI-generated HTML lecture notes into professionally formatted PDF documents. |
| **Google Forms API** | Automatically creates quiz forms from AI-generated questions for student assessments. |
| **Google Sheets** | Stores quiz responses automatically through Google Forms, enabling performance tracking and analysis. |
| **Gmail** | Sends the generated PDF study material and quiz link to all students via email. |
| **HTTP Request** | Integrates external APIs such as Google Forms and PDF.co within the workflow. |
| **JavaScript (Code Node)** | Processes JSON data, formats information, and prepares personalized email data before sending. |

---

## ⚙️ Workflow Overview

The Smart Study Assistant follows a fully automated pipeline that transforms a simple teacher input into complete study materials for students.

```text
Teacher Input
      │
      ▼
AI Summary Generation (Gemini Pro)
      │
      ├──────────────────────┐
      ▼                      ▼
Quiz Generation          PDF Generation
      │                      │
Google Form API         PDF.co
      │                      │
      └──────────┬───────────┘
                 ▼
            Merge Results
                 ▼
        Prepare Student Emails
                 ▼
        Gmail Distribution
                 ▼
Students Receive PDF + Quiz Link
```

The teacher only enters the lecture **subject** and an optional **subtopic**. The workflow automatically handles AI content generation, quiz creation, PDF conversion, Google Form creation, and email distribution without requiring additional manual intervention.

---

## 🔄 End-to-End Workflow

### Step 1 — Teacher Input

The workflow begins when a teacher submits the lecture subject along with an optional subtopic through a simple HTML form.

---

### Step 2 — AI Lecture Summary

Gemini Pro analyzes the provided topic and generates structured, easy-to-understand lecture notes.

---

### Step 3 — Parallel Processing

After the summary is generated, the workflow splits into two independent branches that execute simultaneously.

#### Branch A — Quiz Generation

- AI generates multiple quiz questions from the summarized notes.
- Questions are converted into structured JSON.
- The JSON is sent to the Google Forms API.
- A quiz form is created automatically.
- Google Forms simultaneously creates a linked Google Sheet to collect student responses.

---

#### Branch B — PDF Generation

- The summarized lecture notes are converted into HTML.
- HTML is sent to PDF.co.
- PDF.co generates a professionally formatted PDF.
- The completed PDF is downloaded for distribution.

---

### Step 4 — Merge

The workflow combines:

- Downloaded PDF
- Google Form Quiz Link

into a single output.

---

### Step 5 — Email Preparation

A JavaScript Code node prepares the list of student email addresses and formats the email content.

---

### Step 6 — Student Distribution

The Gmail node automatically sends each student:

- 📄 Lecture Notes (PDF)
- 📝 Google Form Quiz Link

allowing students to immediately begin studying and complete the assessment online.

---

## 🏗️ System Architecture

The Smart Study Assistant is built as an event-driven automation workflow using **n8n** as the orchestration platform. It integrates multiple AI services, APIs, and cloud applications to automate the complete lecture preparation and distribution process.

### Workflow Components

- **Teacher Input** – Accepts the lecture subject and optional subtopic.
- **Gemini Pro** – Generates lecture summaries and quiz questions.
- **PDF.co** – Converts summarized notes into PDF documents.
- **Google Forms API** – Creates quizzes automatically.
- **Google Sheets** – Stores student quiz responses.
- **Code Node** – Processes JSON data and prepares student email information.
- **Gmail** – Delivers study materials and quiz links to students.

> 📌 The detailed architecture diagram is available below and visually represents the complete workflow.

---

## 📌 Use Case

A teacher wants to prepare study material for the topic **Cloud Computing**.

Instead of manually creating lecture notes, designing a quiz, formatting a PDF, creating a Google Form, and emailing every student, the teacher simply enters:

**Subject:** Cloud Computing

The workflow automatically:

1. Generates AI-powered lecture notes.
2. Creates quiz questions.
3. Builds a Google Form.
4. Generates a professional PDF.
5. Links quiz responses to Google Sheets.
6. Emails the PDF and quiz link to all students.

The complete process is finished automatically with minimal manual effort.

---

## 📸 Workflow Screenshots

The following screenshots highlight the major stages of the Smart Study Assistant workflow.

### Complete Workflow

> *(Complete n8n workflow screenshot will be placed here.)*

---

### HTML Form

> *(HTML form screenshot)*

---

### AI Summary Generation

> *(Gemini Pro Summarization Node)*

---

### Quiz Generation

> *(Quiz Generation Workflow)*

---

### Google Form Creation

> *(HTTP Request + Google Forms API)*

---

### PDF Generation

> *(PDF.co Workflow)*

---

### Gmail Automation

> *(Email Distribution Node)*

---

## 🧩 Node-by-Node Explanation

| Node | Purpose |
|------|---------|
| **HTML Form** | Accepts the lecture subject and optional subtopic from the teacher. |
| **Webhook** | Receives the submitted form data and starts the automation workflow. |
| **Gemini Pro (Summary Agent)** | Generates structured lecture notes from the provided topic. |
| **Gemini Pro (Quiz Agent)** | Creates quiz questions based on the generated lecture summary. |
| **String to JSON** | Converts AI-generated quiz content into structured JSON format. |
| **HTTP Request (Google Forms)** | Creates a Google Form quiz automatically using the generated JSON. |
| **HTML Conversion** | Converts lecture notes into HTML format before PDF generation. |
| **PDF.co** | Generates a professionally formatted PDF from the HTML content. |
| **HTTP Request (Download PDF)** | Downloads the generated PDF for distribution. |
| **Merge** | Combines the PDF and Google Form link into a single workflow output. |
| **Code Node** | Processes student email data and prepares the final email payload. |
| **Gmail** | Sends the lecture PDF and quiz link to all students automatically. |

---

## 🚧 Challenges Faced

Building the Smart Study Assistant involved integrating multiple AI services and APIs into a single automated workflow. During development, several technical challenges were encountered and resolved.

### 1. AI Response Formatting

**Challenge**

Gemini Pro occasionally generated quiz content in an inconsistent format, making it difficult to process automatically.

**Solution**

Implemented a JavaScript Code node to transform the AI response into a structured JSON format before sending it to the Google Forms API.

---

### 2. Google Forms API Payload

**Challenge**

The Google Forms API expects quiz questions in a specific JSON structure. Even small formatting issues prevented form creation.

**Solution**

Validated and transformed the generated JSON before making the HTTP request, ensuring compatibility with the API.

---

### 3. PDF Generation Workflow

**Challenge**

AI-generated lecture notes could not be directly converted into a downloadable PDF.

**Solution**

Converted the lecture notes into HTML and used PDF.co to generate a professional PDF document, which was then downloaded through an HTTP Request node.

---

### 4. Parallel Workflow Synchronization

**Challenge**

Quiz generation and PDF generation run independently but both outputs are required before sending emails.

**Solution**

Used the Merge node to synchronize both branches, ensuring that the workflow proceeds only after the PDF and quiz link are available.

---

### 5. Automated Email Distribution

**Challenge**

The final email required both the generated PDF attachment and the Google Form quiz link while supporting multiple student recipients.

**Solution**

Used a JavaScript Code node to prepare the email payload and student email list before sending personalized emails through Gmail.

---

### 6. End-to-End Workflow Automation

**Challenge**

Managing AI generation, PDF conversion, API requests, email automation, and data synchronization within a single workflow while maintaining reliability.

**Solution**

Designed the workflow using n8n's modular node architecture, allowing each service to perform a dedicated task while ensuring smooth data flow between components.

---

## 📈 Future Improvements

Several enhancements can further improve the Smart Study Assistant:

- 📱 Telegram or WhatsApp integration for instant student notifications.
- 🌍 Multi-language lecture note and quiz generation.
- 🎙️ Voice-based lecture input using speech-to-text.
- 📊 Interactive analytics dashboard for student performance.
- 🎯 Personalized quizzes based on previous quiz results.
- 📚 Automatic storage of generated study materials in Google Drive.
- 🧠 Support for multiple AI models such as OpenAI GPT and Claude.
- 🎥 Automatic generation of presentation slides from lecture notes.
- 🔐 User authentication for teachers and students.

---

## 🎯 Key Learnings

Developing the AI Smart Study Assistant strengthened my understanding of:

- Workflow automation using n8n
- Prompt engineering for AI-generated educational content
- AI integration with Gemini Pro
- REST API integration using HTTP Request nodes
- Google Forms automation
- PDF generation workflows
- JSON data transformation using JavaScript
- Email automation with Gmail
- Workflow branching and synchronization using Merge nodes
- Designing scalable AI-powered automation systems

---

## 📊 Project Impact

By automating repetitive academic tasks, the AI Smart Study Assistant significantly reduces the time teachers spend preparing and distributing study materials.

### Benefits for Teachers

- ⏱️ Reduces manual lecture preparation time
- 🤖 Automates note and quiz generation
- 📄 Eliminates repetitive PDF creation
- 📧 Automates distribution of study materials
- 📊 Simplifies quiz response tracking

### Benefits for Students

- 📚 Receive structured study notes instantly
- 📝 Access interactive quizzes through Google Forms
- 📄 Download professionally formatted PDF notes
- 📩 Receive all learning resources directly via email

This workflow demonstrates how AI and workflow automation can simplify educational processes while improving productivity and consistency.

---

## 👨‍💻 Author

**Saurabh  A. Patil**

MCA Student | AI Automation & GenAI Enthusiast

Passionate about building AI-powered workflow automation systems using Large Language Models (LLMs), n8n, APIs, and modern automation tools to solve real-world problems.

### Connect with me

- 💼 LinkedIn: *(Add your LinkedIn URL)*
- 🐙 GitHub: *(Add your GitHub URL)*

---

## 📄 License

This project is licensed under the MIT License.

You are welcome to explore the project for learning and inspiration. Please provide appropriate credit if you reference or adapt any part of this work.

---

## 🌟 Support

If you found this project helpful or interesting, consider giving it a ⭐ on GitHub. Your support motivates me to continue building and sharing AI automation projects.

