I have created a new slash command, `/send-report`, that allows users to send a packet analysis report to a Slack channel of their choice.

Here's a summary of the changes I've made:

*   **Created a new GitHub Actions workflow** (`.github/workflows/send-report.yml`) that triggers on the `/send-report` command in an issue comment.
*   **Modified the existing `packet_copilot.yml` workflow** to be callable by other workflows and to send the generated Markdown report to the specified Slack channel using a dummy secret.
*   **Updated the `gemini-cli.yml` workflow** to ignore the new `/send-report` command.

To use the new command, comment on any issue with `/send-report <your-channel-name>`. The bot will then analyze the `capture.pcap` file and post the report to the specified Slack channel.