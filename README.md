# ☁️ react-weather-widget ☁️


☁️ A nice weather widget for react based on openweather - [Demo](https://eggtronic.github.io/react-weather-widget/)


<span>![](https://img.shields.io/npm/dt/@eggtronic/react-weather-widget.svg)</span> <span class="badge-npmversion"><img src="https://badgen.net/badge/license/MIT/blue" alt="NPM version" /></span> <span>![](https://img.shields.io/badge/0-dependency-blue.svg)</span> <span>![](https://img.shields.io/badge/3-peerDependency-blue.svg)</span>

---

<img src="./doc/img/defaultTheme.png" width="250" style="display: inline-block;"><img src="./doc/img/darkTheme.png" width="250" style="display: inline-block;">


---
### Install
[![NPM](https://nodei.co/npm/@eggtronic/react-weather-widget.png)](https://npmjs.org/package/@eggtronic/react-weather-widget)
 

---
### ✨ Feature
- Light Weight - the only peer dependency is styled-components
- Typescript Support
- Customizable Theme
- Geo Detection - detect you geo location by default

### 🖥 Peer Dependency
- react: "^16.8.0"
- react-dom: "^16.8.0"
- styled-components: "^4.0.0"

### 🌈 Usage
- Basic 
  ```JSX
  import React from 'react';
  import WeatherWidget from '@eggtronic/react-weather-widget';

  function Basic() {
    const key = 'xxx'; // your openweathermap api key

    return (
      <WeatherWidget apiKey={key} />
    );
  }
  ```
- Theme
  ```JSX
  import React from 'react';
  import WeatherWidget, {
    darkTheme,
    lightTheme,
    defaultTheme
  } from '@eggtronic/react-weather-widget';
  function Theme() {
    const key = 'xxx'; // your openweathermap api key

    return (
      <WeatherWidget 
        apiKey={key} 
        theme={darkTheme}
      />
    );
  }
  ```

- Customize Theme
  ```JSX
  import React from 'react';
  import WeatherWidget from '@eggtronic/react-weather-widget';
  function CustomTheme() {
    const key = 'xxx'; // your openweathermap api key
    const theme = {
      color: ['#b92b27', '#1565C0'], // graient color of background
      width: '500px', // widget width
      height: '650px', // widget height
      mainFontSize: '24px', // main text size
      subFontSize: '14px', // sub text size
      mainFontColor: '#fff', // main text color
      subFontColor: '#fff', // sub text color
      hrColor: '#fff', // hr line color

      // line chart styles
      lineChartPadding: [45, 30],
      lineChartLabelPadding: [-10, -10],
      lineChartColor: '#fff',
      lineChartLabelColor: '#fff',
      lineChartLabelSize: 1,
      lineChartHeight: '120px'
    }

    return (
      <WeatherWidget 
        apiKey={key} 
        theme={theme}
      />
    );
  }
  ```
- Others
  ```JSX
  import {
    WeatherHeader, 
    WeatherHourly, 
    WeatherDaily,
    LineChart
  } from '@eggtronic/react-weather-widget';

  // you can use those child components independently
  ```
---
### 📝 Props
| Name         | Type    | Default | Description |
| ------------ | ------- | ------- | ----------- |
| className | string |  | Additional CSS class for the root DOM node |
| apiKey | string | | Your api key from [OpenWeatherMap](https://openweathermap.org/) |
| geo | `{lat: string, lon: string}` or `undefined` | undefined | Widget detects your geo by default, you can also specify your own geo location |
| theme | [WeatherWidgetTheme](./src/types/weatherWidget.ts)| [defaultTheme](./src/theme.ts) | Customize theme |
| exclude | [OpenWeatherMapExclude](./src/types/weatherWidget.ts) | undefined | OpenWeatherMap api config, exclude daily/hourly/current wealther data|
| dayRange | [number, number] | [1, 6] | Specify how many days' weather to display (start from next day)|
| hourRange | [number, number] | [1, 6] | Specify how many hours' weather to display (start from next hour)|
| children | ReactElement[] | undefined | React children|

---

#### 🔨 Development
```
npm run install
npm run storybook
```

#### 🧪 Test
`npm run test`

#### 🔧 Build
`npm run build`



### License

MIT © [EggTronic](https://github.com/eggtronic)
