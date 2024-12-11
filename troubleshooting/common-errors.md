---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# ⁉️ Common Errors

A list of common errors and how to fix them.

<details>

<summary><mark style="color:red;"><code>400</code></mark> - No nodes satisfying the requirements specified for automatic deployment could be found</summary>

Check the locations section in [`settings.json`](../reference/settings.json.md): The ID used should be the **location ID, not the node ID.**

</details>

<details>

<summary><mark style="color:red;"><code>503</code></mark> - There was an error while communicating with the machine running this server. This error has been logged, please try again.</summary>

Check the node status and use the vanilla Lapsus theme, not a modification.

</details>
