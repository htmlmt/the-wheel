# The Wheel

Welcome! I had lots of fun recreating the main show navigation on pbskids.org with Vue.

The geometry involved in making a wheel like this is incredibly interesting, especially because it requires a bit of "magic" in displaying 34 shows on a pie with only 16 wedges.

I also loved thinking through the ways this kind of layout can be flexible for different kinds of content, given that new shows would be added. The shape-outside CSS property is particularly useful here, as two floated SVGs to the left and right of show titles automatically places text within the half circle.

Additionally, it was helpful to use a screen reader utility class for all shows not currently visible, so that all links are accessible, but focusing them doesn't break the layout.

Note that there are a couple differences from the original wheel: I flipped the arrows on the rotate buttons so that new shows entering the wheel are closest to the button that's hovered. I also added a hover state to the show image to reinforce the interaction.

Given more time, I would add the ability to drag the wheel on touch devices, and on small screens would hope to lay out a simplified, scrollable row using the same markup.

## Project setup

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Lints and fixes files

```
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).
