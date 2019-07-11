# react-cam

HTML5 Web/Mobile camera for ReactJS

# Installation

## NPM

```console
npm install react-cam
```

## Yarn

```console
yarn add react-cam
```

# How to use it?

## props

| Prop name   | Optional | Default   | Description                                                                    |
| ----------- | -------- | --------- | ------------------------------------------------------------------------------ |
| showFocus   | Yes      | false     | show/hide the blue focus box, basically useless...                             |
| front       | Yes      | false     | true: front camera, false: rear camera                                         |
| capture     | No       | None      | A function to handle base64 string image                                       |
| width       | No       | 480       | Camera pixel width, percentage or absolute value                               |
| height      | No       | 320       | Camera pixel height, percentage or absolute value                              |
| focusWidth  | Yes      | 80%       | Camera focus box width, percentage or absolute value                           |
| focusHeight | Yes      | 50%       | Camera focus box height, percentage or absolute value                          |
| btnColor    | Yes      | '#2acef5' | Set color of the capture button                                                |
| onError     | No       |           | Handles camera error, the error object will be passed as the function argument |

## example

```javascript
import React, {Component} from 'react';
import { Camera } from 'react-cam';

...

class ContainerComponent extends Component{
  ...

  capture = (imgSrc) => {
    // imgSrc is base64 string
  }

  render(){
    return (
      //Recommended resolution for web cams and phone cameras 1920 x 1440
      <Camera
        showFocus={true} //show/hide focus box, basically useless...
        front={false} // true: front camera, false: rear camera
        capture={this.capture}
        width={1920}
        height={1440}
        focusWidth="200px"
        focusHeight="200px"
        btnColor="#000"
        />
    )
  }
}

```
