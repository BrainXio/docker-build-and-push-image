# 🚀 Fetch Latest GitHub Tag Action

[![Test Fetch Latest Github Tag](https://github.com/BrainXio/actions/actions/workflows/test-fetch-latest-github-tag.yml/badge.svg)](https://github.com/BrainXio/actions/actions/workflows/test-fetch-latest-github-tag.yml)

<div style="display: flex; align-items: center;">
    <div style="flex-shrink: 0; margin-right: 20px; text-align: justify;">
        <img src="https://avatars.githubusercontent.com/u/168876326?s=200&v=4" alt="description of image" width="75" height="75">
    </div>
    <div>
        "Easily retrieve the latest tag from any GitHub repository with this swift and efficient GitHub Action!"
    </div>
</div>

## ✨ Features

- **Simple Setup**: Just specify the repository owner and name, and you're good to go!
- 🛠️ **Composite Execution**: Executes commands directly, ensuring streamlined performance without additional dependencies.
- 🎉 **Output Convenience**: Receive the latest tag name as an output, seamlessly integrating into your workflows.

## 🛠️ Usage

Configure this action effortlessly in your workflow file:

```yaml
name: 'Fetch Latest GitHub Tag'

on: [push]

jobs:
  fetch-latest-tag:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2

    - name: Fetch Latest Tag
      id: fetch-latest-tag
      uses: brainxio/actions/fetch-latest-github-tag@v1
      with:
        owner: '<REPO_OWNER>'
        repo: '<REPO_NAME>'

    - name: Print Latest Tag
        run: echo "Latest Tag ${{ env.GH_BRAINXIO_ACTIONS_LATEST_TAG }}"
```

> Notice the prefix 'GH_' and the '${OWNER_REPO}' in the environment variable, they are mandatory to get actual data out.

### Inputs

- `owner` (required): The owner of the GitHub repository.
- `repo` (required): The name of the GitHub repository.

### Outputs

- `latest-tag`: The latest tag name fetched from the specified repository.

## 🌟 Example

Fetching the latest tag from the repository `brainxio/actions` is as simple as:

```yaml
- name: Fetch Latest Tag
  id: fetch-latest-tag
  uses: brainxio/actions/fetch-latest-github-tag@main
  with:
    owner: 'brainxio'
    repo: 'actions'

- name: Print Latest Tag
    run: echo "Latest Tag ${{ env.GH_BRAINXIO_ACTIONS_LATEST_TAG }}"
```

## 📝 License

This action is licensed under the [The Unlicense](LICENSE). Feel free to use, modify, and distribute it according to your needs. Contributions are welcome!
