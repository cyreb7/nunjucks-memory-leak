# Requiring Nunjucks Leaks Memory

This repository demonstrates a memory leak when requiring Nunjucks using Jest.

## To Reproduce

- `npm install`
- `npm run test`

The heap size increases by about 4MB with every test file run (i.e. on every `require("nunjucks");`).

## Expected Result

- Comment out the `require("nunjucks");` line from `setupTests.js`
- `npm run test`

The heap size should remain constant.
