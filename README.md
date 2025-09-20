### The Great Loop Yacht Selection Guide

### Project Overview

The **Great Loop Yacht Selection Guide** is a two-page web application designed to help prospective "Loopers" choose the ideal motor yacht for their journey. The project consists of two linked pages: a **Yacht Selector** and a **Visual Infographic**.

The **Yacht Selector** is an interactive filtering tool that helps users find suitable yachts based on critical parameters like air draft, water draft, length, and fuel range.

The **Visual Infographic** provides a data-rich overview of the Great Loop, highlighting key dimensional constraints, popular vessel types, and essential onboard technology. It also features a **Looper AI Assistant** powered by a large language model to provide instant checklists and answer user questions about the journey.

---

### Page 1: Yacht Selector (`index.html`) 🛥️

#### ✨ Key Features

* **Interactive Filters**: Users can dynamically filter a database of motor yachts by entering their desired **max air draft**, **max water draft**, **max length**, and **min fuel range**.
* **Real-time Results**: The application instantly displays a list of yachts that match the user's criteria, including key specifications and features for each vessel.
* **User-Friendly Interface**: The page is styled with **Tailwind CSS** for a modern, clean, and responsive design. Input fields include helpful hints to guide the user.
* **Dynamic Visibility**: The results section is only shown when the user begins to apply filters, creating a clean initial view.
* **Data-Driven Recommendations**: The application's core logic is a **JavaScript array** containing a curated list of yacht data, making the recommendations accurate and immediate without requiring an external database.

#### 🛠️ Technical Stack

* **Frontend**: HTML, JavaScript, and Tailwind CSS.
* **Data**: A hard-coded **JavaScript array** containing a curated list of motor yacht specifications.
* **Logic**: Pure JavaScript for filtering, rendering, and handling user interface interactions.

---

### Page 2: Visual Infographic (`infog.html`) 📊

#### ✨ Key Features

* **Data Visualization**: The page uses **Chart.js** to create an interactive bar chart and donut chart. These visuals clearly demonstrate critical dimensional limitations for bridges (**air draft**) and waterways (**water draft**).
* **Categorized Information**: Content is structured into clear sections: an **overview** of the Great Loop, a breakdown of **critical dimensions**, a guide to **popular yacht categories**, and a summary of **essential technology**.
* **Looper AI Assistant**: An AI-powered tool allows users to either generate a comprehensive Great Loop preparation checklist or ask a specific question. This feature uses a **large language model (LLM)** for generating dynamic, context-specific content.
* **Responsive Design**: The entire page is designed with Tailwind CSS to be fully responsive and accessible on both desktop and mobile devices.

#### 🛠️ Technical Stack

* **Frontend**: HTML, JavaScript, and Tailwind CSS.
* **Charting Library**: **Chart.js** is used to render the data visualizations.
* **LLM Integration**: The AI features are powered by a **large language model**, which is called via JavaScript functions. This integration handles the generation of dynamic, context-specific content.
