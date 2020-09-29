# Physics

## `snapPoint()`

```typescript
const snapPoint = (value: number, velocity: number, points: ReadonlyArray<number>): number;
```

Select a point where the animation should snap to given the value of the gesture and it's velocity.


```typescript
withSpring(snapPoint(translationX, velocityX, [0, width])
```
