# Requirements Document

## Introduction

Sniplet is a Code Snippet Marketplace frontend application built in React that enables developers to share, discover, and manage reusable code snippets across multiple programming languages. The platform provides a community-driven environment where users can browse syntax-highlighted code snippets, search and filter by tags or programming languages, and contribute their own snippets. The application includes user authentication through Supabase and focuses on creating a seamless experience for code sharing without complex integrations like GitHub or payment systems.

## Requirements

### Requirement 1

**User Story:** As a developer, I want to browse and discover code snippets on a landing page, so that I can quickly find useful code examples and see what the community is sharing.

#### Acceptance Criteria

1. WHEN a user visits the application THEN the system SHALL display a landing page with featured snippets
2. WHEN the landing page loads THEN the system SHALL show syntax-highlighted code previews for featured snippets
3. WHEN a user views the landing page THEN the system SHALL provide navigation to other sections of the application
4. WHEN featured snippets are displayed THEN the system SHALL show snippet title, language, author, and preview of the code

### Requirement 2

**User Story:** As a developer, I want to search and filter code snippets by language and tags, so that I can find specific types of code examples relevant to my needs.

#### Acceptance Criteria

1. WHEN a user accesses the snippet feed THEN the system SHALL display all available snippets in a paginated or scrollable format
2. WHEN a user enters text in the search field THEN the system SHALL filter snippets based on title, description, or content
3. WHEN a user selects a programming language filter THEN the system SHALL show only snippets for that language
4. WHEN a user selects tag filters THEN the system SHALL show only snippets that match the selected tags
5. WHEN multiple filters are applied THEN the system SHALL show snippets that match all selected criteria
6. WHEN no snippets match the filters THEN the system SHALL display an appropriate "no results" message

### Requirement 3

**User Story:** As a developer, I want to view detailed information about a code snippet, so that I can understand the code, see ratings, and easily copy it for use.

#### Acceptance Criteria

1. WHEN a user clicks on a snippet THEN the system SHALL navigate to a detailed snippet page
2. WHEN the snippet detail page loads THEN the system SHALL display the full code with proper syntax highlighting
3. WHEN viewing a snippet detail THEN the system SHALL show the snippet title, description, author, creation date, and programming language
4. WHEN viewing a snippet detail THEN the system SHALL provide a copy button to copy the code to clipboard
5. WHEN a user clicks the copy button THEN the system SHALL copy the code and show a confirmation message
6. WHEN the snippet detail page loads THEN the system SHALL display any ratings or reviews for the snippet
7. IF the user is authenticated AND is not the snippet author THEN the system SHALL allow the user to rate the snippet

### Requirement 4

**User Story:** As a developer, I want to upload and share my own code snippets, so that I can contribute to the community and help other developers.

#### Acceptance Criteria

1. WHEN an authenticated user accesses the upload page THEN the system SHALL display a form to submit new snippets
2. WHEN submitting a snippet THEN the system SHALL require title, description, programming language, and code content
3. WHEN submitting a snippet THEN the system SHALL allow optional tags to be added
4. WHEN the form is submitted with valid data THEN the system SHALL save the snippet and associate it with the current user
5. WHEN the snippet is successfully saved THEN the system SHALL redirect to the snippet detail page or show a success message
6. WHEN form validation fails THEN the system SHALL display appropriate error messages for each field
7. IF a user is not authenticated THEN the system SHALL redirect them to login before accessing the upload page

### Requirement 5

**User Story:** As a developer, I want to view my profile and manage my snippets, so that I can track my contributions and see my activity on the platform.

#### Acceptance Criteria

1. WHEN an authenticated user accesses their profile THEN the system SHALL display their username, email, and join date
2. WHEN viewing a user profile THEN the system SHALL show all snippets created by that user
3. WHEN viewing own profile THEN the system SHALL allow editing or deleting of own snippets
4. WHEN viewing another user's profile THEN the system SHALL show their public snippets and any reviews they've left
5. WHEN a user deletes their own snippet THEN the system SHALL remove it from the database and update the UI
6. IF a user is not authenticated THEN the system SHALL redirect them to login before accessing profile pages

### Requirement 6

**User Story:** As a developer, I want to create an account and log in securely, so that I can upload snippets and manage my profile.

#### Acceptance Criteria

1. WHEN a user accesses the registration page THEN the system SHALL provide a form with email and password fields
2. WHEN a user submits valid registration data THEN the system SHALL create an account using Supabase authentication
3. WHEN registration is successful THEN the system SHALL redirect to the main application or show a confirmation message
4. WHEN a user accesses the login page THEN the system SHALL provide email and password authentication fields
5. WHEN a user submits valid login credentials THEN the system SHALL authenticate using Supabase and establish a session
6. WHEN login is successful THEN the system SHALL redirect to the intended page or dashboard
7. WHEN authentication fails THEN the system SHALL display appropriate error messages
8. WHEN a user is logged in THEN the system SHALL show logout option and user-specific navigation
9. WHEN a user logs out THEN the system SHALL clear the session and redirect to the landing page