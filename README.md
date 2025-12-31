# Pastebin Lite

Pastebin Lite is a simple Pastebin-like application that allows users to create text pastes and share them using a link.  
Each paste can optionally expire based on time (TTL) or number of views.

---

## How to run the app locally

1. Clone the repository:
        git clone <your-github-repository-url>
        cd pastebin-lite

2.install dependencies: npm install

3.Create a .env file in the project root:

    PORT=3000
    REDIS_URL=redis://localhost:6379
    BASE_URL=http://localhost:3000

Make sure Redis is running on your system.

4.Start the application:
    npm start


5.Open the app in your browser:

    http://localhost:3000



Persistence layer
=================
1.Redis is used as the persistence layer.

2.All paste data (content, expiry time, and remaining views) is stored in Redis.

3.Redis ensures data is not lost when the server restarts.

4.In production, Upstash Redis is used to support cloud deployment.

Important design decisions
============================

1.The application is built using Node.js and Express for simplicity.

2.Business logic is separated into a service layer to keep routes clean.

3.Redis is used instead of in-memory storage to support persistence and scalability.

4.Each paste supports time-based expiry (TTL) and view-count limits.

5.Paste content is rendered safely to prevent script execution.

6.The project is designed to work correctly in cloud environments.