# Troubleshooting

For authentication, URL, and server error messages, see the
[CLI troubleshooting section](cli.md#troubleshooting).

For recipe failures, first capture:

- The recipe command with secrets removed
- Job and sub-job IDs
- The installed client version, from `python -c "import cortex_training; print(cortex_training.__version__)"`
- Model, precision, GPU count, and sequence length
- The Snowflake request ID. The CLI prints it on server errors. In the Python
  SDK, HTTP errors start with `[snowflake request id: <id>]` when the response
  carried one. Other failed client operations, such as a request that ended
  `failed` while polling, log a `WARNING` such as
  `[last snowflake request id: <id>] poll_request failed: ...`; that is the
  operation's most recent request, which did not necessarily fail. Client-side
  argument errors (`ValueError`, `TypeError`) log nothing.
- Downloaded execution logs, from `cortex-training download-log JOB_ID`

Recipe-specific failure modes are documented beside the recipe rather than
accumulated on this page.
