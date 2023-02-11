---
title = "React Testing Recipes"
author = ["Suraj Yadav"]
date = 2023-02-11
tags = ["recipe"]
draft = false
---

## You want to setup jest
### A minimal config

*jest.config.js*
```javascript
module.exports = {
 transform: {
   "^.+\\.jsx?$": `<rootDir>/jest-preprocess.js`,
 },
 moduleNameMapper: {
   '^.+\\.(css|style|less|sass|scss)$': 'identity-obj-proxy',
 },
 transformIgnorePatterns: [ '!node_modules/',],
 testEnvironmentOptions: {
   url: `http://localhost`,
 },
}
```
#### Further Reading
- Jest configuration docs
  - https://jestjs.io/docs/configuration
- `identity-obj-proxy` docs
  - https://github.com/keyz/identity-obj-proxy


*jest.preprocess.js*
```javascript
const babelOptions = {
  // your babel config goes here
};

module.exports = require('babel-jest').default.createTransformer(babelOptions);
```
#### Further Reading
- Babel docs
  - https://babeljs.io/docs/en/presets/
  - https://babeljs.io/docs/en/plugins
