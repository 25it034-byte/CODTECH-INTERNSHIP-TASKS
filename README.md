# CODETECH Internship Tasks

This repository contains the Java implementation files for the assigned internship tasks.

## Project Structure

1. **Task 1: File Handling Utility** (`FileHandlingUtility.java`)
   - Demonstrates writing, reading, and appending data cleanly to text files using Java I/O streams (`FileWriter`, `Scanner`, `File`).

2. **Task 2: REST API Client** (`RestAPIClient.java`)
   - Uses native `HttpURLConnection` to fetch raw data asynchronously over HTTP (GET request) from the GitHub API and logs JSON responses.

3. **Task 3: Client-Server Chat Application** (`ChatServer.java` & `ChatClient.java`)
   - A two-way interactive command-line socket chat utility running over port `5000` via TCP networking streams (`ServerSocket`, `Socket`).

4. **Task 4: Movie Recommendation System** (`RecommendationSystem.java`)
   - An interactive console-driven app parsing structured matrices/switch structures to recommend similar curated titles based on numeric inputs.

## Setup Instructions
Compile any program locally using your terminal:
```bash
javac ClassName.java
java ClassName
```
*Note: For the Chat application, run `ChatServer` first, then launch `ChatClient` in a separate terminal terminal window.*
