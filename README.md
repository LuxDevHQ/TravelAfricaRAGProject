### **Student Instructions: Travel Africa RAG Project**

![Uploading image.png…](https://github.com/LuxDevHQ/TravelAfricaRAGProject/blob/main/Travel%20Africa.png)

You are required to build a **Travel Africa RAG Assistant** that helps users discover hotels, explore destinations, and plan trips across **Kenya and East Africa**.

You have already learned **FastAPI** and how to build a **RAG system**. In this project, you will combine those skills by collecting hotel data, processing it, storing it in a vector database, and building a user interface based on the provided **Travel Africa RAG Template**.

---

### **Project Title**

**Travel Africa: Kenya Hotel Discovery and Trip Planning RAG Assistant**

---

### **Project Objective**

The goal of this project is to build a complete **RAG-powered travel assistant** that can answer user questions about hotels, destinations, safari trips, coastal vacations, and travel planning in Kenya and East Africa.

The assistant should help users answer questions such as:

```text
Find affordable hotels in Diani near the beach.

Recommend hotels in Nairobi for business travelers.

Plan a 6-day Kenya trip covering safari, coast, and culture.

Which hotels are good for families near Maasai Mara?

Compare hotels in Mombasa and Diani for a weekend trip.
```

---

### **Project Scenario**

You are building a smart travel assistant for tourists, local travelers, and travel agencies.

The system should allow users to search for hotels and ask travel-related questions. Your assistant should use the data you collected and return useful answers with hotel recommendations and sources.

---

### **Data Collection Requirements**

You are required to scrape or collect hotel data from public sources.

Your data should focus on hotels in Kenya and, where possible, East Africa.

Examples of locations to include:

```text
Nairobi
Mombasa
Diani
Naivasha
Nakuru
Maasai Mara
Amboseli
Watamu
Malindi
Kisumu
Nanyuki
Lamu
Zanzibar
Arusha
Kampala
Dar es Salaam
```

Each hotel record should contain as many of the following fields as possible:

```text
Hotel Name
Location
County or Region
Country
Hotel Description
Price Range
Amenities
Room Types
Rating
Review Summary
Nearby Attractions
Hotel Category
Contact Information
Website URL
Image URL
Source URL
```

---

### **Minimum Dataset Requirement**

Your dataset should contain:

```text
Minimum: 50 hotels
Recommended: 100+ hotels
Advanced: 200+ hotels
```

You may store your scraped data in:

```text
CSV
JSON
SQLite
PostgreSQL
MongoDB
```

---

### **Data Cleaning Requirements**

Before building the RAG system, clean your dataset.

You should handle:

```text
Missing hotel names
Duplicate hotel records
Invalid or missing prices
Inconsistent location names
Missing descriptions
Empty amenities
Incorrect ratings
Unstructured text
```

Your final dataset should be clean, structured, and ready for embedding.

---

### **Ethical Scraping Guidelines**

When collecting hotel data, make sure you follow responsible and ethical scraping practices.

You should:

```text
Use publicly available data only
Respect robots.txt where applicable
Avoid aggressive scraping
Add delays between requests
Store the source URL for every record
Avoid collecting private or sensitive information
Clean and validate the scraped data
```

Where scraping is difficult, you may manually collect data from public sources and organize it into a structured dataset.

---

### **RAG System Requirements**

Your RAG pipeline should follow this process:

```text
1. Scrape or collect hotel data.
2. Clean and structure the dataset.
3. Convert each hotel record into meaningful text.
4. Split the text into chunks where necessary.
5. Generate embeddings.
6. Store the embeddings in a vector database.
7. Allow the user to ask a question.
8. Retrieve relevant hotel records from the vector database.
9. Send the retrieved context to the LLM.
10. Return an answer with sources.
```

---

### **Backend Requirements**

Your backend should be built using **FastAPI**.

The backend should include endpoints such as:

```text
GET /
Health check endpoint

POST /scrape
Scrape hotel data from selected sources

POST /upload-data
Upload hotel data from CSV or JSON

POST /create-embeddings
Generate embeddings from hotel records

POST /ask
Ask travel-related questions

GET /hotels
Return all available hotels

GET /hotels/{location}
Return hotels from a specific location

POST /plan-trip
Generate a travel itinerary based on user preferences
```

Example `/ask` request:

```json
{
  "question": "Recommend affordable hotels in Diani for a couple."
}
```

Example response:

```json
{
  "answer": "Here are some affordable hotels in Diani that may be suitable for a couple...",
  "sources": [
    {
      "hotel_name": "Example Hotel",
      "location": "Diani",
      "source_url": "https://example.com"
    }
  ]
}
```

---

### **Frontend UI Requirements**

You are required to build your frontend using the provided **Travel Africa RAG Template**.

Your UI should be inspired by the attached design.

The interface should include:

```text
Travel Africa logo or title
Large hero section
Headline
Subtitle
Prompt input box
Quick action buttons
Travel destination visuals
Currency selector
Language selector
Hotel recommendation cards
Source links
Loading state
```

Suggested hero headline:

```text
Hey explorer,
where are we going today?
```

Suggested subtitle:

```text
Discover Kenya & East Africa with hotel recommendations, live travel insights, and expert trip planning.
```

Suggested prompt placeholder:

```text
6 days in Kenya: safari, coast, culture
```

Suggested quick action buttons:

```text
Create a new trip
Explore Kenya
Find hotels
Plan a safari
East Africa escapes
Compare destinations
```

---

### **Instruction to Run the Template**

# Travel Africa RAG Template

A starter front-end template for a **Travel Africa RAG class project**.

The repository currently contains a static **HTML5/CSS3 landing page** that students can connect to their own retrieval-augmented generation backend.

---

## Folder Structure

```text
TravelAfricaRAGProject/
├── README.md
├── static/
│   └── css/
│       └── styles.css
└── templates/
    └── index.html
```

---

## Run Locally

From the repository root, start a simple static server:

```bash
python3 -m http.server 8000
```

Then open the link below in your browser:

```text
http://localhost:8000/templates/
```

---

### **Connecting the Template to Your FastAPI Backend**

After confirming that the template runs locally, connect the frontend input box to your FastAPI `/ask` endpoint.

Example frontend request:

```javascript
const response = await fetch("http://localhost:8000/ask", {
  method: "POST",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify({
    question: userQuestion
  })
});

const data = await response.json();
```

The answer returned from the backend should be displayed on the frontend.

You should also display the sources used by the RAG system.

---

### **Recommended Technology Stack**

#### **Backend**

```text
Python
FastAPI
Uvicorn
Pandas
BeautifulSoup
Requests
LangChain or LlamaIndex
ChromaDB or FAISS
OpenAI API or local embedding model
```

#### **Frontend**

```text
HTML
CSS
JavaScript
React or Next.js, optional
Tailwind CSS, optional
```

#### **Database**

```text
CSV or JSON for beginner version
SQLite or PostgreSQL for advanced version
Vector database: ChromaDB, FAISS, Qdrant, or Pinecone
```

---

### **Minimum Project Deliverables**

Each group should submit:

```text
1. GitHub repository
2. Scraping script
3. Cleaned hotel dataset
4. FastAPI backend
5. RAG pipeline
6. Vector database setup
7. Frontend UI based on the Travel Africa template
8. README.md file
9. Screenshots of the working system
10. Short demo video or live presentation
```

---

### **README.md Requirements**

Your README file should include:

```text
Project title
Project description
Problem statement
Data sources used
How the data was scraped
How the data was cleaned
RAG architecture
Tech stack used
How to run the backend
How to run the frontend template
API endpoints
Screenshots
Challenges faced
Future improvements
```

---

### **Evaluation Criteria**

| Area | Marks |
|---|---:|
| Data scraping and data quality | 20 |
| Data cleaning and structuring | 15 |
| RAG implementation | 25 |
| FastAPI backend | 15 |
| UI implementation using the template | 15 |
| Documentation and presentation | 10 |
| **Total** | **100** |

---

### **Final Submission Instruction**

Your final project should demonstrate a working **Travel Africa RAG Assistant**.

The user should be able to ask travel-related questions through the frontend, the backend should retrieve relevant hotel data, and the system should generate useful answers based on the retrieved context.

Your UI must use the provided **Travel Africa RAG Template** as the starting point.
