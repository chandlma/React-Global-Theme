# react-global-theme

> A React library for creating a global theme

[![NPM](https://img.shields.io/npm/v/react-global-theme.svg)](https://www.npmjs.com/package/react-global-theme) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

## Install

#### Yarn
```bash
yarn add react-global-theme
```

#### npm
```bash
npm install --save react-global-theme
```

## Usage

```jsx
import React from 'react'

import { createTheme, ThemeProvider, useTheme } from 'react-global-theme'

const globalTheme = createTheme({
  // Override the default theme with custom values
  palette: {
    primary: {
      main: '#738',
    }
  },

  // Add additional custom data
  customPadding: {
    small: 10,
    large: 20,
  }
})

const App = () => {
  return (
    <ThemeProvider theme={globalTheme}>
      <ThemedComponent />
    </ThemeProvider>
)
}

const ThemedComponent = () => {
  // Use hook to get theme to any component
  const theme = useTheme();

  // Pass theme to style object for scoped styles
  const styles = useStyles(theme);

  return (
    <div style={styles.example}>
      Example Themed Component
    </div>
  )
}

const useStyles = theme => ({
  example: {
    // -------- Access global theme ------------
    backgroundColor: theme.palette.primary.main,
    color: theme.palette.common.white,
    padding: theme.customPadding.large,
    // -----------------------------------------

    margin: '20%',
    borderRadius: 100,
    textAlign: 'center',
  }
})

export default App

```

## License

MIT © [CTOverton](https://github.com/CTOverton)
