# Quickstart Guide

This guide will help you quickly integrate the SmarterServices Platform into your application.

## Installation Options

### Option 1: SmarterElements Integration

The fastest way to integrate with SmarterServices is through our SmarterElements library:

```html
<!-- Include the SmarterElements library -->
<script src="https://cdn.smarterproctoring.com/elements/v1/smarter-elements.umd.js"></script>

<div id="proctor-element"></div>

<script>
  // Initialize SmarterElements
  const elements = window.SmarterElements({
    environment: 'production',
    apiKey: 'YOUR_API_KEY',
    baseUrl: 'https://api.smarterservices.com',
  });

  // Create a proctoring element
  const proctorElement = elements.create('proctorSession', {
    examId: 'exam123',
    userId: 'user456',
    // Additional configuration options
  });

  // Mount the element to the container
  proctorElement.mount('#proctor-element');
</script>
```

### Option 2: React Integration

For React applications, we provide a React component library:

```bash
npm install @smarterproctoring/elements
```

```jsx
import React from 'react';
import { ProctorSession } from '@smarterproctoring/elements';

function ExamComponent() {
  return (
    <ProctorSession
      examId="exam123"
      userId="user456"
      onSessionStart={session => console.log('Session started', session)}
      onSessionEnd={session => console.log('Session ended', session)}
    />
  );
}
```

### Option 3: API Integration

For complete customization, you can integrate directly with our APIs:

```bash
# Install the SmarterServices API client
npm install @smarterservices/api-client
```

```js
import { SmarterServicesClient } from '@smarterservices/api-client';

// Initialize the client
const client = new SmarterServicesClient({
  apiKey: 'YOUR_API_KEY',
  environment: 'production',
});

// Create a proctoring session
async function createSession() {
  const session = await client.proctoring.createSession({
    examId: 'exam123',
    userId: 'user456',
    type: 'automated',
    settings: {
      // Proctoring settings
    },
  });

  console.log('Session created:', session);
  return session;
}
```

## Next Steps

- Explore the [SmarterElements documentation](./smarter-elements/overview) for detailed component information
- Check out our [API Reference](./api-reference/authentication) for direct API integration
- Learn about [LMS Integration](./guides/lms-integration) for popular learning management systems
