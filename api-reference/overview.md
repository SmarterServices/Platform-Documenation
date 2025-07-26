# Authentication

The SmarterServices API uses JWT (JSON Web Tokens) for authentication. All API requests must include a valid token in the Authorization header.

## Obtaining an API Key

To use the SmarterServices API, you need to obtain API credentials:

1. Log in to the [SmarterServices Dashboard](https://app.smarterservices.com)
2. Navigate to Settings > API Keys
3. Click "Create New API Key"
4. Give your API key a name and select the appropriate permissions
5. Store your API key and secret securely

## Authentication Flow

### Step 1: Request an Access Token

```javascript
const response = await fetch('https://api.smarterservices.com/v1/auth/token', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify({
    apiKey: 'YOUR_API_KEY',
    apiSecret: 'YOUR_API_SECRET',
  }),
});

const { token, expiresIn } = await response.json();
```

### Step 2: Use the Token in API Requests

```javascript
const examResponse = await fetch('https://api.smarterservices.com/v1/exams', {
  headers: {
    Authorization: `Bearer ${token}`,
    'Content-Type': 'application/json',
  },
});

const exams = await examResponse.json();
```

## Token Expiration

Access tokens expire after 24 hours. Your application should handle token expiration by requesting a new token when needed.

## Using with API Client Libraries

Our client libraries handle authentication automatically:

```javascript
import { SmarterServicesClient } from '@smarterservices/api-client';

const client = new SmarterServicesClient({
  apiKey: 'YOUR_API_KEY',
  apiSecret: 'YOUR_API_SECRET',
});

// The client handles token management automatically
const exams = await client.exams.list();
```

## Security Best Practices

- **Never** expose your API secret in client-side code
- Store API credentials securely in environment variables
- Implement proper token management and rotation
- Use HTTPS for all API requests
- Apply the principle of least privilege when creating API keys
