<div align="center">

# PointOfView (POV)

A full-stack video streaming platform inspired by YouTube that uses a recommendation engine to suggest videos based on user watch history and viewing preferences.

<br>

<img src="https://img.shields.io/badge/React-Frontend-61DAFB?logo=react&logoColor=white" />
<img src="https://img.shields.io/badge/Flask-Backend-000000?logo=flask&logoColor=white" />
<img src="https://img.shields.io/badge/MySQL-Database-4479A1?logo=mysql&logoColor=white" />
<img src="https://img.shields.io/badge/Stripe-Payments-635BFF?logo=stripe&logoColor=white" />
<img src="https://img.shields.io/badge/Scikit--Learn-KNN%20Recommendations-F7931E?logo=scikitlearn&logoColor=white" />

</div>

---

## Overview

PointOfView (POV) is a full-stack video streaming platform inspired by YouTube. Users can watch videos, search content, explore categories, interact with channels, and receive personalized video recommendations.

The platform leverages a machine learning recommendation engine built using the K-Nearest Neighbors (KNN) algorithm to analyze user watch history and viewing preferences, delivering a more personalized content discovery experience.

In addition, POV integrates Stripe for secure online payments, enabling premium memberships or subscription-based features.

---

## Key Features

### User Authentication

- Secure user registration system allowing new users to create personalized accounts.
- Login functionality that verifies user credentials and provides access to platform features.
- Logout support for safely ending active user sessions.
- Authentication layer designed to maintain user-specific data such as watch history, subscriptions, likes, and recommendations.
- Enables personalized experiences by associating user activity with individual accounts.

**Backend Endpoints**

```text
/signup
/login
/logout
```

---

### Personalized Video Recommendations

The recommendation engine is one of the core features of the platform.

It analyzes:

- User watch history
- Video categories and genres
- User viewing patterns

Using:

- Scikit-Learn
- K-Nearest Neighbors (KNN)

The system identifies similar viewing interests and recommends relevant videos to users.

#### Recommendation Highlights

- Tracks videos previously watched by a user.
- Identifies frequently consumed categories and genres.
- Uses similarity-based matching through the KNN algorithm.
- Generates personalized recommendations instead of displaying generic content.
- Continuously improves recommendations as users interact with more videos.
- Creates a content discovery experience tailored to individual viewing preferences.

---

### Video Streaming Experience

Users can:

- Watch videos
- Search videos
- Browse recommended content
- Explore trending and categorized videos

The homepage dynamically displays personalized recommendations based on user activity.

**Route**

```text
/homepage
```

#### Platform Experience

- Provides a familiar YouTube-style content browsing experience.
- Displays recommended videos directly on the homepage.
- Supports seamless navigation between videos and related content.
- Enables quick access to newly discovered videos through recommendation feeds.
- Delivers responsive video browsing across different device sizes.

---

### Video Categories

Users can explore videos across multiple categories:

- Business
- Technology
- Sports
- Health
- Entertainment
- National
- International

This enables easier content discovery and navigation.

#### Category Features

- Organizes content into clearly defined genres and topics.
- Simplifies navigation for users interested in specific subject areas.
- Supports content discovery beyond a user's recommendation feed.
- Helps users explore trending content within individual categories.
- Improves platform usability through structured content organization.

---

### Video Interaction

Each video page supports:

- View count tracking
- Likes
- Comments
- Related video recommendations

When a video is opened:

- Views are updated
- Comments are loaded
- Likes are loaded
- Recommended videos are displayed

#### User Engagement Features

- Automatically records video views to track engagement metrics.
- Displays related content to encourage continued platform usage.
- Loads interaction data dynamically for an updated viewing experience.
- Encourages user participation through likes and comments.
- Mimics the workflow and engagement model commonly found on modern video streaming platforms.

---

### Likes & Comments

The platform stores and manages:

```text
liked_videos
comments
watch_history
```

Users can:

- Like videos
- Comment on videos
- Engage with content creators

#### Social Interaction Features

- Allows users to express interest and engagement through likes.
- Supports discussion and feedback through comment sections.
- Maintains persistent interaction records within the database.
- Helps generate engagement data that can contribute to recommendation quality.
- Encourages community interaction between viewers and creators.

---

### Channels & Subscriptions

Users can:

- Visit channel pages
- View channel information
- Subscribe to channels
- Track subscribed creators

Channel-related modules include:

```text
Channel
ChannelInfo
Subscription
```

#### Creator Features

- Dedicated channel pages for content creators.
- Channel profiles displaying creator information and uploaded content.
- Subscription functionality allowing users to follow preferred creators.
- Structured channel management for organizing creator content.
- Supports long-term viewer engagement through creator-following mechanisms.

---

### Payment Integration

POV includes secure payment processing using Stripe.

Supported through:

```bash
@stripe/react-stripe-js
@stripe/stripe-js
```

Potential use cases include:

- Premium memberships
- Subscription plans
- Creator support features

#### Payment Features

- Integrates Stripe using official frontend SDKs.
- Supports secure online payment workflows.
- Enables future monetization and subscription-based services.
- Provides a scalable foundation for premium platform functionality.
- Follows industry-standard payment processing practices.

---

## Technology Stack

### Frontend

| Technology | Purpose |
|------------|---------|
| React.js | User Interface |
| React Router DOM | Client-side Routing |
| Bootstrap | Responsive Design |
| Axios | API Communication |
| React Icons | UI Icons |

### Backend

| Technology | Purpose |
|------------|---------|
| Flask | REST API Backend |
| Python | Server-side Development |

### Database

| Technology | Purpose |
|------------|---------|
| MySQL | Data Storage |

### Machine Learning

| Technology | Purpose |
|------------|---------|
| Scikit-Learn | Recommendation Engine |
| KNN (Nearest Neighbors) | Personalized Recommendations |

### Payments

| Technology | Purpose |
|------------|---------|
| Stripe | Secure Payment Processing |

---

## Recommendation System Architecture

The recommendation engine uses the K-Nearest Neighbors (KNN) algorithm to provide personalized suggestions.

### Workflow

```text
User Activity
      │
      ▼
Watch History Collection
      │
      ▼
Genre Preference Analysis
      │
      ▼
KNN Similarity Matching
      │
      ▼
Personalized Recommendations
```

### Recommendation Factors

- Previously watched videos
- Frequently viewed categories
- Genre similarity
- User engagement patterns

---

## System Architecture

```text
┌─────────────────────────────────────────┐
│                Frontend                 │
│      React + Bootstrap + Axios          │
└───────────────────┬─────────────────────┘
                    │
                    ▼
┌─────────────────────────────────────────┐
│               Flask API                 │
│ Authentication • Videos • Channels      │
└───────────────────┬─────────────────────┘
                    │
        ┌───────────┴───────────┐
        ▼                       ▼
┌─────────────────┐   ┌──────────────────┐
│      MySQL      │   │ Recommendation   │
│    Database     │   │   Engine (KNN)   │
└─────────────────┘   └──────────────────┘
                    │
                    ▼
           ┌────────────────┐
           │     Stripe     │
           │    Payments    │
           └────────────────┘
```

---

## Installation

### Clone the Repository

```bash
git clone <repository-url>
```

### Navigate to Project Directory

```bash
cd PointOfView
```

### Install Frontend Dependencies

```bash
npm install
```

### Start Frontend

```bash
npm start
```

Application runs at:

```text
http://localhost:3000
```

---

## Frontend Dependencies

```bash
npm install react-scripts
npm install bootstrap
npm install react-icons
npm install react-router-dom
npm install axios
npm install @stripe/react-stripe-js
npm install @stripe/stripe-js
```

---

## Project Structure

```text
PointOfView
│
├── frontend/
│
│   ├── public/
│   └── src/
│       ├── components/
│       ├── pages/
│       ├── assets/
│       ├── services/
│       ├── routes/
│       ├── App.js
│       └── index.js
│
├── backend/
│   ├── algo.py
│   ├── routes/
│   ├── models/
│   └── services/
│
├── package.json
├── package-lock.json
├── .gitignore
└── README.md
```

---

## Security Considerations

Sensitive credentials should never be committed to source control.

Use environment variables for configuration:

```env
REACT_APP_STRIPE_PUBLIC_KEY=YOUR_PUBLIC_KEY
```

Store all secret keys securely on the backend.

---

## Learning Outcomes

This project provided hands-on experience with:

- Building a complete full-stack web application using React, Flask, and MySQL.
- Designing reusable frontend components and scalable application structures.
- Implementing authentication workflows including user registration and login systems.
- Developing RESTful APIs for communication between frontend and backend services.
- Integrating machine learning concepts into a real-world software project.
- Building and deploying a recommendation engine using the KNN algorithm.
- Managing user-generated content such as comments, likes, subscriptions, and watch history.
- Implementing secure online payment workflows using Stripe.
- Designing responsive user interfaces with Bootstrap and React.
- Handling asynchronous API communication using Axios.
- Structuring large-scale projects with clear separation of concerns.
- Using Git and GitHub for version control, collaboration, and project management.

---

## Project Summary

PointOfView (POV) is a full-stack video streaming platform inspired by YouTube. The application enables users to watch, search, like, comment on, and subscribe to video channels. A machine learning-powered recommendation engine built using KNN analyzes user watch history and viewing preferences to deliver personalized video suggestions. The platform is developed using React, Flask, MySQL, Scikit-Learn, and Stripe.
