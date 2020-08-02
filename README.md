# Requiring Nunjucks Leaks Memory

~~This repository demonstrates a memory leak when requiring Nunjucks using Jest.~~
**The issue is fixed in [Nunjucks v3.2.1](https://github.com/mozilla/nunjucks/releases/tag/v3.2.1), I assume the old version of `chokidar` was responsible.**

## To Reproduce

- `npm ci`
- `npm run test`

The heap size increases by about 4MB with every test file run (i.e. on every `require("nunjucks");`).

## Expected Result

- Comment out the `require("nunjucks");` line from `setupTests.js`
- `npm run test`

The heap size should remain constant.
