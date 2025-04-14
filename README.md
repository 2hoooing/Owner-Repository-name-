name: Slack Webhook Test

on:
  workflow_dispatch:

jobs:
  send-message:
    runs-on: ubuntu-latest
    steps:
      - name: Send test message to Slack
        uses: slackapi/slack-github-action@v1.24.0
        with:
          payload: |
            {
              "text": "✅ 슬랙 Webhook 테스트 성공! 메시지가 잘 도착했어요 :)"
            }
        env:
          SLACK_WEBHOOK_URL: ${{ secrets.DISCORD_WEBHOOK }}
