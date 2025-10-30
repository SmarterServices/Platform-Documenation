# SmarterElements Documentation

This directory contains the public-facing documentation for SmarterElements, automatically generated from element schemas and manually curated guides.

## Documentation Structure

```
smarter-elements/
├── overview.mdx              # Overview of SmarterElements
├── getting-started.mdx       # Integration guide (React & JS)
├── api-reference.mdx         # Complete API documentation
├── examples.mdx              # Practical examples and patterns
├── troubleshooting.mdx       # Common issues and solutions
├── elements.mdx              # Index of all available elements
└── elements/                 # Auto-generated element docs
    └── [element-name].mdx    # Individual element documentation
```

## Auto-Generated Documentation

Element documentation is automatically generated from schema files using:

```bash
npm run docs:elements
```

This script:
1. Scans `apps/ui/src/context/elements/components/` for elements with `schema.ts` files
2. Parses TypeScript interfaces and metadata
3. Generates comprehensive MDX documentation for each element
4. Updates the Mintlify navigation automatically

## Manual Documentation

The following files are manually maintained:
- `overview.mdx` - High-level overview and concepts
- `getting-started.mdx` - Integration guides and quick start
- `api-reference.mdx` - Complete API reference
- `examples.mdx` - Code examples and patterns
- `troubleshooting.mdx` - Common issues and solutions

## Element Schema Requirements

For an element to be included in the documentation, it must have:

1. **Schema file**: `schema.ts` in the element directory
2. **Required exports**:
   ```typescript
   export const ELEMENT_NAME = 'Display Name';
   export const ELEMENT_TYPE = 'category/element-name';
   export const ELEMENT_DESCRIPTION = 'Brief description';
   
   export interface InputSchema {
     // Input parameters
   }
   
   export interface OutputSchema {
     // Output interface (optional)
   }
   
   export interface EventsSchema {
     // Events emitted (optional)
   }
   ```

3. **Component file**: `index.tsx` or `index.jsx` in the same directory

## Adding New Elements

When adding a new element:

1. Create the element directory structure:
   ```
   apps/ui/src/context/elements/components/category/ElementName/
   ├── index.tsx        # React component
   ├── schema.ts        # TypeScript schema
   └── ...              # Other files
   ```

2. Define the schema with proper exports
3. Run the documentation generator:
   ```bash
   npm run docs:elements
   ```

4. The documentation will be automatically generated and added to navigation

## Development Workflow

### Updating Documentation

1. **Auto-generated docs**: Modify the `schema.ts` file and run `npm run docs:elements`
2. **Manual docs**: Edit the `.mdx` files directly
3. **Navigation**: Run `npm run docs:navigation` to update navigation only

### Testing Documentation

```bash
# Start the documentation server
npm run docs:public

# Visit http://localhost:3333 to preview
```

### Publishing Documentation

Documentation is automatically deployed when changes are pushed to the main branch.

## Documentation Standards

### Element Documentation

Each element page includes:
- **Overview** - What the element does
- **Usage** - React and JavaScript examples
- **Configuration** - Input parameters and types
- **Events** - Available events and data
- **Examples** - Common use cases
- **API Reference** - Methods and options

### Code Examples

- Include both React and vanilla JavaScript examples
- Show realistic, working code
- Include error handling
- Demonstrate common patterns

### Writing Style

- **Clear and concise** - Get to the point quickly
- **Practical** - Focus on real-world usage
- **Complete** - Include all necessary imports and setup
- **Accessible** - Use simple language and explain concepts

## Scripts Reference

| Script | Purpose |
|--------|---------|
| `npm run docs:elements` | Generate all element documentation |
| `npm run docs:navigation` | Update navigation with new elements |
| `npm run docs:public` | Start documentation development server |

## File Locations

| Type | Location |
|------|----------|
| Element schemas | `apps/ui/src/context/elements/components/*/schema.ts` |
| Generated docs | `docs/public/smarter-elements/elements/` |
| Manual docs | `docs/public/smarter-elements/*.mdx` |
| Navigation config | `docs/public/docs.json` |
| Generation scripts | `tools/scripts/generate-element-docs.js` |

## Contributing

When contributing to SmarterElements documentation:

1. **Element docs**: Update the schema file and regenerate
2. **Guide docs**: Edit the MDX files directly
3. **Examples**: Add practical, tested code examples
4. **Navigation**: Let the scripts handle navigation updates

For questions or issues with documentation, see the [troubleshooting guide](./troubleshooting.mdx) or contact the development team.
