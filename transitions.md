---
description: Transitions can attach an animation value to a change of React state.
---

# Transitions

| State \(JS Thread\) | Value \(UI Thread\) |  |
| :--- | :---: | ---: |
| Timing | useTimingTransition\(\) | withTimingTransition\(\) |
| Spring | useSpringTransition\(\) | withSpringTransition\(\) |

```typescript
import { useTiming } from "react-native-redash";

const Toggle = () => {
  const [open, setOpen] = useState(false);
  const transition = useTiming(open, { duration: 400 });
}
```

## `useTiming()`

```typescript
const useTiming: (state: number | boolean, config?: Animated.WithTimingConfig) => number;
```

## `useSpring()`

```typescript
const useSpring: (state: number | boolean, config?: Animated.WithSpringConfig) => number;
```

