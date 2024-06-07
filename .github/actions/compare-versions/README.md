# 🚀 Compare Semantic Versions Action

[![Test Compare Versions](https://github.com/BrainXio/actions/actions/workflows/test-compare-versions.yml/badge.svg)](https://github.com/BrainXio/actions/actions/workflows/test-compare-versions.yml)

<div style="display: flex; align-items: center;">
    <div style="flex-shrink: 0; margin-right: 20px; text-align: justify;">
        <img src="https://avatars.githubusercontent.com/u/168876326?s=200&v=4" alt="description of image" width="75" height="75">
    </div>
    <div>
        "Effortlessly compare the current tag of a repository with a specified tag using this swift and efficient GitHub Action!"
    </div>
</div>

## ✨ Features

- **Simple Comparison**: Just provide the current tag and the tag to compare against, and you're good to go!
- 🛠️ **Composite Execution**: Executes commands directly, ensuring streamlined performance without additional dependencies.
- 🎉 **Boolean Output**: Receive a boolean indicating whether the current tag and the specified tag are equal.

## 🛠️ Usage

Configure this action effortlessly in your workflow file:

```yaml
name: 'Compare Semantic Versions'

on: [push]

jobs:
  compare-versions:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2

    - name: Compare Semantic Versions
      id: compare-versions
      uses: brainxio/actions/compare-semantic-versions@v1
      with:
        compare-to-tag: '<TAG_TO_COMPARE>'

    - name: Print Comparison Result
      run: echo "Are tags equal? ${{ env.TAGS_ARE_EQUAL }}"
```

> Ensure to specify the tag to compare against in the `compare-to-tag` input.

### Inputs

- `compare-to-tag` (required): The tag to compare against the current tag of the repository.

### Outputs

- `tags-are-equal`: Boolean indicating if the current tag and the specified tag are equal.

## 🌟 Example

Comparing the current tag with the specified tag is as simple as:

```yaml
- name: Compare Semantic Versions
  id: compare-versions
  uses: brainxio/actions/compare-semantic-versions@main
  with:
    compare-to-tag: '<TAG_TO_COMPARE>'
```

## 📝 License

This action is licensed under the [The Unlicense](LICENSE). Feel free to use, modify, and distribute it according to your needs. Contributions are welcome!
