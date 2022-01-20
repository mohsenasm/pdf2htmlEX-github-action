# GitHub Action to convert PDF to HTML with pdf2htmlEX tool

This GitHub action will convert your PDF file to an HTML file.
You should only specify the `filepath`. Then, the output will be an HTML file with the same name.

You can also specify a `zoom` parameter (e.g. `zoom=1.3`).

## Usage Example

Create this `.github/workflows/main.yml` file in your github repo:

```yml
on: [push]

jobs:
  pdf_to_html:
    runs-on: ubuntu-latest
    name: A job to convert PDF to HTML
    steps:
      - name: Checkout repo content
        uses: actions/checkout@v2
      - name: Convert PDF to HTML
        uses: mohsenasm/pdf2htmlEX-github-action@v1
        with:
          zoom: '1.3'
          filepath: 'resume.pdf'
```

The `v1` in the above command is a tag in this repo.

Afterward, you can use other actions to work with the newly created HTML file. Like [action-gh-release](https://github.com/softprops/action-gh-release) or [github-action-push-to-another-repository](https://github.com/cpina/github-action-push-to-another-repository).
