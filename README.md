# datalogz-custom-tree-select

A fork of [`react-dropdown-tree-select`](https://github.com/dowjones/react-dropdown-tree-select), adapted to work with our the React version and to match Datalogz's product needs.

## Why a fork?

The original package hasn't been actively maintained and doesn't support React 19, which broke when we tried to use it in newer Datalogz apps. Rather than blocking on an upstream fix, we forked it so we could:

1. **Keep it compatible** with our stack — React 19 support, dependency cleanup, and build tooling updates (Tailwind support added, legacy Bootstrap-style classes removed).
2. **Customize it for Datalogz** — brand-aligned styling, tweaked interaction behavior, and support for additional fields/data we need to show in the tree/dropdown that the upstream component didn't expose.

This is not a general-purpose open source replacement — it's tailored to Datalogz's design system and use cases. External contributors should probably use the upstream package instead.

## Installation

```bash
npm install datalogz-custom-tree-select
# or, if not published to npm yet:
npm install github:arif-js/datalogz-custom-tree-select
```

## Usage

```jsx
import DropdownTreeSelect from 'datalogz-custom-tree-select'
import 'datalogz-custom-tree-select/dist/styles.css'

const data = {
  label: 'search me',
  value: 'searchme',
  children: [{ label: 'search me too', value: 'searchmetoo' }],
}

function Example() {
  return <DropdownTreeSelect data={data} onChange={(currentNode, selectedNodes) => console.log(selectedNodes)} />
}
```

## What's different from upstream

- React 19 compatibility (upstream peer deps cap at React 18).
- Tailwind-based styling instead of Bootstrap utility classes.
- Datalogz brand theming (colors, spacing, typography) baked into the default styles.
- [list any new/custom props you've added for extra fields, e.g. `showXField`, `customNodeRenderer`, etc.]
- [note any behavior changes vs. upstream, e.g. default open state, search behavior]

Most props and core behavior are unchanged from upstream — see the [original docs](https://github.com/dowjones/react-dropdown-tree-select) for the full API reference, or `types/react-dropdown-tree-select-wrapper.d.ts` in this repo for the current type definitions.

## Development

```bash
npm install
npm run build       # builds dist/
npm run demo        # local demo playground
npm run test        # runs the test suite
```

## Credits & License

This package is a derivative of [react-dropdown-tree-select](https://github.com/dowjones/react-dropdown-tree-select) by Dow Jones, Inc., MIT licensed. See `LICENSE` for the original copyright notice.
