<!-- BEGIN_ACTION_DOC -->
# R spellcheck action

### Description
Checks for spelling errors in R packages

### Action Type
Composite

### Author
Insights Engineering

### Inputs
* `path`:

  _Description_: Path to package root

  _Required_: `false`

  _Default_: `.`

* `exclude`:

  _Description_: Files or folders to exclude from spellcheck

  _Required_: `false`

  _Default_: `""`

### Outputs
None
<!-- END_ACTION_DOC -->

## Usage

Here's an example workflow demonstrating how this action can be used:

```yml
---
name: Spellcheck

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  check:
    runs-on: ubuntu-latest
    name: Spellcheck
    container:
      image: rocker/tidyverse:4.1.2
    steps:
      - name: Checkout repo
        uses: actions/checkout@v2

      - name: Run Spelling Check test
        uses: insightsengineering/r-spellcheck-action@v2
```
