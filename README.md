
# Select Component Ng

## Description

The `Select` component is a customizable, highly flexible select dropdown built using Vue 3 and TypeScript. It includes support for themes, multiple sizes, input validation, server-side filtering, and more. The component is designed to be reusable and extendable for any project that requires a feature-rich select element.

### Features:
- **Themes**: Light, Dark, and Custom themes with full color palette control.
- **Sizes**: Supports small, medium, and large sizes.
- **Server-side data support**: Easily integrate with API calls to load options dynamically.
- **Filtering**: Filters options based on user input in real-time.
- **Input Validation**: Customizable validation messages.
- **Fully responsive**: Works on all device sizes, including mobile.

## Installation

To install the component in your project:

### Clone the repository:

```bash
git clone https://github.com/your-repo/select-component.git
cd select-component
```

### Install the required dependencies:

```bash
npm install
```

### Run tests to ensure everything is functioning correctly:

```bash
npm run test
```

## Usage

### Basic Usage

To integrate the `Select` component into your Vue project:

```vue
<template>
  <Select :options="options" theme="minimal" size="medium" />
</template>

<script setup>
import Select from './components/Select.vue';

const options = [
  { id: 1, name: 'Option 1' },
  { id: 2, name: 'Option 2' }
];
</script>
```

## Props

- `options`: An array of option objects, each containing `id` and `name` properties.
- `theme`: Defines the theme for the select box. Available values: `'minimal'`, `'full'`, `'custom'`.
- `size`: Specifies the size of the select box. Available values: `'small'`, `'medium'`, `'large'`.
- `error`: A boolean indicating if there is an input validation error.
- `inputStyle`: Custom styles applied to the input box.

## Theme Customization

The `Select` component supports multiple themes that can be extended or customized. The three provided themes (`minimal`, `full`, and `custom`) are defined using SCSS and CSS variables.

### Example with Custom Theme

You can easily create your own theme by passing in custom styles or modifying the default themes:

```vue
<template>
  <Select :options="options" theme="custom" size="large" />
</template>

<script setup>
import Select from './components/Select.vue';

const options = [
  { id: 1, name: 'Custom Option 1' },
  { id: 2, name: 'Custom Option 2' }
];
</script>

<style scoped>
.custom-select {
  --background-color: #f0e6f6;
  --text-color: #562c6d;
  --border-color: #bb86fc;
  --hover-background-color: #d7c3ed;
}
</style>
```

## Color Palette

Here is the full color palette used by the component. Each theme is defined with its own palette, and the colors can be customized using CSS variables.

### Default Themes

#### Minimal Theme (Light Theme)

| Element                | Color Hex   |
|------------------------|-------------|
| Background Color        | `#ffffff`   |
| Text Color              | `#333333`   |
| Border Color            | `#cccccc`   |
| Hover Background Color  | `#f0f0f0`   |
| Hover Text Color        | `#000000`   |

#### Full Theme (Dark Theme)

| Element                | Color Hex   |
|------------------------|-------------|
| Background Color        | `#333333`   |
| Text Color              | `#ffffff`   |
| Border Color            | `#444444`   |
| Hover Background Color  | `#444444`   |
| Hover Text Color        | `#ffffff`   |

#### Custom Theme (Example)

| Element                | Color Hex   |
|------------------------|-------------|
| Background Color        | `#f7e8e8`   |
| Text Color              | `#c70039`   |
| Border Color            | `#900c3f`   |
| Hover Background Color  | `#ff5733`   |
| Hover Text Color        | `#ffffff`   |

### Custom Theme Variables

Each theme is defined using the following CSS variables that can be easily modified:

```css
--background-color: #f7e8e8;
--text-color: #c70039;
--border-color: #900c3f;
--hover-background-color: #ff5733;
--hover-text-color: #ffffff;
```

### Adding New Themes

To add a new theme, simply extend the SCSS map or create your custom styles using the variables provided. You can override the variables at the component or global level.

## Size Customization

The `Select` component supports three predefined sizes: `small`, `medium`, and `large`.

### Size Definitions

#### Small

| Property      | Value  |
|---------------|--------|
| Height        | `24px` |
| Font Size     | `14px` |
| Line Height   | `24px` |

#### Medium (Default)

| Property      | Value  |
|---------------|--------|
| Height        | `32px` |
| Font Size     | `16px` |
| Line Height   | `32px` |

#### Large

| Property      | Value  |
|---------------|--------|
| Height        | `40px` |
| Font Size     | `18px` |
| Line Height   | `40px` |

## Validation

The component provides simple input validation. If no value is selected or an invalid value is entered, an error message will appear. You can customize the validation message.

```vue
<template>
  <Select :options="options" theme="minimal" size="medium" error />
</template>

<script setup>
import Select from './components/Select.vue';

const options = [
  { id: 1, name: 'Option 1' },
  { id: 2, name: 'Option 2' }
];
</script>
```

## Testing

The project includes comprehensive tests covering:

- **Business Logic**: Tests for filtering, option selection, and validation.
- **UI Tests**: Ensures correct rendering, theming, and interactivity.

### Running Tests

To run all tests:

```bash
npm run test
```

### Test Coverage

- **useSelect.ts**: Tests filtering logic, option selection, and state management.
- **Select.vue**: Tests input rendering, options list, and interaction logic.
