# Pusher Channel Demo in Express.js (TypeScript) and Event Driven approach.

[Pusher](https://pusher.com/) is a cloud-based real-time messaging platform that enables scalable pub/sub communication. It simplifies event broadcasting and live updates without requiring complex infrastructure. Pusher's Channels service allows bidirectional communication between producers and consumers, making it ideal for real-time applications like notifications, chat systems, and live dashboards.

## Messaging Patterns Implemented
This implementation leverages the Publisher-Subscriber (Pub/Sub) Pattern, ensuring scalable and decoupled communication:
- Decoupled Messaging: Publishers send messages without knowing their consumers, fostering modularity.
- Multiple Subscribers: Allows multiple consumers to listen to events, enhancing distribution.
- Asynchronous Processing: Messages are dispatched asynchronously, ensuring non-blocking execution.
- Event-Based Workflow: Events trigger specific actions, optimizing real-time interactions.

## Roles in the System
Pusher handles two primary roles in messaging:

#### Producer
A producer is responsible for emitting events to Pusher Channels:
- Publishes messages/events: Sends structured data to channels for distribution.
- Defines event types: Categorizes different types of events to maintain consistency.
- Controls access: Ensures only authorized events are published.
- Triggers real-time updates: Enables instant notifications or state changes.

#### Consumer
A consumer listens for events from Pusher Channels:
- Subscribes to channels: Listens for relevant events in real time.
- Handles incoming data: Processes messages and executes corresponding logic.
- Updates UI dynamically: Reacts to events for real-time changes in applications.
- Maintains event consistency: Ensures reliable handling and prevents loss of messages.

## Setup
To set up Pusher Channels in your environment:
- Create a Pusher Account: Sign up at [Pusher](https://pusher.com/) and create an application.
- Obtain Configuration Details: After setup, retrieve your App ID, Key, Secret, and Cluster from the Pusher dashboard.

#### Project Setup
- Clone the Repository
```bash
git clone <your-repo-url>
cd <your-project-directory>
``` 
- Setup `util` Service
    - Move into the util solution and create an .env file:
    ```bash
    NODE_ENV=development
    ```
    - Install dependencies:
    ```bash
    npm i
    ```
    - Build the utility package:
    ```bash
    npm run build
    ```
    - Link the package:
    ```bash
    npm link
    ```
- Setup `api` Service
    - Move into the api solution and create an .env file:
    ```bash
    NODE_ENV=development
    PORT=3000

    # Logging
    LOG_FORMAT=dev
    LOG_DIR=logs

    # CORS Config
    ORIGIN=*
    CREDENTIALS=true

    PUSHER_APP_ID=APP_ID
    PUSHER_KEY=KEY
    PUSHER_SECRET=SECRET
    PUSHER_CLUSTER=CLUSTER

    # Rate Limiter
    RATE_LIMITER=1000
    ```
    - Install dependencies:
    ```bash
    npm i
    ```
    - Link the `util` package:
    ```bash
    npm link <utilurl>
    ```
    - Build the Api service:
    ```bash
    npm run build
    ```
    - Run the API in development mode:
    ```bash
    npm run dev
    ```