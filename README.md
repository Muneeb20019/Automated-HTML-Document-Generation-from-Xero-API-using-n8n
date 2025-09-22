# Automated HTML Document Generation from Xero API Data using n8n

An automated workflow built in n8n that integrates data from the Xero API, uses a Large Language Model (LLM) for intelligent structuring, and generates styled HTML documents for storage in Google Drive.

## Objective

The primary goal is to replace a manual copy-and-paste process with an efficient, automated workflow. This saves significant time, eliminates data entry errors, and ensures all documents have a consistent, professional appearance.

---

## Workflow Architecture

The following diagram provides a high-level overview of the automation's node-based architecture.
## Workflow Architecture

The following diagram provides a high-level overview of the automation's node-based architecture.

![Xero Invoice Workflow](https://raw.githubusercontent.com/Muneeb20019/Automated-HTML-Document-Generation-from-Xero-API-using-n8n/main/Xero%20Invoice.jpeg)

---

## Technical Breakdown

The workflow operates in a clear, step-by-step sequence:

1.  **Manual Trigger:** The workflow is started on-demand with a single click. It could easily be adapted to run automatically in response to an event, such as a new invoice being created.

2.  **API Integration with Xero:** The workflow securely connects to the **Xero API** using stored credentials. It fetches the complete data for a specific invoice, which is received as a structured **JSON payload**.

3.  **AI-Powered Data Structuring:** The raw JSON data is sent to an **AI model (like OpenAI's GPT)** with a specific instruction, or "prompt." The AI reads the complex data, extracts only the key details needed (like name, date, and line items), and formats them into a simple and clean **markdown table**.

4.  **HTML Conversion & Styling:** A code node uses **JavaScript and Regular Expressions (RegEx)** to convert the AI's markdown table into a proper **HTML5** structure. In-line CSS is used at this stage to apply styling for colors, spacing, and borders, ensuring the final document looks polished.

5.  **File Creation in Google Drive:** The finished HTML is sent to the **Google Drive API**. A new file is created in a specific folder, and the workflow writes the HTML content into it, creating the final, viewable document.

---

## Technologies Utilized

*   **Automation Platform:** [n8n.io](https://n8n.io/)
*   **AI Language Model:** OpenAI API (GPT-4 / GPT-3.5)
*   **Data Source:** Xero REST API
*   **File Storage:** Google Drive API

## Technical Highlights

*   **API Integration:** Connecting to and retrieving data from REST APIs (using OAuth 2.0).
*   **ETL Pipeline Design:** Building a logical flow to Extract, Transform, and Load data.
*   **Prompt Engineering:** Instructing an AI model to perform a specific data transformation task.
*   **Data Structuring:** Working with and converting data formats (JSON, Markdown, HTML).
*   **Code & Expressions:** Using JavaScript and RegEx for precise data manipulation.
*   **Workflow Automation:** Designing and building end-to-end automated processes.
