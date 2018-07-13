
<p align="center"><a href="https://giojs.org" target="_blank"><img width="100" src="https://raw.githack.com/syt123450/giojs/master/assets/readme/logo.png" alt="Gio logo"></a></p>

<h1 align="center">React-Giojs</h1>

<p align="center">
  <a href="https://www.npmjs.com/package/giojs"><img src="https://img.shields.io/npm/v/giojs.svg" alt="npm version" height="18"></a>
  <a href="https://github.com/syt123450/Gio.js/blob/master/LICENSE"><img src="https://img.shields.io/badge/license-Apache--2.0-green.svg" alt="license badge"></a>
  <a href="https://github.com/mrdoob/three.js/"><img src="https://img.shields.io/badge/dependencies-Three.js-brightgreen.svg" alt="dependencies badge"></a>
  <a href="https://travis-ci.org/syt123450/Gio.js"><img src="https://travis-ci.org/syt123450/Gio.js.svg" alt="build"></a>
  <a href="https://coveralls.io/github/syt123450/Gio.js?branch=master"><img src="https://coveralls.io/repos/github/syt123450/Gio.js/badge.svg" alt="coverage"></a>
</p>

**React-Giojs** is the react version of the open source library **Gio.js**. **Gio.js** is an open source library for web 3D globe data visualization built with Three.js. What makes Gio.js different is that it is **simple** to use Gio.js to **customize** a 3D data visualization model in a declarative way, add your own data, and integrate it into your own **modern** web application.

<!-- [START screenshot] -->
<p align="center">
  <a href=""><img src="https://raw.githack.com/syt123450/giojs/master/assets/readme/Gio.gif"/></a>
</p>
<!-- [END screenshot] -->

## Table of Content

- [Getting Started](#getting-started)
- [Try it online](#try-it-online)
- [Configuration](#configuration)
- [Documentation](#documentation)
- [WIP](#wip)
- [License](#license)

<!-- [START getstarted] -->
## Getting Started

### Installation

- Option 1: npm
```bash
npm install react-giojs --save
```
- Option 2: yarn
```bash
yarn add react-giojs
```
### Usage

After install react-giojs, create a `Gio` tag to render the 3D Gio globe:

```html
import React, {Component} from 'react';
import axios from 'axios';

// import gio component from "react-giojs"

import Gio from 'react-giojs';

class App extends Component {

    constructor() {
        super();

        this.state = {
            data: null
        };
    }

    componentDidMount() {
        axios.get(`../data/sampleData.json`)
            .then(response => this.setState({data: response.data}))
    }

    render() {

        return (
        
            // add data to "data" attribute, and render <Gio> tag
        
            <Gio data={this.state.data} />
        )
    }
}

export default App;

```

If everything goes well, you should see [this](http://giojs.org/examples/00_hello_world(simplest).html).

## Try it online

* [Gio.js playground](http://giojs.org/html/playground.html)
* [Gio.js codepen online demos](https://codepen.io/collection/DkBobG/)

<!-- [END getstarted] -->

## Configuration

Provide a some prop to the <Gio> component, which will customize Gio globe, the code below introduce all these customizable props.

Know more about what these API means, check out [Gio.js document](http://giojs.org/html/docs/index.html)

```

    <Gio

        // width of the Gio container
        width: 400,

        // height of the Gio container
        height: 500,

        // data of the Gio controller, in Json format
        data: data,

        // API to switch to a specific country without click on the globe
        forceSwitchCountry: "US",

        // user can set these configs to define how the Gio look like, this is the same as the parameter of Gio.js's configure() API
        configs: {

            control: {

                // whether show stats (boolean)
                stats: false,

                // whether let unmentioned country unclickable (boolean)
                disableUnmentioned: false,

                // whether let the country mentioned in dataset lighter (boolean)
                lightenMentioned: false,

                // only show in line for selected country (boolean)
                inOnly: true,

                // only show out line for selected country (boolean)
                outOnly: false,

                // set the initial selected country (ISO3166, String, eg. "CN")
                initCountry: "CN",

                // whether show halo (boolean)
                halo: true

            },

            // set elements' color, parameter can be: string (eg. "#ffffff") or hex number (eg. 0xffffff)
            color: {

                // surface color
                surface: 0x48C12,

                // color of selected country
                selected: 0xF17F49,

                // color of in line of selected country
                in: 0x0091FF,

                // color of out line of selected country
                out: 0xFF8000,

                // halo color
                halo: 0X2C4247,

                // background color, area behind the globe
                background: 0x1A2029

            },

            // set the brightness of elements, parameter range can be [0, 1]
            brightness: {

                // brightness of ocean on the earth's surface
                ocean: 0.5,

                // brightness of country mentioned in the data set
                mentioned: 1,

                // country related to the selected country (in or out)
                related: 0.1

            }

        }

    />

```

<!-- [START documentation] -->
## Documentation

These documentations are about Gio.js, which introduce what Gio.js is, how to use Gio.js, how to contributor to Gio.js, and so on. We are trying our best to write more documentation about react-giojs.

- For quick start, see [Getting Started](https://github.com/syt123450/Gio.js/blob/master/docs/Getting%20Started.md)
- To learn more about the [Basic Elements](https://github.com/syt123450/Gio.js/blob/master/docs/Basic%20Elements.md)
- To contribute to Gio.js's code base, read [Developer Guide](https://github.com/syt123450/Gio.js/blob/master/docs/Developer%20Guide.md)
- See Gio's offical website [giojs.org](http://giojs.org) for everything above and plus lots of live examples

<!-- [END documentation] -->

## WIP

* More documentation for React-giojs
* Official website for React-giojs
* Online demos for React-giojs
* Follow Gio.js 2.0

## License

[Apache-2.0](https://github.com/syt123450/react-giojs/blob/master/LICENSE)


[screenshot-url]: http://via.placeholder.com/400x300
[npm-badge]: https://img.shields.io/badge/npm-v0.0.5-orange.svg
[npm-badge-url]: https://www.npmjs.com/package/giojs
[license-badge]: https://img.shields.io/badge/license-MIT-brightgreen.svg
[license-badge-url]: https://github.com/syt123450/Gio.js/blob/master/LICENSE
[dependencies-badge]: https://img.shields.io/badge/dependencies-Three.js-brightgreen.svg
[dependencies-badge-url]: https://github.com/mrdoob/three.js/
