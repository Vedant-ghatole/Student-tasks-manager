# Student Tasks Manager

A comprehensive Firebase-powered web application for managing academic tasks, assignments, and communication between students, teachers, and CRs (Class Representatives).

## Features

### 🔐 Authentication & Authorization
- **Email/Password Authentication** with Firebase Auth
- **Google OAuth Integration** for seamless sign-in
- **Role-based Access Control** (Student, Teacher, CR/SRC)
- **Password Reset** via email
- **Secure Session Management**

### 📊 Dashboard
- **Real-time Statistics** with live updates
- **Role-specific Widgets** and quick actions
- **Upcoming Deadlines** with countdown timers
- **Latest Announcements** with audio support
- **WhatsApp Quick Links** for instant communication
- **Daily Motivational Quotes**

### 📝 Assignment Management
- **Create/Edit Assignments** (Teachers)
- **Submit Assignments** with file uploads (Students)
- **Deadline Tracking** with automatic status updates
- **File Upload Support** (PDF, DOCX, ZIP)
- **Assignment Statistics** and progress tracking

### ✅ To-Do Lists
- **Personal & Academic Tasks** with separate tabs
- **Priority-based Organization** (Low, Medium, High)
- **Due Date Management** with reminders
- **Drag & Drop** task reordering
- **Real-time Synchronization**

### 🔔 Notifications & Communication
- **Push Notifications** via Firebase Cloud Messaging
- **Real-time Updates** using Firestore listeners
- **WhatsApp Integration** for direct contact
- **Audio Announcements** with voice messages
- **In-app Messaging** system

### 📚 Study Materials
- **File Upload & Management** (Teachers/CRs)
- **Material Categorization** by subject
- **Search & Filter** functionality
- **Download Tracking**
- **Version Control** for updated materials

### 📈 Attendance Tracking
- **Visual Charts** using Chart.js
- **Subject-wise Tracking**
- **Percentage Calculations**
- **Attendance Alerts** for low attendance
- **Export Functionality**

### 🏛️ Library Management
- **Book Catalog** with availability status
- **Borrow Requests** system
- **Due Date Reminders**
- **Book Search** functionality
- **Request Approval** workflow

### 🚨 Issue Reporting
- **Student Issue Submission**
- **Teacher Response System**
- **Category-based Organization**
- **Status Tracking**
- **Escalation Support**

## Tech Stack

### Frontend
- **HTML5** - Semantic markup
- **TailwindCSS** - Utility-first CSS framework
- **Bootstrap 5** - Component library
- **Vanilla JavaScript** - ES6+ features
- **Chart.js** - Data visualization
- **Font Awesome** - Icons

### Backend & Services
- **Firebase v9 Modular SDK** - Backend-as-a-Service
- **Firebase Authentication** - User management
- **Cloud Firestore** - NoSQL database
- **Firebase Storage** - File storage
- **Firebase Cloud Messaging** - Push notifications
- **Firebase Hosting** - Web hosting

### Development Tools
- **Firebase CLI** - Development and deployment
- **ES6 Modules** - Modern JavaScript
- **Service Workers** - Offline support (planned)

## Project Structure

```
student_tasks_manager/
├── index.html              # Landing page with login/signup
├── dashboard.html          # Main dashboard
├── assignments.html        # Assignment management
├── todo.html              # To-do list management
├── css/
│   └── style.css          # Custom styles
├── js/
│   ├── firebase-config.js # Firebase configuration
│   ├── auth.js            # Authentication module
│   ├── dashboard.js       # Dashboard functionality
│   ├── assignments.js     # Assignment management
│   └── todo.js            # To-do list functionality
├── firebase.json          # Firebase hosting config
├── firestore.rules        # Firestore security rules
├── storage.rules          # Storage security rules
└── README.md              # Project documentation
```

## Setup Instructions

### Prerequisites
- Node.js (v14 or higher)
- Firebase CLI (`npm install -g firebase-tools`)
- Modern web browser with ES6 support

### 1. Firebase Project Setup

1. **Create Firebase Project**
   ```bash
   # Go to Firebase Console (https://console.firebase.google.com)
   # Create a new project
   # Enable Authentication, Firestore, Storage, and Hosting
   ```

2. **Enable Authentication Methods**
   - Email/Password
   - Google Sign-in
   - Configure authorized domains

3. **Set up Firestore Database**
   - Create database in production mode
   - Set up security rules

4. **Configure Storage**
   - Set up storage bucket
   - Configure security rules

### 2. Local Development Setup

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd student_tasks_manager
   ```

2. **Install Firebase CLI**
   ```bash
   npm install -g firebase-tools
   ```

3. **Login to Firebase**
   ```bash
   firebase login
   ```

4. **Initialize Firebase Project**
   ```bash
   firebase init
   # Select: Hosting, Firestore, Storage
   # Use existing project
   # Set public directory to "." (current directory)
   ```

5. **Update Firebase Configuration**
   - Replace `your-api-key` in `js/firebase-config.js` with your actual Firebase config
   - Update VAPID key for push notifications

### 3. Configuration

1. **Firebase Config** (`js/firebase-config.js`)
   ```javascript
   const firebaseConfig = {
       apiKey: "your-actual-api-key",
       authDomain: "your-project.firebaseapp.com",
       projectId: "your-project-id",
       storageBucket: "your-project.appspot.com",
       messagingSenderId: "your-sender-id",
       appId: "your-app-id"
   };
   ```

2. **VAPID Key** (for push notifications)
   ```javascript
   const token = await getToken(messaging, { 
       vapidKey: 'your-vapid-key' 
   });
   ```

### 4. Deploy to Firebase

1. **Deploy Security Rules**
   ```bash
   firebase deploy --only firestore:rules
   firebase deploy --only storage
   ```

2. **Deploy to Hosting**
   ```bash
   firebase deploy --only hosting
   ```

3. **Access Your App**
   - Your app will be available at: `https://your-project-id.web.app`

## Usage Guide

### For Students
1. **Sign up/Login** with email or Google account
2. **View Dashboard** for overview of tasks and deadlines
3. **Submit Assignments** with file uploads
4. **Manage To-Do Lists** for personal and academic tasks
5. **Track Attendance** and view statistics
6. **Report Issues** to teachers
7. **Access Study Materials** uploaded by teachers

### For Teachers
1. **Create Assignments** with deadlines and file attachments
2. **Upload Study Materials** for students
3. **Track Submissions** and grade assignments
4. **Manage Attendance** records
5. **Respond to Student Issues**
6. **Post Announcements** with audio support
7. **Monitor Class Progress**

### For CRs (Class Representatives)
1. **Post Class Announcements**
2. **Upload Study Materials**
3. **Manage Class Communications**
4. **Coordinate with Teachers**
5. **Monitor Student Engagement**

## Security Features

- **Role-based Access Control** - Different permissions for different user types
- **Firestore Security Rules** - Database-level security
- **Storage Security Rules** - File upload restrictions
- **Authentication Required** - All sensitive operations require login
- **Input Validation** - Client and server-side validation
- **File Type Restrictions** - Only allowed file types can be uploaded
- **Size Limits** - File upload size restrictions

## Performance Optimizations

- **Firebase v9 Modular SDK** - Tree-shaking for smaller bundle size
- **Lazy Loading** - Load modules only when needed
- **Offline Support** - Firestore persistence for offline access
- **Image Optimization** - Compressed images and lazy loading
- **Caching** - Browser caching for static assets
- **CDN** - Firebase Hosting CDN for global performance

## Browser Support

- **Chrome** 80+
- **Firefox** 75+
- **Safari** 13+
- **Edge** 80+

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support and questions:
- Create an issue in the repository
- Contact the development team
- Check the Firebase documentation

## Roadmap

### Phase 2 Features
- [ ] **Mobile App** (React Native/Flutter)
- [ ] **Advanced Analytics** and reporting
- [ ] **Calendar Integration** with Google Calendar
- [ ] **Video Conferencing** integration
- [ ] **AI-powered** task recommendations
- [ ] **Multi-language** support
- [ ] **Advanced Search** functionality
- [ ] **Export/Import** data functionality

### Phase 3 Features
- [ ] **Advanced Notifications** with scheduling
- [ ] **Group Projects** management
- [ ] **Peer Review** system
- [ ] **Gamification** elements
- [ ] **Integration** with LMS platforms
- [ ] **Advanced Security** features
- [ ] **Performance Monitoring** and analytics

---

**Built with ❤️ using Firebase and modern web technologies**
