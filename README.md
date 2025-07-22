# Task Manager Web App

A modern, responsive task management application with Google Analytics integration.

## Features

- ✅ Add, complete, and delete tasks
- 📊 Real-time statistics (total, completed, pending tasks)
- 🔍 Filter tasks by status (all, pending, completed)
- 💾 Local storage persistence
- 📱 Mobile-responsive design
- 📈 Google Analytics tracking for user interactions

## Setup Instructions

### 1. Google Analytics Setup

1. Go to [Google Analytics](https://analytics.google.com/)
2. Create a new account or use an existing one
3. Create a new property for your webapp
4. Get your **Measurement ID** (format: G-XXXXXXXXXX)

### 2. Configure Analytics

1. Open `index.html`
2. Find the two instances of `GA_MEASUREMENT_ID`
3. Replace both with your actual Measurement ID:

```html
<!-- Replace GA_MEASUREMENT_ID with your actual ID -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());
    gtag('config', 'G-XXXXXXXXXX');
</script>
```

### 3. Launch the App

Simply open `index.html` in your web browser or serve it using a local server:

```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx serve .

# Using PHP
php -S localhost:8000
```

## Analytics Events Tracked

The app automatically tracks these user interactions:

- `page_view` - When the app loads
- `task_added` - When a new task is created
- `task_completed` - When a task is marked as complete
- `task_uncompleted` - When a task is marked as incomplete
- `task_deleted` - When a task is removed
- `filter_changed` - When users switch between filter views

## File Structure

```
.
├── index.html      # Main HTML file
├── styles.css      # CSS styles
├── script.js       # JavaScript functionality
└── README.md       # This file
```

## Browser Compatibility

- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

## Privacy Note

This app stores task data locally in your browser and sends anonymous usage analytics to Google Analytics. No personal task content is transmitted to external servers.