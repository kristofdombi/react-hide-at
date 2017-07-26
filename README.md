# react-hide-at

Build leaner webpages with `react-hide-at` like Airbnb. 👌

## Install

NPM:
`npm install react-hide-at`

## How to use

Here is a basic example, how `HideAt` can be used:

```js
import React from 'react';
import ReactDOM from 'react-dom';

import HideAt from 'react-hide-at';

ReactDOM.render(
  // "Hello world!" will be hidden on medium screen width and below
  <HideAt breakpoint="mediumAndBelow">
    <p>Hello world!</p>
  </HideAt>,
  document.getElementById('app')
);

```

### Props
List of props

`breakpoint`: This is where you can specify on which screen sizes should be hidden by giving one of the following values:
- `small`
- `mediumAndBelow`
- `medium`
- `mediumAndAbove`
- `large`

Eg.:

```js
...

ReactDOM.render(
  <HideAt breakpoint="medium" />,
  document.getElementById('app')
);
```

**NOTE:** The value given to `breakpoint` prop must be like the ones above, otherwise the prop validation is going to fail❗️

### Default breakpoint values
These breakpoint values are inherited from [withBreakpoint](https://github.com/kristof0425/react-with-breakpoints).

Breakpoint | Value
--- | ---
small | 744
medium | 1128
large | `Infinity`

### Overwriting the breakpoints

You can overwrite the breakpoints simply by giving a `breakpoints` prop to the instance of `withBreakpoint`.
Example:

```js
import React from 'react';
import ReactDOM from 'react-dom';
import HideAt from 'react-hide-at';

// Declare a constant and assign an object to it,
// with the following properties:
const breakpoints = {
  small: 479,
  medium: 768,
  large: 1440
};

ReactDOM.render(
  // Overwrite breakpoints here, by passing your breakpoints constant
  <HideAt breakpoint="mediumAndBelow" breakpoints={ breakpoints }>
    <p>Hello world!</p>
  </HideAt>,
  document.getElementById('app')
);
```

## Contributions

If you'd like to help, feel free to post an issue and have a discussion about your suggestions!

## Background story

**Skip this section, if you aren't interested.**

As I was reading Adam Neary's article of [Rearchitecting Airbnb’s Frontend](https://medium.com/airbnb-engineering/rearchitecting-airbnbs-frontend-5e213efc24d2), two components caught my attention as a junior frontend developer. These were `HideAt` and `ShowAt`, these components seemed to me easy to 'reverse engineer' 🤓 for a rookie like me, but as it turned I needed to create a HOC as well to be able to share the above two with you, the react community. [Airbnb's website](https://aribnb.com) and the [React dev tool](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi) helped me with inspiration along the way.

## Licence
MIT
