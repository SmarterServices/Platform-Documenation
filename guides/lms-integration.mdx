# LMS Integration Guide

This guide explains how to integrate the SmarterServices Platform with popular Learning Management Systems (LMS).

## Integration Options

SmarterServices offers multiple integration options for Learning Management Systems:

1. **LTI Integration**: Using Learning Tools Interoperability standard
2. **SmarterElements**: Embedding UI components directly in your LMS
3. **API Integration**: Custom integration using our comprehensive API
4. **SSO Integration**: Single sign-on for seamless user experience

## Canvas Integration

### LTI Integration

1. Log in to Canvas as an administrator
2. Navigate to Admin > Settings > Apps
3. Click "View App Configurations" and then "+ App"
4. Select "By URL" and enter the following details:
   - Name: SmarterServices
   - Consumer Key: (Your LTI key from SmarterServices dashboard)
   - Shared Secret: (Your LTI secret from SmarterServices dashboard)
   - Launch URL: `https://app.smarterservices.com/lti/launch`
   - Domain: `app.smarterservices.com`
5. Configure privacy settings and submit

### SmarterElements Integration

For a more customized experience, you can embed SmarterElements directly in Canvas:

1. Navigate to the course where you want to add SmarterServices
2. Create a new page or edit an existing one
3. Click the HTML Editor button
4. Add the following code:

```html
<div id="smarter-proctor-element"></div>
<script src="https://cdn.smarterproctoring.com/elements/v1/smarter-elements.umd.js"></script>
<script>
  const elements = window.SmarterElements({
    environment: 'production',
    apiKey: 'YOUR_API_KEY',
    lms: {
      type: 'canvas',
      courseId: '{{course_id}}',
      userId: '{{user_id}}',
    },
  });

  const proctorElement = elements.create('proctorSession', {
    examId: 'YOUR_EXAM_ID',
  });

  proctorElement.mount('#smarter-proctor-element');
</script>
```

## Blackboard Integration

### LTI Integration

1. Log in to Blackboard as an administrator
2. Navigate to System Admin > LTI Tool Providers
3. Click "Register Provider Domain"
4. Enter the following details:
   - Provider Domain: `app.smarterservices.com`
   - Provider Domain Status: Approved
   - Default Configuration: Set globally
   - Tool Provider Key: (Your LTI key from SmarterServices dashboard)
   - Tool Provider Secret: (Your LTI secret from SmarterServices dashboard)
5. Configure additional settings and submit

### Blackboard Building Block

For Blackboard Learn installations that support Building Blocks:

1. Download the SmarterServices Building Block from your dashboard
2. Navigate to System Admin > Building Blocks > Installed Tools
3. Click "Upload Building Blocks"
4. Select the downloaded .war file and install
5. Configure the Building Block settings

## Moodle Integration

### LTI Integration

1. Log in to Moodle as an administrator
2. Navigate to Site administration > Plugins > Activity modules > External tool > Manage tools
3. Click "configure a tool manually"
4. Enter the following details:
   - Tool name: SmarterServices
   - Tool URL: `https://app.smarterservices.com/lti/launch`
   - Consumer key: (Your LTI key from SmarterServices dashboard)
   - Shared secret: (Your LTI secret from SmarterServices dashboard)
5. Configure additional settings and save

### SmarterElements in Moodle

To embed SmarterElements in Moodle:

1. Navigate to your course
2. Turn editing on
3. Add an activity or resource > HTML
4. Click "HTML source" in the editor
5. Add the SmarterElements code (similar to Canvas example)

## API Integration

For custom LMS solutions or deeper integration, use our comprehensive API:

```javascript
import { SmarterServicesClient } from '@smarterservices/api-client';

// Initialize the client
const client = new SmarterServicesClient({
  apiKey: 'YOUR_API_KEY',
  environment: 'production',
});

// Create a proctoring session linked to your LMS
async function createLmsSession(courseId, examId, userId) {
  const session = await client.proctoring.createSession({
    examId: examId,
    userId: userId,
    lmsData: {
      lmsType: 'canvas',
      courseId: courseId,
      resourceId: examId,
    },
  });

  return session;
}
```

## Troubleshooting

### Common Issues

- **Authentication Failures**: Verify your LTI key and secret
- **Missing User Data**: Ensure proper LTI parameter passing
- **Display Problems**: Check browser console for JavaScript errors
- **Session Creation Failures**: Verify API key permissions

For additional help, contact SmarterServices support at support@smarterservices.com.
