# Loosely

**Turn any string into JSON.**

Loosely is a browser-based JSON parser that takes messy, malformed, or loosely formatted text and does its best to turn it into valid JSON.

Paste a JavaScript object, Python-style data, malformed JSON, plain text, or a JSON structure buried inside other text — Loosely attempts to extract, repair, normalize, and display it as usable JSON.

## Features

* **Lenient JSON parsing** — handles input that isn't strict JSON.
* **JavaScript-style objects** — supports unquoted keys, single quotes, and trailing commas.
* **Python-style values** — converts `True`, `False`, and `None`.
* **Malformed JSON repair** — attempts to recover from missing or mismatched brackets and other common paste errors.
* **JSON extraction** — finds JSON objects or arrays embedded inside surrounding text.
* **Plain text support** — text that cannot be interpreted as a structure is converted into a JSON string.
* **Format JSON** — display JSON with two-space indentation.
* **Minify JSON** — convert formatted JSON into a compact representation.
* **Filter** — search and filter JSON by keys or values.
* **Syntax highlighting** — makes keys, strings, numbers, booleans, and punctuation easier to read.
* **Compare input and output** — inspect what changed during conversion with a line-based diff.
* **Copy JSON** — copy the resulting JSON directly to your clipboard.
* **Export JSON** — save the result as a `.json` file.
* **History** — keep up to 30 successful conversions in your browser.
* **Themes** — choose from 12 built-in themes.
* **Fullscreen views** — expand the input or output pane when working with larger data.
* **Responsive interface** — works on desktop and smaller screens.
* **No backend required** — everything runs directly in the browser.

## Privacy

Loosely runs entirely in your browser.

**Nothing you paste is sent to a server.**

Your parsing, formatting, filtering, and conversion happen locally using JavaScript in your browser.

Parse history is stored locally using `localStorage` and is not uploaded anywhere.

## Supported Input

Loosely can handle normal JSON:

```json
{
  "name": "Ada Lovelace",
  "active": true,
  "age": 36
}
```

It can also handle JavaScript-style objects:

```javascript
{
  name: 'Ada Lovelace',
  active: True,
  languages: ['math', 'computing'],
  notes: None,
}
```

It can attempt to recover JSON from surrounding text:

```text
Response received:
{"name": "Ada", "role": "engineer"}
End of response.
```

It also attempts to recover from common formatting and paste errors such as:

* Single-quoted strings
* Unquoted object keys
* Trailing commas
* Missing commas
* Missing or mismatched brackets
* Python-style booleans and null values
* Comments
* Stray quotes inside string values
* JSON structures embedded in other text
* Incomplete or slightly corrupted structures

When no JSON structure can be detected, Loosely falls back to treating the input as plain text and wraps it as a JSON string.

## How It Works

Loosely uses a series of parsing and recovery strategies rather than relying exclusively on `JSON.parse()`.

The parser roughly follows this process:

1. Try standard JSON parsing.
2. Detect and extract JSON structures from surrounding text.
3. Remove surrounding quotes when appropriate.
4. Remove comments and trailing commas.
5. Repair certain malformed quotes.
6. Repair unbalanced or mismatched brackets.
7. Interpret JavaScript/Python-style literals.
8. Handle bare booleans, numbers, and null values.
9. Fall back to a JSON string for plain text.

The parser also includes a tolerant structural parser for recovering objects and arrays from imperfect input.

## Browser Storage

Loosely uses browser `localStorage` for:

* Selected theme
* Parse history

History is limited to the latest **30 successful conversions**.

Clearing browser storage will also remove this locally stored data.

## Technology

Loosely is intentionally simple:

* HTML
* CSS
* Vanilla JavaScript
* Web APIs
* Browser `localStorage`

There is no framework, backend, database, or build system required.

## Running Locally

Because Loosely is a static browser application, you can simply open:

```text
index.html
```

in a modern web browser.

For development, you can also serve the directory using any simple static HTTP server.

## GitHub Pages

Loosely can be hosted as a static website using GitHub Pages.

Once GitHub Pages is enabled for the repository, the application can be accessed directly through its GitHub Pages URL.

## License

This project is **not licensed for reuse**.

All rights reserved.

You may view the source code, but copying, modifying, redistributing, or using the source code in another project is not permitted without permission from the copyright holder.

## Author

**Abhishek Jajoria**

---

> **Loosely** — paste anything, get valid JSON.
