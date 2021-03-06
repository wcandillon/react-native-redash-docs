# Redash

The React Native Reanimated and Gesture Handler Toolbelt. As seen on the [“Can it be done in React Native?”](http://youtube.com/user/wcandill) YouTube series.

## Installation

```bash
yarn add react-native-redash
```

## ⚠️ v1 Users ⚠️

v1 documentation: [https://wcandillon.github.io/react-native-redash-v1-docs/](https://wcandillon.github.io/react-native-redash-v1-docs/)

To access functions that work with Reanimated v1 nodes, use the following import:

```typescript
import {usePanGestureHandler} from  "react-native-redash/lib/module/v1";
```

To add TypeScript support for the v1 functions, add the following type to your `tsconfig`:

```javascript
  "include": ["node_modules/react-native-redash/lib/typescript/v1/index.d.ts"]
```

