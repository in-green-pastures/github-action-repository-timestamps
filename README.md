[![Test](https://github.com/tzieleniewski/github-action-repository-dates/actions/workflows/test.yaml/badge.svg)](https://github.com/tzieleniewski/github-action-repository-dates/actions/workflows/test.yaml)
[![GitHub](https://img.shields.io/github/license/in-green-pastures/github-action-repository-timestamps?label=License)](LICENSE)
[![GitHub tag (latest SemVer)](https://img.shields.io/github/v/tag/in-green-pastures/github-action-repository-timestamps?color=green&label=Tag)](https://github.com/tzieleniewski/github-action-repository-dates/releases)

# Repository Timestamps

Action outputs repository timestamps fetched from the repository resource.

## Usage

Exemplary workflow.

```yaml
name: Repository Timestamps example

on: push

jobs:
  repository-timestamps:
    runs-on: ubuntu-latest
    steps:
      - uses: in-green-pastures/github-action-repository-timestamps@latest
        id: timestamps
      - run: |
          echo Created at timestamp ${{ steps.timestamps.outputs.created-at }}
          echo Pushed at timestamp ${{ steps.timestamps.outputs.pushed-at }}
          echo Updated at timestamp ${{ steps.timestamps.outputs.updated-at }}
```

### Inputs

| Name           | Required | Default value       | Description                                            |
|----------------|----------|---------------------|--------------------------------------------------------|
| `github-token` | false    | ${{ github.token }} | A GitHub token used for making requests to GitHub APIs | 

### Outputs

| Name         | Description                                                 |
|--------------|-------------------------------------------------------------|
| `created-at` | The created at timestamp fetched from `created_at` element. | 
| `pushed-at`  | The pushed at timestamp fetched from `pushed_at` element.   | 
| `updated-at` | The updated at timestamp fetched from `updated_at` element. | 

## License

See the [license file](LICENSE). 