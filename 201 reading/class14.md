## Css Transformation and animation

### Transition

- For a transition to take place, an element must have a change in state, and different styles must be identified for each state. The easiest way for determining styles for different states is by using the `:hover`, `:focus`, `:active`, and `:target` which are pseudo-classes.
there are four transition properties `transition-property`, `transition-duration`, `transition-timing-function`, and `transition-delay`. Not all of these are required to build a transition, with the first three are the most popular.

### Animation

- To set multiple points at which an element should undergo a transition, use the `@keyframes` rule. The `@keyframes` rule includes the animation name, any animation breakpoints, and the properties intended to be animated.

```css
@keyframes slide {
  0% {
    left: 0;
    top: 0;
  }
  50% {
    left: 244px;
    top: 100px;
  }
  100% {
    left: 488px;
    top: 0;
  }
}
```

- the `animation-name` property is used with the animation name, identified from the `@keyframes rule`, as the property value. 

```css
.stage:hover .ball {
  animation-name: slide;
}
```

[tables of contents](./README.md)