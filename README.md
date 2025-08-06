Visual Understanding Chat Assistant
A powerful agentic chat assistant for visual understanding that processes video input, recognizes events, summarizes content, and engages in multi-turn conversations with intelligent guideline adherence detection.

working demo
https://drive.google.com/file/d/1doKL_hdew_PE2SxRvDTxRzcPHGsjdugx/view

🎯 Project Overview
This project demonstrates a comprehensive solution for video analysis and conversational AI, specifically designed to identify events within video streams and engage users in natural conversations about the detected content. The system excels at traffic scene analysis, pedestrian behavior detection, and guideline violation identification.
Key Capabilities:

Process video streams up to 2 minutes duration
Detect and timestamp specific events (vehicle movements, pedestrian crossings, traffic violations)
Generate intelligent summaries with guideline adherence analysis
Support natural multi-turn conversations with context retention
Provide interactive timeline navigation and event visualization

🏗️ Architecture Diagram
┌─────────────────────────────────────────────────────────────┐
│                    Frontend (React)                         │
├─────────────────┬─────────────────┬─────────────────────────┤
│   Video Upload  │   Chat Interface │   Event Timeline        │
│   & Player      │   & History     │   & Navigation          │
└─────────────────┴─────────────────┴─────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────┐
│                    API Gateway                              │
├─────────────────┬─────────────────┬─────────────────────────┤
│   Video Upload  │   Chat API      │   Analysis API          │
│   Endpoint      │   Endpoint      │   Endpoint              │
└─────────────────┴─────────────────┴─────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────┐
│                Backend Services                             │
├─────────────────┬─────────────────┬─────────────────────────┤
│   Video         │   Event         │   Conversation          │
│   Processing    │   Detection     │   Management            │
│   Service       │   Engine        │   Service               │
└─────────────────┴─────────────────┴─────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────┐
│                AI/ML Pipeline                               │
├─────────────────┬─────────────────┬─────────────────────────┤
│   Computer      │   Object        │   Natural Language      │
│   Vision        │   Detection     │   Processing            │
│   Models        │   Models        │   Models                │
└─────────────────┴─────────────────┴─────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────┐
│                Data Storage                                 │
├─────────────────┬─────────────────┬─────────────────────────┤
│   Video Files   │   Analysis      │   Chat History          │
│   Storage       │   Results       │   Database              │
└─────────────────┴─────────────────┴─────────────────────────┘
🛠️ Tech Stack Justification
Frontend Technologies

React 18: Chosen for its component-based architecture, excellent state management, and rich ecosystem. Perfect for building interactive UIs with real-time updates.
Tailwind CSS: Provides rapid UI development with consistent design patterns and responsive utilities.
Lucide React: Modern icon library offering scalable, customizable icons for enhanced UX.

Backend Technologies (Recommended)

Node.js with Express: Lightweight, fast, and excellent for handling video uploads and API requests. JavaScript across the stack ensures consistency.
Python with FastAPI: Alternative choice for AI/ML integration, offering async support and automatic API documentation.
Redis: For session management and chat history caching.
PostgreSQL: Robust database for storing analysis results and user data.

AI/ML Models & APIs

OpenAI GPT-4 Vision: For intelligent video analysis and natural conversation capabilities.
Google Cloud Video AI: For specialized video event detection and object tracking.
YOLO v8: Open-source option for real-time object detection in video streams.
OpenCV: For video processing, frame extraction, and basic computer vision tasks.

Infrastructure

AWS S3: Secure, scalable video file storage.
AWS Lambda: Serverless video processing for cost-effective scaling.
Docker: Containerization for consistent deployment across environments.

🚀 Setup and Installation Instructions
Prerequisites

Node.js (v18 or higher)
npm or yarn package manager
Git

Frontend Setup

Clone the repository:

bashgit clone <repository-url>
cd visual-understanding-chat-assistant

Install dependencies:

bashnpm install

Start the development server:

bashnpm start

Open your browser:
Navigate to http://localhost:3000

Backend Setup (Production Ready)

Install backend dependencies:

bashcd backend
npm install

Configure environment variables:

bashcp .env.example .env
# Edit .env with your API keys and configuration

Set up database:

bashnpm run db:migrate
npm run db:seed

Start the backend server:

bashnpm run dev
Docker Deployment

Build and run with Docker Compose:

bashdocker-compose up --build
This will start all services including the frontend, backend, database, and Redis.
📖 Usage Instructions
Basic Workflow

Upload Video:

Click the upload area or drag and drop a video file
Supported formats: MP4, AVI, MOV, WebM
Maximum duration: 2 minutes
Maximum file size: 50MB (demo limitation)


Analyze Video:

Click "Analyze Video" button
Wait for processing (typically 10-30 seconds)
Review the generated timeline and event summary


Interactive Chat:

Use predefined quick questions or type custom queries
Ask follow-up questions for detailed explanations
Click on timeline events to jump to specific moments



Example Video Scenarios
Traffic Scene Analysis
Sample Questions:
- "What is the most significant event in this video?"
- "How did the camera vehicle react to the pedestrian?"
- "What traffic violations were detected?"
- "Describe the overall environment and lighting conditions"
Expected Responses

Event Detection: "Pedestrian crossing detected at 00:03 - High risk violation"
Vehicle Analysis: "Camera mounted on motorcycle, continued forward without evasive action"
Environment: "Urban road, late afternoon lighting, multi-lane traffic"

Advanced Features
Timeline Navigation

Click on any detected event to jump to that timestamp
Color-coded events: Red (violations), Green (normal), Orange (warnings)
Hover over events for detailed descriptions

Conversation Context

Assistant remembers previous questions and answers
Can reference earlier parts of the conversation
Maintains context about the specific video being analyzed

Export Options

Chat history can be copied for documentation
Analysis results can be saved for reporting
Timeline data available for further processing

API Integration Examples
Video Upload
javascriptconst formData = new FormData();
formData.append('video', videoFile);

const response = await fetch('/api/upload', {
  method: 'POST',
  body: formData
});
Chat Interaction
javascriptconst chatResponse = await fetch('/api/chat', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({
    message: "What happened at 3 seconds?",
    videoId: "video_123",
    sessionId: "session_456"
  })
});
🎯 Features Demonstrated
Core Features

✅ Video Event Recognition: Automated detection of vehicles, pedestrians, and traffic events
✅ Guideline Adherence Analysis: Traffic violation and safety compliance checking
✅ Multi-turn Conversations: Natural dialogue with context awareness
✅ Real-time Processing: Interactive video analysis with immediate feedback
✅ Timeline Navigation: Click-to-seek event-based video control

Advanced Features

✅ Responsive Design: Works seamlessly on desktop and mobile devices
✅ Error Handling: Robust file validation and processing error management
✅ Performance Optimization: Efficient video processing with progress indicators
✅ Accessibility: Keyboard navigation and screen reader support
✅ Export Capabilities: Save analysis results and chat histories

🧪 Testing
Sample Test Cases

Traffic Scene Video: Upload provided sample video and verify:

Pedestrian crossing detection at ~3 second mark
Vehicle type identification (motorcycle)
Environment description accuracy
Chat responses match expected Q&A format


Multi-turn Conversation: Test conversation flow:

Ask initial question about main event
Follow up with specific timing questions
Verify context retention across multiple exchanges


Error Handling: Test edge cases:

Upload oversized video files
Upload non-video files
Network interruption during processing



Performance Benchmarks

Video upload: < 5 seconds for 50MB files
Analysis processing: < 30 seconds for 2-minute videos
Chat response time: < 2 seconds
Timeline navigation: < 100ms response time

🎬 Demo Video
[Link to Demo Video]: A 3-minute demonstration showing:

Video upload process
Automatic event detection and analysis
Interactive timeline navigation
Multi-turn conversation examples
Guideline violation identification

🔮 Future Enhancements
Planned Features

Real-time Streaming: Support for live video feeds
Multi-language Support: Conversations in multiple languages
Advanced Analytics: Statistical analysis and reporting dashboards
Custom Guidelines: User-defined rule sets for specific use cases
Collaborative Features: Multi-user sessions and shared analysis

Scalability Improvements

Microservices Architecture: Split processing into specialized services
CDN Integration: Global video delivery network
Auto-scaling: Dynamic resource allocation based on demand
Caching Layer: Intelligent caching for repeated analysis requests

🤝 Contributing

Fork the repository
Create a feature branch (git checkout -b feature/amazing-feature)
Commit your changes (git commit -m 'Add amazing feature')
Push to the branch (git push origin feature/amazing-feature)
Open a Pull Request

📄 License
This project is licensed under the MIT License - see the LICENSE file for details.
🙏 Acknowledgments

OpenAI for GPT-4 Vision API
React community for excellent documentation
Tailwind CSS team for the utility-first framework
All contributors and testers who helped improve this project
