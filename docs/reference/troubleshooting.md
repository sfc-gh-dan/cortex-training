# Troubleshooting

For authentication, URL, and server error messages, see the
[CLI troubleshooting section](cli.md#troubleshooting).

For recipe failures, first capture:

- The recipe command with secrets removed
- Job and sub-job IDs
- The installed client version, from `python -c "import cortex_training; print(cortex_training.__version__)"`
- Model, precision, GPU count, and sequence length
- The Snowflake request ID. The CLI prints it on server errors; in the Python
  SDK, HTTP errors end with `(snowflake request id: <id>)`, and other failed
  operations log a `WARNING` such as
  `poll_request failed (snowflake request id: <id>): ...`
- Downloaded execution logs, from `cortex-training download-log JOB_ID`

Recipe-specific failure modes are documented beside the recipe rather than
accumulated on this page.
