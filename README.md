# Stored XSS in B‑CRM Document Viewer

## Summary

This repository documents a stored Cross-Site Scripting (XSS) vulnerability found in the B‑CRM web application, where HTML files uploaded via the document form are rendered directly in a built-in viewer without sanitization.

## Description

The application fails to sanitize user-uploaded `.html` files. If such a file contains JavaScript — for example:

```html
<html>
  <body>
    <script>alert('Mega Pwned');</script>
  </body>
</html>
```

<img width="940" height="711" alt="image" src="https://github.com/user-attachments/assets/0e7f7d53-7f44-4354-b660-02fe6267158b" />



File uploaded and using built-in viewer renders the html allowing injection.


<img width="940" height="178" alt="image" src="https://github.com/user-attachments/assets/c4403863-9d8f-427f-9427-ab67103bb2ed" />

<img width="709" height="244" alt="image" src="https://github.com/user-attachments/assets/304f6ecc-b9ab-47ce-b1f0-057facdb0dbe" />

