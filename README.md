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
      - uses: ostk0069/github-discussions-notifier@v0.0.2
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
      - uses: ostk0069/github-discussions-notifier@v0.0.2
        with:
          SLACK_CHANNEL_ID: <your slack channel id>
          SLACK_BOT_TOKEN: <your slack bot token>
          send-discussion-create: true
          send-discussion-comment: false
```

## Inputs

See [action.yml](action.yml)

| Name | Description | Default | Required |
| - | - | - | - |
| `SLACK_CHANNEL_ID` | your slack channel id | - | yes |
| `SLACK_BOT_TOKEN` | your slack bot token | - | yes |
| `send-discussion-create` | send discussion notification? | true | no |
| `send-discussion-comment` | send discussion comment notification? | true | no |
| `unfurl-links` | Pass true to enable unfurling of primarily text-based content | false | no |
| `unfurl-media` | Pass false to disable unfurling of media content | false | no |

## Supported

### Events

- `discussion: types: [created]`
- `discussion_comment: types: [created]`

## Dependencies

- [actions/cache](https://github.com/actions/cache) >= 3.0.0
- [GitHub CLI](https://cli.github.com/) >= 2.6.0
