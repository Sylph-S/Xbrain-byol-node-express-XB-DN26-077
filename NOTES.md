# NOTES

## Strategy Chosen: Option A — `serverless-http`

## Why this strategy?

- Lowest code-change cost: only 1 new file (`lambda.js`) with 3 lines of code, plus 1 npm dependency.
- Zero changes to `app.js` — the Express app stays framework-pure and Lambda-unaware.
- Well-maintained, widely adopted package.
- Simple mental model: `serverless-http` wraps the Express app and translates API Gateway events into standard HTTP request/response objects.

## What was added

- `lambda.js` — entrypoint that wraps `app.js` with `serverless-http`
- `serverless-http` added to `package.json` dependencies
- `template.yaml` — set `Handler: lambda.handler`

## Cold Start Measured

- **Init Duration: 261.74 ms**

## API Gateway URL

https://inpxk1n1ok.execute-api.us-west-2.amazonaws.com
