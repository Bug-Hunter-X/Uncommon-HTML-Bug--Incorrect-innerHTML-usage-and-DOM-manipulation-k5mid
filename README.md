# Uncommon HTML Bug: Incorrect innerHTML usage and DOM manipulation

This repository demonstrates a subtle yet significant bug that can occur in HTML when manipulating the DOM (Document Object Model) and using `innerHTML` improperly.  The bug focuses on two primary aspects:

1. **Direct modification of element content**: While seemingly simple, directly manipulating an element's content (e.g., using `textContent` or `innerHTML`) can lead to unexpected behavior if not handled carefully, especially when combining methods.
2. **XSS vulnerabilities using innerHTML**: Directly assigning user-supplied data to `innerHTML` creates a significant security vulnerability, known as Cross-Site Scripting (XSS).  This allows malicious users to inject harmful scripts into your webpage.

The `bug.html` file showcases the incorrect implementation, while `bugSolution.html` provides the corrected code.

## How to reproduce the bug:

1. Clone this repository.
2. Open `bug.html` in your web browser.
3. Observe the output. Notice how innerHTML is overriding the changes from the textContent. Then note that the XSS vulnerability becomes a problem.

## How to fix the bug:

1. Open `bugSolution.html` in your web browser.
2. Observe the corrected output. The solution uses proper DOM manipulation to update the div's content, and avoid the potential XSS vulnerability.  It leverages `createElement` and `appendChild` for safer content injection.