# 🌠 ForceLayout: D3 Force Layouts Made Easy in Nuxt 🌌

**ForceLayout** simplifies the process of creating mesmerizing D3 force layouts with nodes and edges. Perfect for visualizing everything from social networks to complex systems, right in your Nuxt app! 🎉

## 🌈 Features

- 📊 Easy-to-use API for D3 force layouts.
- 🔄 Built-in data importers for Neo4j and Gephi.
- 🎛️ Real-time manipulation of force properties.
- 🎨 SVG and Canvas rendering modes.
- 🔌 Vue-friendly, using a directive-driven approach similar to VUE-USE.

## 📚 Data Importers 🌐

Before diving into your Nuxt app, you may need to prepare your data into node/edge CSVs with our Node.js-based importers.

### 🌳 Neo4j to ForceLayout 🚀

1. **Install the Neo4j Importer Globally**:
    ```bash
    npm install -g @force-layout/neo4j-importer
    ```
2. **Run the Script**:
    ```bash
    force-layout-neo4j-importer --input neo4j_output.json --nodes nodes.csv --edges edges.csv
    ```
3. 🎨 **Import the CSVs**: Your Neo4j data is ready!

### 🌀 Gephi to ForceLayout 🎡

1. **Install the Gephi Importer Globally**:
    ```bash
    npm install -g @force-layout/gephi-importer
    ```
2. **Run the Script**:
    ```bash
    force-layout-gephi-importer --input graph.gexf --nodes nodes.csv --edges edges.csv
    ```
3. 🌌 **You're Set!**: Your Gephi data is ready!

## 🛠️ Installation

Install ForceLayout in your Nuxt project:
```bash
npm install nuxt-force-layout
```

## 🚀 Usage

Add the module to your `nuxt.config.js`:

```javascript
export default {
  modules: [
    'nuxt-force-layout'
  ]
}
```

In your Vue component, use the `v-force-layout` directive and destructure its properties to customize your force layout:

```vue
<template>
  <div ref="forceLayoutCanvas">
    <!-- Your force layout will be rendered here -->
  </div>
</template>

<script>
export default {
  directives: {
    forceLayout: {
      bind(el, binding) {
        const { initForce, updateForce, width, height } = binding.value;
        // Initialize and manipulate your force layout
      }
    }
  }
}
</script>
```

## 🎛️ Real-Time Manipulation

You can easily tweak the force layout's properties such as `forceX`, `forceY`, `collision`, etc., in real-time!

```javascript
updateForce({ forceX: 0.5, forceY: 0.8 });
```

## 🎨 Rendering Modes

ForceLayout supports two modes:

- **SVG Mode**: For high-quality, scalable graphics.
- **Canvas Mode**: For performance optimization.

Switch between them easily:

```javascript
initForce({ mode: 'svg' }); // or 'canvas'
```

## 📚 Starter Scripts for Data Conversion 🔄

If your data is in JSON, XML, SQL, or other formats, check out our conversion scripts to get you started.

## 🤝 Contributing

We welcome contributions! Please check out our [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.


## Quick Setup

1. Add `nuxt-force-layout` dependency to your project

```bash
# Using pnpm
pnpm add -D nuxt-force-layout

# Using yarn
yarn add --dev nuxt-force-layout

# Using npm
npm install --save-dev nuxt-force-layout
```

2. Add `nuxt-force-layout` to the `modules` section of `nuxt.config.ts`

```js
export default defineNuxtConfig({
  modules: [
    'nuxt-force-layout'
  ]
})
```

That's it! You can now use My Module in your Nuxt app ✨

## Development

```bash
# Install dependencies
npm install

# Generate type stubs
npm run dev:prepare

# Develop with the playground
npm run dev

# Build the playground
npm run dev:build

# Run ESLint
npm run lint

# Run Vitest
npm run test
npm run test:watch

# Release new version
npm run release
```

## 🙋‍♀️ Frequently Asked Questions (FAQs) 🤔

### Q: How do I import my custom data formats?
A: Our built-in Node.js importers currently support Neo4j and Gephi. For other data formats, you can use our starter scripts to help you convert them to the required CSV format.

### Q: Can I use ForceLayout on multiple pages or components?
A: Absolutely! You can use the `v-force-layout` directive in as many components or pages as you like. Just make sure to initialize it separately for each instance.

### Q: What about touch events for mobile support?
A: ForceLayout is designed to be responsive and mobile-friendly. It handles touch events just like mouse events out of the box.

### Q: How do I optimize performance for large datasets?
A: Switch to Canvas rendering mode by setting the `mode` to 'canvas' in the `initForce` method. This offers better performance for larger datasets.

### Q: Can I integrate ForceLayout with Vuex?
A: Yes, you can easily dispatch actions or commit mutations from within the directive to store your layout's state in a Vuex store.

### Q: How do I uninstall the module?
A: To uninstall, simply run `npm uninstall @force-layout/nuxt-module` and remove the related code from your `nuxt.config.js`.

### Q: Is ForceLayout compatible with Nuxt 2?
No, it is intended for use with Nuxt 3. 

Certainly! Here are some more FAQs that cover a wider range of topics:

### Q: Can I use ForceLayout with TypeScript?
A: Yes! ForceLayout is TypeScript-friendly. We provide type definitions out of the box to make your development experience smooth.

### Q: Does ForceLayout support 3D layouts?
A: Currently, ForceLayout focuses on 2D force layouts. However, we're intrigued by the idea of 3D and may consider it for future releases.

### Q: Can I change the color theme dynamically?
A: Absolutely! You can update the color properties in real-time just like you would with force properties. 

### Q: How does ForceLayout handle accessibility?
A: Accessibility is important to us. We're working on features like ARIA labels and keyboard navigation for future releases.

### Q: What happens if I have a cyclic graph? Will ForceLayout get stuck in an infinite loop?
A: Don't worry, ForceLayout is designed to handle cyclic graphs gracefully without getting stuck.

### Q: Can I export the layout to different formats like PNG or PDF?
A: While ForceLayout doesn't natively support this feature yet, you can easily implement it using external libraries.

### Q: Is there a way to pause and resume the force simulation?
A: Yes, you can pause and resume the force simulation by using the `pause` and `resume` methods exposed by the directive.

### Q: Do I need D3 installed to use ForceLayout?
A: No, ForceLayout comes with all the necessary D3 components bundled in. You don't need a separate D3 installation.

### Q: My pet parrot loves watching the nodes move. Is that normal?
A: Absolutely! ForceLayout aims to create engaging and aesthetically pleasing visualizations that can captivate audiences of all species! 🦜

### Q: I'm a time traveler from the year 2050. Will this still work?
A: While we can't guarantee compatibility with future versions of technology, we do strive to make ForceLayout as future-proof as possible!

---

Feel free to suggest additional questions or modifications! 📝

<!-- Badges -->
[npm-version-src]: https://img.shields.io/npm/v/nuxt-force-layout/latest.svg?style=flat&colorA=18181B&colorB=28CF8D
[npm-version-href]: https://npmjs.com/package/nuxt-force-layout

[npm-downloads-src]: https://img.shields.io/npm/dm/nuxt-force-layout.svg?style=flat&colorA=18181B&colorB=28CF8D
[npm-downloads-href]: https://npmjs.com/package/nuxt-force-layout

[license-src]: https://img.shields.io/npm/l/nuxt-force-layout.svg?style=flat&colorA=18181B&colorB=28CF8D
[license-href]: https://npmjs.com/package/nuxt-force-layout

[nuxt-src]: https://img.shields.io/badge/Nuxt-18181B?logo=nuxt.js
[nuxt-href]: https://nuxt.com
