# n8n CT-e Automation Workflow

This repository contains an n8n automation workflow designed to automatically generate a **Conhecimento de Transporte Eletrônico (CT-e)** for transport and logistics businesses.  
The workflow processes fiscal inputs, validates data, and automates CT-e creation through a web system.

## 🧠 Problem Solved

In transport logistics operations, issuing a CT-e manually is time-consuming and error-prone. Operators must handle NFe access keys, document images, OCR extraction, XML validation, and repetitive form filling in third-party or government systems.

This workflow solves that problem by fully automating the CT-e creation process, reducing manual effort, minimizing errors, and significantly speeding up logistics operations.

## 💡 Workflow Summary

- The workflow is executed by another workflow and receives an input that can be either:
  - An **NFe access key (numeric)**, or
  - An **image** containing NFe information.
- If the input is an image, the workflow uses the **Google Vision OCR API** to extract the NFe access key.
- The extracted or provided key is validated and used to search and retrieve the corresponding **NFe XML** via an external API.
- A **debounce mechanism** is applied to handle cases where a CT-e includes **multiple NFe keys**, ensuring all data is processed before continuing.
- After validation and aggregation, a **Playwright automation script** is executed.
- The script accesses a web application and automatically fills and submits the **CT-e form**, completing the document creation process without manual interaction.

## 📸 Workflow Preview

<img width="1496" height="541" alt="image" src="https://github.com/user-attachments/assets/9ad18991-5e08-429c-aa71-114dca80bd32" />
