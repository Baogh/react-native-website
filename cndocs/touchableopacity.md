---
id: touchableopacity
title: TouchableOpacity
---

A wrapper for making views respond properly to touches. On press down, the opacity of the wrapped view is decreased, dimming it.

Opacity is controlled by wrapping the children in an Animated.View, which is added to the view hierarchy. Be aware that this can affect layout.

Example:

```
renderButton: function() {
  return (
    <TouchableOpacity onPress={this._onPressButton}>
      <Image
        style={styles.button}
        source={require('./myButton.png')}
      />
    </TouchableOpacity>
  );
},
```

### Example

```ReactNativeWebPlayer
import React, { Component } from 'react'
import {
  AppRegistry,
  StyleSheet,
  TouchableOpacity,
  Text,
  View,
} from 'react-native'

class App extends Component {
  constructor(props) {
    super(props)
    this.state = { count: 0 }
  }

  onPress = () => {
    this.setState({
      count: this.state.count+1
    })
  }

 render() {
   return (
     <View style={styles.container}>
       <TouchableOpacity
         style={styles.button}
         onPress={this.onPress}
       >
         <Text> Touch Here </Text>
       </TouchableOpacity>
       <View style={[styles.countContainer]}>
         <Text style={[styles.countText]}>
            { this.state.count !== 0 ? this.state.count: null}
          </Text>
        </View>
      </View>
    )
  }
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    paddingHorizontal: 10
  },
  button: {
    alignItems: 'center',
    backgroundColor: '#DDDDDD',
    padding: 10
  },
  countContainer: {
    alignItems: 'center',
    padding: 10
  },
  countText: {
    color: '#FF00FF'
  }
})

AppRegistry.registerComponent('App', () => App)
```

### Props

* [TouchableWithoutFeedback props...](touchablewithoutfeedback.md#props)

- [`activeOpacity`](touchableopacity.md#activeopacity)
- [`tvParallaxProperties`](touchableopacity.md#tvparallaxproperties)
- [`hasTVPreferredFocus`](touchableopacity.md#hastvpreferredfocus)

### Methods

* [`setOpacityTo`](touchableopacity.md#setopacityto)

---

# 文档

## Props

### `activeOpacity`

Determines what the opacity of the wrapped view should be when touch is active. Defaults to 0.2.

| 类型   | 必填 |
| ------ | -------- |
| number | 否       |

---

### `tvParallaxProperties`

Apple TV parallax effects

| 类型   | 必填 |
| ------ | -------- |
| object | 否       |

---

### `hasTVPreferredFocus`

_(Apple TV only)_ TV preferred focus (see documentation for the View component).

| 类型 | 必填 | 平台 |
| ---- | -------- | -------- |
| bool | 否       | iOS      |

## Methods

### `setOpacityTo()`

```javascript
setOpacityTo((value: number), (duration: number));
```

Animate the touchable to a new opacity.