# Class Roll Call System

## Project Overview
A classroom roll call system that supports both random and sequential student number calling modes.

## Basic Requirements

### Core Features
1. Import student lists from Excel files (including student ID, name, major, etc.) and store them in a FREE Online database
2. Support both random and sequential roll call modes
3. Database storage for roll call information with scoring rankings and visualization (bar charts or line charts)
4. Export scoring details from the database
5. Display called student's name and ID

### Scoring Rules
- Initial score: 0
- Present when called: +1 point
- Question response:
  - Accurately repeating the question: +0.5 points
  - Unable to repeat the question: -1 point
  - Correctly answering questions: +0.5 to +3 points based on performance
- Higher total score leads to lower probability of being randomly selected

## Technical Stack

### Frontend
- Vue.js framework with MVVM architecture
- Encapsulated Axios for network operations
- ElementUI for component library
- Interactive mouse effects and animations

### Backend
- SpringBoot framework
- MyBatis and MyBatis-Plus for persistence layer
- MySQL for main data storage
- Redis for hot data caching
- JWT for authentication
- Bcrypt hash algorithm for password encryption
- Swagger for API documentation
- EasyExcel for student list import
- Docker + Nginx for deployment

## Project Structure

### Frontend Directory Structure
```
├─api           -- API encapsulation
├─assets        -- Resources (images, etc.)
│  ├─home       -- Homepage resources
│  └─login      -- Login page resources
├─components    -- Components
├─pages         -- Pages
├─router        -- Route definitions
└─utils         -- Utility classes
```

### Backend Directory Structure
```
├─common        -- Common classes
├─config        -- Configuration
├─controller    -- Controllers
├─dto           -- DTOs
│  ├─req        -- Request DTOs
│  └─resp       -- Response DTOs
├─entity        -- Database entities
├─exception     -- Global exception handler
├─filter        -- Global filters
├─mapper        -- Database operations
├─service       -- Services
│  └─impl       -- Service implementations
└─util          -- Utilities
    └─cache     -- Cache utilities
```

## Key Features

### Random Events System
- Equal Chance: True random selection without weights
- Double Penalty: Doubles the deduction points
- Lucky Wednesday: Triple points for attendance and answers

### Performance Optimization
1. First API Call Optimization
   - Implemented lazy loading
   - Service preheating during startup
   
2. Roll Call Cache Optimization
   - Redis caching implementation
   - Cache Aside strategy for synchronization
   - Optimized data structure for student information storage

## Testing
- Comprehensive interface testing using JUnit
- Mock testing for service layer
- Performance testing using JProfiler
- HTTP request testing for API endpoints

## Development Tools
- MasterGo for UI/UX design
- Visual Studio Code/IDEA for development
- Git for version control
- Docker for containerization
