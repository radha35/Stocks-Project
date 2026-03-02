# Stocks-Project


# QuantEdge – Real-Time Stock Intelligence Platform

QuantEdge is a full-stack real-time stock tracking and intelligence platform designed to process live market data, generate OHLC candles, and stream low-latency updates to clients.

The system combines a scalable Go-based real-time engine with a modern Next.js frontend to deliver trading insights, alerts, and AI-powered summaries.

<div align="center">
  <br />
 
  <br />

  <div>
    <img src="https://img.shields.io/badge/-Next.js-black?style=for-the-badge&logoColor=white&logo=next.js&color=black"/>
    <img src="https://img.shields.io/badge/-Better Auth-black?style=for-the-badge&logoColor=white&logo=betterauth&color=black"/>
<img src="https://img.shields.io/badge/-Shadcn-black?style=for-the-badge&logoColor=white&logo=shadcnui&color=black"/>
<img src="https://img.shields.io/badge/-Inngest-black?style=for-the-badge&logoColor=white&logo=inngest&color=black"/><br/>

<img src="https://img.shields.io/badge/-MongoDB-black?style=for-the-badge&logoColor=white&logo=mongodb&color=00A35C"/>
<img src="https://img.shields.io/badge/-CodeRabbit-black?style=for-the-badge&logoColor=white&logo=coderabbit&color=9146FF"/>
<img src="https://img.shields.io/badge/-TailwindCSS-black?style=for-the-badge&logoColor=white&logo=tailwindcss&color=38B2AC"/>
<img src="https://img.shields.io/badge/-TypeScript-black?style=for-the-badge&logoColor=white&logo=typescript&color=3178C6"/>

  </div>

  <h3 align="center">Stock Market App — Alerts, Charts, AI Insights</h3>

   
</div>

---

## 🚀 Features

- 🔐 Secure JWT-based authentication  
- 📈 Real-time stock trade ingestion via WebSockets  
- 🕒 1-minute OHLC candle aggregation  
- 🗄 Persistent candle storage in PostgreSQL  
- 📡 Low-latency live broadcasting using pub-sub architecture  
- ⭐ Personalized watchlists  
- 🔔 Automated price alerts  
- 🤖 AI-generated daily market summaries  
- 📊 Historical data retrieval via REST APIs  

---

## 🏗 System Architecture

```
Finnhub WebSocket API
        ↓
Go Backend Service
        ↓
Trade Processing Engine
        ↓
In-Memory 1-Minute OHLC Aggregation
        ↓
PostgreSQL (Closed Candle Storage)
        ↓
WebSocket Pub-Sub Broadcasting
        ↓
Next.js Frontend Clients
```

---

## 🧠 Architecture Overview

### 1️⃣ Real-Time Trade Ingestion

- Connects to Finnhub WebSocket API  
- Receives live trade events  
- Processes high-frequency market data streams  

### 2️⃣ In-Memory OHLC Aggregation

- Aggregates trade events into 1-minute OHLC candles  
- Maintains the current open candle in memory  
- On candle close:
  - Persists to PostgreSQL
  - Broadcasts to connected clients  

### 3️⃣ Persistent Storage

- PostgreSQL used for structured financial time-series data  
- Indexed by symbol + timestamp  
- Ensures strong consistency and reliable historical retrieval  

### 4️⃣ Live Broadcasting (Pub-Sub Model)

- WebSocket server maintains active client connections  
- Clients subscribe to stock symbols  
- Closed and live candles are pushed in real-time  

### 5️⃣ REST APIs

- Fetch historical OHLC data  
- Retrieve user watchlists  
- Manage alerts  
- Authentication endpoints  

---

## 🗄 Database Design

### MongoDB
Used for:
- User authentication data  
- Watchlists  
- Alert configurations  
- AI-generated summaries  

Chosen for flexible schema and rapid iteration.

### PostgreSQL
Used for:
- OHLC candle storage  
- Time-series financial data  
- Aggregations and indexed queries  

Chosen for strong ACID guarantees and structured querying.

This approach follows **polyglot persistence**, selecting databases based on workload characteristics.

---

## ⚙️ Tech Stack

### Backend (Real-Time Engine)
- Go (Golang)
- Gorilla WebSocket
- PostgreSQL
- GORM
- REST APIs
- Pub-Sub architecture

### Backend (Application Services)
- Node.js
- MongoDB
- JWT Authentication
- Inngest (event workflows)
- Nodemailer

### Frontend
- Next.js
- TypeScript

### External Integrations
- Finnhub API (Live market data)
- Gemini API (AI market summaries)

---

## 🔥 Key Engineering Concepts Implemented

- WebSocket-based real-time data streaming  
- In-memory event aggregation  
- Time-based window processing (1-minute candles)  
- Concurrency handling using goroutines  
- Stateless REST architecture  
- Event-driven alert processing  
- Low-latency client broadcasting  
- Database indexing strategy for time-series queries  

---

## 📈 Future Improvements

- Horizontal WebSocket scaling with Redis  
- Time-series optimization using TimescaleDB  
- Distributed pub-sub messaging  
- Kubernetes deployment  
- Load balancing for high concurrency  

---

## 🎯 Why This Project Matters

QuantEdge demonstrates:

- Real-time market data processing  
- Financial time-series engineering  
- Go concurrency management  
- Low-latency WebSocket broadcasting  
- Multi-database architecture  
- Full-stack system ownership  

It reflects production-style trading infrastructure principles.
