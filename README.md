
# @precooked/react-interpolated-content-cell

![Precooked Logo](https://precookedcode.com/assets/logos/logo-horizontal-dark.svg)

`@precooked/react-interpolated-content-cell` is a React component designed to display interpolated content based on dynamic data. It supports rendering both HTML templates and JSON structures, making it a versatile choice for dynamic UI generation.

## Installation

To install the package, use the following command:

```bash
npm install @precooked/react-interpolated-content-cell
```

## Usage

Here's an example of how to use the `InterpolatedContentCell` component:

```tsx
import React from "react";
import InterpolatedContentCell from "@precooked/react-interpolated-content-cell";

const App = () => {
  const extraData = {
    name: "John Doe",
    age: 30,
    city: "New York",
  };

  const htmlContent = "<p>Hello, {{ name }}! Welcome to {{ city }}.</p>";

  const jsonStructure = [
    {
      type: "tag",
      tagName: "Div",
      attributes: { style: { color: "blue" } },
      children: [
        { type: "text", content: "Hello, {{ name }}!" },
        {
          type: "tag",
          tagName: "Span",
          attributes: { style: { fontWeight: "bold" } },
          children: [{ type: "text", content: "Your age: {{ age }}" }],
        },
      ],
    },
  ];

  return (
    <div>
      <InterpolatedContentCell
        extraData={extraData}
        htmlContent={htmlContent}
      />
      <InterpolatedContentCell
        extraData={extraData}
        jsonStructure={jsonStructure}
      />
    </div>
  );
};

export default App;
```

## Props

| Prop Name       | Type                        | Description                                                       |
|-----------------|-----------------------------|-------------------------------------------------------------------|
| `extraData`     | `{ [key: string]: any }`    | The dynamic data used for interpolation.                         |
| `htmlContent`   | `string` \| `undefined`    | The HTML template containing placeholders for dynamic data.      |
| `jsonStructure` | `any[]` \| `undefined`     | A JSON structure for dynamically rendering UI components.        |

## Features

- **Dynamic Interpolation**: Replaces placeholders in HTML or JSON with values from `extraData`.
- **Conditional Rendering**: Supports `showIf` expressions in JSON structures for conditional rendering.
- **HTML and JSON Support**: Allows flexible content rendering using either HTML strings or JSON configurations.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

---

For more components and documentation, visit [PrecookedCode](https://precookedcode.com).
