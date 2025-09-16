# Project Development and Troubleshooting: A Case Study

This document outlines the key steps and solutions taken to diagnose and resolve issues with the `Yacht Selection Guide` project, focusing on a non-functional AI assistant tool. The process involved systematic debugging of both the core HTML/JavaScript and the automated GitHub Pages deployment workflow.

-----

### Phase 1: Diagnosing the Initial Problem

The primary challenge was a non-functional AI assistant on the `infog.html` page, which was preventing the display of an AI-generated checklist and question responses. An initial review of the browser's console logs revealed a missing or invalid API key, indicating the core issue was with the JavaScript code itself.

**The Root Cause**: The JavaScript code had a variable name mismatch. It declared the API key using `const apiKey = "YOUR_GEMINI_API_KEY_HERE";` but then attempted to use a different variable name, `GEMINI_API_KEY`, in its `fetch` calls. This caused a `ReferenceError` at runtime.

**The Solution**: The code was updated to use a single, consistent variable name, `GEMINI_API_KEY`, for both the declaration and its subsequent use. Additionally, a redundant variable declaration was removed to clean up the code.

```javascript
// Corrected code with a consistent variable name
const GEMINI_API_KEY = "YOUR_GEMINI_API_KEY_HERE";
```

-----

### Phase 2: Troubleshooting the GitHub Action

After the JavaScript was corrected, the AI tool remained non-functional on the live GitHub Pages site. This indicated that the automated deployment process was failing to correctly inject the API key.

**The Root Cause**: The issue was a subtle configuration error within the GitHub Actions workflow file (`.yml`). The workflow's `sed` command, which is responsible for replacing the API key placeholder, was configured to find the placeholder in `index.html`, while the actual project file was named `infog.html`. This meant the workflow was successfully modifying the wrong file, leaving the correct file unchanged.

**The Solution**: The `sed` command in the workflow file was updated to specifically target `infog.html`.

**Original (Incorrect) Command:**

```bash
sed -i "s/YOUR_GEMINI_API_KEY_HERE/${{ secrets.GEMINI_API_KEY }}/g" index.html
```

**Corrected Command:**

```bash
sed -i "s/YOUR_GEMINI_API_KEY_HERE/${{ secrets.GEMINI_API_KEY }}/g" infog.html
```

### Final Conclusion

By systematically debugging both the front-end code and the backend deployment pipeline, the project was successfully fixed. The working solution demonstrates the importance of consistency in code variables and the need for meticulous configuration in automated workflows, where even a small typo can lead to a complete failure.
