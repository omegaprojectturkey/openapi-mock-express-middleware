<div align="center">
  <a href="https://swagger.io/docs/specification/about/">
    <img src="https://raw.githubusercontent.com/aleksandryackovlev/openapi-mock-express-middleware/master/assets/openapi-logo.png" alt="Open API logo" width="200" height="200">
  </a>
  <a href="https://github.com/expressjs/express">
    <img src="https://raw.githubusercontent.com/aleksandryackovlev/openapi-mock-express-middleware/master/assets/express-logo.png" alt="Express logo" width="465" height="141">
  </a>
</div>

[![npm][npm]][npm-url]
[![deps][deps]][deps-url]
[![Build Status](https://travis-ci.org/aleksandryackovlev/openapi-mock-express-middleware.svg?branch=master)](https://travis-ci.org/aleksandryackovlev/openapi-mock-express-middleware)
[![codecov](https://codecov.io/gh/aleksandryackovlev/openapi-mock-express-middleware/branch/master/graph/badge.svg)](https://codecov.io/gh/aleksandryackovlev/openapi-mock-express-middleware)
[![size](https://packagephobia.now.sh/badge?p=openapi-mock-express-middleware)](https://packagephobia.now.sh/result?p=openapi-mock-express-middleware)

# openapi-mock-express-middleware

Generates an express mock server from an [Open API 3.0](https://swagger.io/docs/specification/about/) documentation.

## Installation

To begin, you'll need to install `openapi-mock-express-middleware`:

```console
$ npm install openapi-mock-express-middleware --save-dev
```

## Usage
### Simple Config
```javascript
const express = require('express');
const mockServer = require('openapi-mock-express-middleware');

const app = express();
app.use(
  '/api' /* root path for the mock server */,
  mockServer({ file: '/absolute/path/to/your/openapi/spec.yml' })
);
app.listen(80, () => console.log('Server listening on port 80'))''
```

### Advanced Config
The middleware uses [json-schmea-faker](https://github.com/json-schema-faker/json-schema-faker) under the hood. To configure it, you can pass locale and the options object to the factory function. (The full list of available options can be seen [here](https://github.com/json-schema-faker/json-schema-faker/tree/master/docs#available-options))
```javascript
const express = require('express');
const mockServer = require('openapi-mock-express-middleware');

const app = express();
app.use(
  '/api', // root path for the mock server
  mockServer({
    file: '/absolute/path/to/your/openapi/spec.yml'
    locale: 'ru', // json-schema-faker locale, default to 'en'
    {
      alwaysFakeOptionals: true,
      useDefaultValue: true,
      // ...
    }, // json-schema-faker options
  })
);
app.listen(80, () => console.log('Server listening on port 80'))''
```

## Contributing

Please take a moment to read our contributing guidelines if you haven't yet done so.

[CONTRIBUTING](./.github/CONTRIBUTING.md)

## License

[MIT](./LICENSE)


[npm]: https://img.shields.io/npm/v/openapi-mock-express-middleware.svg
[npm-url]: https://npmjs.com/package/openapi-mock-express-middleware
[deps]: https://david-dm.org/aleksandryackovlev/openapi-mock-express-middleware.svg
[deps-url]: https://david-dm.org/aleksandryackovlev/openapi-mock-express-middleware
j
