---
source_path: "/en/copilot/tutorials/copilot-cookbook/debug-errors/debug-invalid-json"
title: "Debugging invalid JSON"
intro: "Copilot Chat can identify and resolve syntax errors or structural issues in JSON data."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "Tutorials"
    href: "/en/copilot/tutorials"
  - title: "GitHub Copilot Cookbook"
    href: "/en/copilot/tutorials/copilot-cookbook"
  - title: "Debug errors"
    href: "/en/copilot/tutorials/copilot-cookbook/debug-errors"
  - title: "Debug invalid JSON"
    href: "/en/copilot/tutorials/copilot-cookbook/debug-errors/debug-invalid-json"
---

# Debugging invalid JSON

Copilot Chat can identify and resolve syntax errors or structural issues in JSON data.

When working with JSON data, you may encounter issues such as trailing commas, mismatched braces, or incorrect data types that make the JSON invalid. GitHub Copilot Chat can help you debug and fix these errors by suggesting corrections to fix invalid JSON.

## Example scenario

Consider a scenario where an application consumes JSON data from an API, but the response fails to parse due to invalid formatting. You receive the error message:

```bash
Error: Parse error
----------------------^
Expecting 'STRING', 'NUMBER', 'NULL', 'TRUE', 'FALSE', '{', '[', got 'undefined'
```

Below is the JSON data that caused the error:

```json id=json-error
{
  "location": "San Francisco",
  "current_weather": {
    "temperature": 18,
    "unit": "Celsius",
    "conditions": "Cloudy
  },
  "forecast": {
    "day": "Monday",
    "high": 22,
    "low": 15,
    "precipitation": 10
  }
}
```

## Example prompt

```copilot copy prompt ref=json-error
Why is my JSON object invalid and how can I fix it?
```

## Example response

> \[!NOTE] The following response is an example. Copilot Chat responses are non-deterministic, so you may get a different response from the one shown here.

Copilot might suggest that your JSON is invalid because it's missing a closing quote for the `conditions` value. Here is the corrected JSON:

```json
{
  "location": "San Francisco",
  "current_weather": {
    "temperature": 18,
    "unit": "Celsius",
    "conditions": "Cloudy"
  },
  "forecast": {
    "day": "Monday",
    "high": 22,
    "low": 15,
    "precipitation": 10
  }
}
```

In this example response, Copilot's suggestions include fixing the closing quote for the `conditions` value, which resolves the JSON parsing error.

## Further reading

* [Prompt engineering for GitHub Copilot Chat](/en/copilot/concepts/prompting/prompt-engineering)
* [Best practices for using GitHub Copilot](/en/copilot/get-started/best-practices)
