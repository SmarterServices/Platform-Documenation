# SmarterServices Public Documentation

This directory contains the public-facing documentation for the SmarterServices Platform, built with [Mintlify](https://mintlify.com/).

## Documentation Structure

The documentation is organized as follows:

```
public/
├── mint.json              # Mintlify configuration file
├── introduction.md        # Main landing page
├── quickstart.md          # Getting started guide
├── development.md         # Developer guide
├── api-reference/         # API documentation
│   ├── authentication.md  # API authentication
│   └── ...
├── platform/              # Platform information
│   ├── architecture.md    # Architecture overview
│   └── ...
├── smarter-elements/      # SmarterElements documentation
│   ├── overview.md        # Overview of SmarterElements
│   └── ...
├── guides/                # Integration guides
│   ├── lms-integration.md # LMS integration guide
│   └── ...
└── logo/                  # Logo and branding assets
```

## Working with Mintlify

### Local Development

To preview the documentation locally:

1. Install the Mintlify CLI:

   ```bash
   npm install -g mintlify
   ```

2. Run the development server from the project root:

   ```bash
   mintlify dev docs/public
   ```

3. Open your browser to `http://localhost:4000`

### Deployment

The documentation is automatically deployed when changes are pushed to the main branch. Mintlify connects to your repository and builds the documentation site.

### Adding New Pages

1. Create a new Markdown file in the appropriate directory
2. Add the page to the navigation in `mint.json`
3. Link to the page from other relevant pages

### Formatting Guidelines

- Use Markdown for content formatting
- Use front matter for page metadata if needed
- Follow the [Mintlify documentation](https://mintlify.com/docs/quickstart) for advanced features

## Separation from Internal Documentation

This public documentation is separate from the internal documentation in the parent directory. The internal documentation is for development team use only and should not be published externally.

When adding new documentation:

- Public-facing documentation goes in this directory
- Internal development documentation goes in the parent directory
