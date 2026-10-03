# 🔗 URL Shortener

A simple **URL Shortener API** built using **Node.js, Express.js, and MongoDB**.

This project converts long URLs into short URLs and redirects users to the original URL when they access the generated short URL. It also records the visit history of shortened URLs.

## 🚀 Features

- Create shortened URLs
- Store URL information in MongoDB
- Redirect short URLs to their original URLs
- Track URL visit history
- Store visit timestamps
- REST API based backend
- MongoDB integration using Mongoose

## 🛠️ Tech Stack

- **Node.js** – JavaScript runtime
- **Express.js** – Backend web framework
- **MongoDB** – Database
- **Mongoose** – MongoDB ODM
- **JavaScript** – Programming language
- **Nodemon** – Development server

## 📂 Project Structure

```text
SHORT_URL/
│
├── index.js
├── connect.js
├── package.json
├── package-lock.json
│
├── models/
│   └── url.js
│
└── routes/
    └── url.js
```

## ⚙️ How It Works

The basic flow of the application is:

```text
User
  ↓
Send URL
  ↓
Express.js API
  ↓
Generate Short ID
  ↓
Store URL in MongoDB
  ↓
Return Short URL
  ↓
User opens Short URL
  ↓
Find URL in MongoDB
  ↓
Record Visit History
  ↓
Redirect to Original URL
```

## 🗄️ Database

The project uses a local MongoDB database:

```text
mongodb://localhost:27017/short-url
```

The application connects to MongoDB using Mongoose.

URL information includes data such as:

- Short ID
- Original/redirect URL
- Visit history
- Visit timestamps

## 📦 Installation

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

### 2. Go to the project directory

```bash
cd SHORT_URL
```

### 3. Install dependencies

```bash
npm install
```

### 4. Make sure MongoDB is running

The project currently uses:

```text
mongodb://localhost:27017/short-url
```

So MongoDB should be running locally on your computer.

### 5. Start the server

Using npm:

```bash
npm start
```

The project uses Nodemon, so the server can automatically restart when you make changes.

You can also run:

```bash
node index.js
```

## 🌐 Server

The application runs on:

```text
http://localhost:8001
```

## 🔀 URL Redirection

When a user opens a shortened URL such as:

```text
http://localhost:8001/abc123
```

the server uses the `shortId` to find the corresponding URL in MongoDB.

It then records the visit time and redirects the user to the original URL.

## 📊 Visit History

The application records when a shortened URL is accessed.

For each visit, a timestamp is added to the URL's `visitHistory`.

Example concept:

```json
{
  "timestamp": "Visit time"
}
```

This can later be used to build URL analytics such as:

- Number of visits
- Visit timestamps
- Most visited URLs

## 📡 API

The URL routes are mounted under:

```text
/url
```

The main Express application also provides a redirection route:

```text
GET /:shortId
```

For example:

```text
GET /abc123
```

The server searches for `abc123` and redirects the user to the stored original URL.

> The exact URL creation endpoint and request body depend on the implementation in `routes/url.js`.

## 📚 What I Learned

While building this project, I practiced:

- Node.js fundamentals
- Express.js
- REST APIs
- HTTP requests and responses
- MongoDB
- Mongoose
- Database operations
- URL redirection
- Middleware
- Route handling
- Working with asynchronous JavaScript
- Tracking user visits

## 🔮 Future Improvements

Some features that can be added in the future:

- User authentication
- Custom short URLs
- URL expiration
- Click analytics
- QR code generation
- Dashboard for URL statistics
- Rate limiting
- Input validation
- Deployment to a cloud platform

## 👨‍💻 Author

**Mohammad Aman**

B.Tech CSE Student  
Interested in Backend Development, Web Development and Software Engineering.

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.

---

**Built with ❤️ while learning Node.js and Backend Development.**
