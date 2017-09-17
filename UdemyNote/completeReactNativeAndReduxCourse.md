# Memo
## section 5 Lecture 19
### just creating a component does not do anything
---
-   react does not automatically wire up components, so just creating a component does not make react to render an instance of the component.
-   you must explicitly tell react to render an instance of the comonent created.
-   to render a component, a **function** returning a component**(not an instance!!)** must be registered

## section 5, Lecture 22
### no round parenthesis for returning single jsx
---
-   when there are multi lines of jsx to return, use round parenthesis
```jsx
const App = () => {
  return (
    <Text>
      <Text>text1</Text>
      <Text>text2</Text>    
      <Text>text3</Text>    
    </Text>
  );
};
```

-   when there is only single line of jsx to return, ommit round parenthesis
```jsx
const App = () => {
  return <Text>some text</Text>
};
```

### no .js extension when importing custom compoment
---
-   if importing from js file, the extension is not necessary
```jsx
import Header from './src/components/header';
```

## section 7 lecture 32
---
### enable hot reload
[Debugging](https://facebook.github.io/react-native/docs/debugging.html)
-   go to Hardware > Shake gesture (ctrl-cmd-z)
-   choose enable hot reaload

---
### enable debug with react-native

[Debugging](https://facebook.github.io/react-native/docs/debugging.html)
-   go to hardware > shake gesture(ctrl-cmd-z)
-   choose enable remote debug

---
### setting break point
-   just add 'debugger' satement
```sh
class AlbumLists extends Component {
  componentWillMount() {
    console.log('component will mount called!!');
    debugger;
  }
  render() {
    return (
      <View>
        <Text>Album Lists </Text>
      </View>
    );
  }
}
```
## section 8 lecture 50
---
### more detail of flexbox layout
[understanding-react-native-flexbox-layout-7a528200afd4](https://medium.com/the-react-native-log/understanding-react-native-flexbox-layout-7a528200afd4)
-   all the react native component is a flex container by default
>First and the main difference I should start with — is that all container elements in React Native are Flex containers by default.

-   in react-native, if a component (by default, _flex container_) is contained inside yet another parent compoent (this is also a flex container), it can accept both 'align-self' property and other properties for a flex container including 'justifyContent'

-   always pay attention to the direction of main-axis, and secondary-axis.
    -   justify-content is with respect to main-axis
    -   align-items is with respect to secondary-axis

| property | what it does | axis
| :------------- | :------------- | :------------- |
| justifyContent | control spacing of the children | main-axis|
| alignItems | control spacing of the children | secondary-axis|
| flex | control the size of the flex container itself with respect to its **parent flex container** if not specified, the width defaults to the width of **its contents**| main-axis<br> **of the parent container**|
| alignSelf | control spacing of the flex container itself with respect to its **parent flex container** alignSelf is used when it is necessary to override the behaviour of a specific content in a parent flex container <br > **e.g.** alignItems of _CardSection_ component is "flex-start", but one of the contents require "center"| secondary-axis **of the parent container**|




# Troubleshooting
### resolve No URL bundeld
---
[github  issue](https://github.com/facebook/react-native/issues/12754)
-   when build under proxy setting, the error occurs
-   to resolve, change the location where proxy is not used
-   or, configure to bypass the proxy for localhost and 127.0.0.1
[How to configure your firewall, proxy,](https://support.1password.com/firewall-proxy/)
-   om2pkral comment on Mar16
>For Debug configuration, which is default when new project is generated with react-native init command, build does not generate bundle file but instead uses packager for that. So the issue is related to network settings and is very likely related to proxy settings. If proxy is used, do not forget to set bypass proxy for localhost and 127.0.0.1 addresses.
