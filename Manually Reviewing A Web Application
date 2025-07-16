# Essential Notes: Manual Web Application Security Review Using Browser Tools

## 🧠 Core Concepts

- Web apps can hide valuable information in **source code**, **network requests**, and **JavaScript logic**.
- Automated scanners often **miss vulnerabilities** that are obvious when manually analyzing an application.
- Manual testing is **slow but precise**, giving more context and control over findings.

## 🔍 Why Manual Review?

- Tools like Burp Suite or Nikto may **skip over dynamic content** or JS-rendered endpoints.
- You may **miss logic bugs** or configuration flaws if you rely only on automation.
- Developers often leave **debug messages**, **commented-out credentials**, or **unfinished features** in code.

## 🛠️ Browser Dev Tools to Use

- **Elements Tab**: Inspect DOM, detect hidden fields, analyze user input handling.
- **Console Tab**: Interact with the page using JavaScript. Try calling hidden functions.
- **Network Tab**: Analyze API calls, data leaks, cookies, token flows, HTTP status.
- **Application Tab**: Access local storage, session storage, and cookies.
- **Sources Tab**: Read loaded JS files; check for obfuscated code or dev artifacts.

## 📌 What to Look For

- Sensitive info in HTML: `<!-- API_KEY: abc123 -->`
- JavaScript exposing internal logic like `isAdmin = true`
- API endpoints that are not visible in the UI but show up in the network tab
- Misconfigured CORS headers, insecure cookie attributes (missing HttpOnly, Secure)
- Hidden GET/POST parameters that trigger admin functionality

## 🧪 Testing Tips

- Change values in hidden inputs and observe server behavior.
- Modify API requests in the **network tab** and resend them with `Fetch/XHR Replay`.
- Look for `robots.txt` and `sitemap.xml` for disallowed or hidden URLs.
- Use console to manipulate DOM and bypass UI restrictions.
- Test for client-side validation bypass (e.g., minimum length checks).

## 📷 Visual References

![Chrome DevTools Overview](https://developer.chrome.com/blog/images/devtools-homepage.png)

![Inspecting Elements in Browser](https://i.imgur.com/2y6kXJu.png)

![Network Panel Showing API Calls](https://i.imgur.com/jJQ5LlT.png)

## ✅ Summary

Manual testing is essential when:

- Exploring **CTFs** or **bug bounty targets**
- Auditing custom apps or obscure frameworks
- Finding issues missed by automated tools

It empowers you to learn **how apps work under the hood**, not just how to break them.

---

**This document is the sole property of AlphaBey, made independently.**
