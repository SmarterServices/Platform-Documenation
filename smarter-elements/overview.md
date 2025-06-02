# SmarterElements Overview

SmarterElements is a JavaScript library that allows you to embed UI components into any web application, similar to how Stripe Elements works. This library provides a simple way to integrate proctoring functionality into your application without having to build the UI components yourself.

## What are SmarterElements?

SmarterElements are pre-built, customizable UI components that you can easily embed in your web application. These components handle complex functionality like:

- Exam information display
- Proctor scheduling
- Identity verification
- Exam verification
- Proctoring sessions

Each element is designed to be:

- **Easy to integrate**: Simple JavaScript API
- **Customizable**: Matches your application's design
- **Responsive**: Works on all devices
- **Accessible**: Built with accessibility in mind
- **Secure**: Handles sensitive operations securely

## Available Elements

The SmarterElements library includes several components:

- **ExamCard**: Displays exam information in a card format
- **ProctorSchedule**: Shows a proctor's schedule in a calendar-like format
- **ExamVerification**: Handles verification steps before an exam
- **IdentityCheck**: Handles identity verification for exam takers
- **ProctorSession**: Manages the entire proctoring session
- **ElementsLayout**: Provides a container for elements with auto-resizing iframe support

## Integration Methods

SmarterElements can be integrated in several ways:

### Direct Script Include

```html
<script src="https://cdn.smarterproctoring.com/elements/v1/smarter-elements.umd.js"></script>
```

### NPM Package

```bash
npm install @smarterproctoring/elements
```

### React Components

```jsx
import { ExamCard } from '@smarterproctoring/elements/react';
```

## Basic Example

Here's a simple example of using SmarterElements:

```html
<div id="exam-card-element"></div>

<script>
  // Initialize SmarterElements
  const elements = window.SmarterElements({
    environment: 'production',
    apiKey: 'YOUR_API_KEY',
  });

  // Create an Exam Card element
  const examCard = elements.create('examCard', {
    exam: {
      id: 'exam123',
      title: 'Mathematics 101',
      course: 'MATH 101 - Calculus I',
      description: 'Final Exam - Spring 2025',
      date: '2025-06-15',
      startTime: '9:00 AM',
      endTime: '11:00 AM',
      duration: 120,
    },
  });

  // Mount the element to the container
  examCard.mount('#exam-card-element');

  // Listen for events
  examCard.on('exam-selected', data => {
    console.log('Exam selected:', data.examId);
  });
</script>
```

## Next Steps

- Learn how to [install SmarterElements](./installation)
- Explore the available [components](./components)
- Understand [events and callbacks](./events)
- Customize appearance with [theming](./theming)
