[![Test](https://github.com/snow-actions/composite-action-template/actions/workflows/test.yml/badge.svg)](https://github.com/snow-actions/composite-action-template/actions/workflows/test.yml)

# Create a Composite Action

Click the `Use this template` to bootstrap the creation of a [composite action](https://docs.github.com/en/actions/creating-actions/creating-a-composite-action).:rocket:

This template includes tests, a validation workflow and versioning guidance.

Learn how to use this template at [Wiki](https://github.com/snow-actions/composite-action-template/wiki).

## Usage

### Basic

```yml
name: GitHub Discussions Notifier

on:
  discussion:
    types: [created]
  discussion_comment:
    types: [created]
    
jobs:
  notify-github-discussions:
    runs-on: ubuntu-latest
    steps:
      - uses: ostk0069/github-discussions-notifier@v0.0.1
        with:
          SLACK_CHANNEL_ID: <your slack channel id>
          SLACK_BOT_TOKEN: <your slack bot token>
```

### Optional

```yml
name: GitHub Discussions Notifier

on:
  discussion:
    types: [created]
  discussion_comment:
    types: [created]
    
jobs:
  notify-github-discussions:
    runs-on: ubuntu-latest
    steps:
      - uses: ostk0069/github-discussions-notifier@v0.0.1
        with:
          SLACK_CHANNEL_ID: <your slack channel id>
          SLACK_BOT_TOKEN: <your slack bot token>
          send-discussion: true
          send-discussion-comment: false
```

## Inputs

See [action.yml](action.yml)

| Name | Description | Default | Required |
| - | - | - | - |
| `SLACK_CHANNEL_ID` | your slack channel id | - | yes |
| `SLACK_BOT_TOKEN` | your slack bot token | - | yes |
| `send-discussion` | send discussion notification? | false | no |
| `send-discussion-comment` | send discussion comment notification? | true | no |


## Supported

### Runners

- `ubuntu-22.04`
- `ubuntu-20.04`
- `ubuntu-18.04`
- `windows-2022`
- `windows-2019`
- `macos-11`
- `macos-10.15`
- `self-hosted`

### Events

- `discussion: types: [created]`
- `discussion_comment: types: [created]`

## Dependencies

- [actions/cache](https://github.com/actions/cache) >= 3.0.0
- [GitHub CLI](https://cli.github.com/) >= 2.6.0

## Contributing

Welcome.
