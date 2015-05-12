# React Native

---

# One of these things is not like the others

---

### "React Native enables you to build world-class application experiences on native platforms using a consistent developer experience based on JavaScript and React. The focus of React Native is on developer efficiency across all the platforms you care about — learn once, write anywhere. Facebook uses React Native in multiple production apps and will continue investing in React Native."

---

## Getting Started

* brew install nvm
* brew install watchman
* nvm install iojs-v1.6.4 (or whatever is the latest)
* npm install -g react-native-cli
* react-native init AwesomeProject

---

## What does it give you?

1. A new xcode project
1. A working index.ios.js file (that's the react part)

---

## Running the app

* open new_project.xcodeproj
* npm start
* Build and Run within xcode

---

## On the device

*

---

## How is my code run

```objectivec
  jsCodeLocation = [NSURL URLWithString:@"http://localhost:8081/index.ios.bundle"];
```

```objectivec
  RCTRootView *rootView = [[RCTRootView alloc] initWithBundleURL:jsCodeLocation
                                                      moduleName:@"TestProject"
                                                      launchOptions:launchOptions];
```

---

## What does that mean

* You can host your app on a webserver
* When you submit your app, the .bundle has to be part of the app bundle

---

# Some basic parts

---

## ES6

```javascript
class NavButton extends React.Component {
  render() {
    return (
      <TouchableHighlight
        style={styles.button}
        underlayColor="#B5B5B5"
        onPress={this.props.onPress}>
        <Text style={styles.buttonText}>{this.props.text}</Text>
      </TouchableHighlight>
    );
  }
}
```

---

## Navigation

```javascript
render: function() {
  return (
    <NavigatorIOS
      initialRoute={{
        component: MyView,
        title: 'My View Title',
        passProps: { myProp: 'foo' },
      }}
    />
  );
},
```

---

## TableView

```javascript
render: function() {
  return (
    <ListView
      dataSource={this.state.dataSource}
      renderRow={(rowData) => <Text>{rowData}</Text>}
    />
  );
},
```

---

## Text View

```javascript
var WithLabel = React.createClass({
  render: function() {
    return (
      <View style={styles.labelContainer}>
        <View style={styles.label}>
          <Text>{this.props.label}</Text>
        </View>
        {this.props.children}
      </View>
    );
  }
});
```

---

## Touchable Highlight
```javascript
renderButton: function() {
  return (
    <TouchableHighlight onPress={this._onPressButton}>
      <Image
        style={styles.button}
        source={require('image!myButton')}
      />
    </TouchableHighlight>
  );
},
```
---

## Animations

```javascript
var AnimationTest = React.createClass({
  componentDidMount () {
    Animation.startAnimation(this.refs['this'], 400, 0, 'linear', {opacity: 1});
  },

  render () {
    return (
      <View ref='this' style={styles.test}>
        <Text>Just an animation test</Text>
      </View>
    )
  }
});
```
---

## Polyfills

### "So there's this thing on the web we want you to use"

* Flexbox
* Geolocation
* Network
* Timers

---

## Testing (here be dragons)

* Jest (http://facebook.github.io/jest/)
* Integration Tests
* Snapshot Tests

---

## Magic
### The test runner
```objectivec
RCTTestRunner *_runner;
_runner = RCTInitRunnerForApp(@"Examples/UIExplorer/UIExplorerApp");
[_runner runTest:_cmd module:@"NavigatorIOSExample"];
```

---

## Snapshots



---

### Integration Tests

### For when you need JS and Native

* RCTTestRunner (sets up the world)
* RCTTestModule (exported to JS)

Relies on XCTestCase

---

## The Community

* React Rocks (http://react.rocks/)
* ReactNative.com

---

#　終わりだ
