# CODETECH IT SOLUTIONS — INTERNSHIP SOFTWARE DEVELOPMENT ARTIFACTS

Welcome to my project repository for the **CODETECH IT SOLUTIONS** Java Software Development Internship. This repository serves as a professional portfolio containing the complete implementation of four assigned development tasks. 

Each module emphasizes clean code structure, thorough error handling, and foundational software engineering principles.

---

## 🛠️ Repository Architecture & Module Index

The project files are structured cleanly as independent executable modules within the root directory:
├── README.md                  # Comprehensive portfolio documentation
├── FileHandlingUtility.java   # Task 1: Persistent storage utility
├── RestAPIClient.java         # Task 2: REST network API client
├── ChatServer.java            # Task 3: TCP server routing node
├── ChatClient.java            # Task 3: TCP client communication endpoint
└── RecommendationSystem.java  # Task 4: Content decision-matrix engine

## 💻 Technical Architecture Breakdowns

### 1. Persistent File Handling Utility (`FileHandlingUtility.java`)
* **Core Function:** Implements a state-persistent console utility capable of safely executing sequential write, read, and continuous append operations on the local file system.
* **Underlying Logic:** * Instantiates a `java.io.FileWriter` stream without an active append flag to open a write-buffer, outputting raw structural records cleanly.
  * Uses a tokenized parsing engine (`java.util.Scanner`) targeting a local file descriptor to dynamically capture line breaks and stream data directly to the command line interface.
  * Configures trailing-byte updates using `new FileWriter(fileName, true)` to append fresh records without risking data truncation or erasing historical file records.
* **Resilience:** Wrapped inside non-nested `try-catch` structures catching low-level `IOException` states to guarantee system protection against runtime disruptions like directory access restrictions.

---

### 2. Remote REST API Connector (`RestAPIClient.java`)
* **Core Function:** Establishes an outbound network layer engineered to pull, ingest, and process structured web payloads asynchronously using native HTTP protocols.
* **Underlying Logic:**
  * Builds a rigid network target loop utilizing `java.net.URL` directed toward the public GitHub user API endpoint.
  * Opens an active `HttpURLConnection` gateway explicitly configured to process network requests using the standard `GET` protocol verb.
  * Evaluates server response states dynamically via integer status code checks (`connection.getResponseCode()`). Upon verifying a successful state (`200 OK`), it initializes a combined `InputStreamReader` and `BufferedReader` sequence.
* **Optimization:** Leverages an internal `StringBuilder` to collect incoming stream character segments, preventing string pool memory fragmentation before executing a mandatory `.disconnect()` to release the socket back to the operating system.

---

### 3. Distributed Network Chat Application (`ChatServer.java` & `ChatClient.java`)
* **Core Function:** A two-way, full-duplex terminal communication system operating over persistent TCP/IP network sockets.
* **Underlying Logic:**
  * **The Server Component (`ChatServer`):** Allocates a dedicated communication port over `5000` via a standard `ServerSocket`. It invokes a blocking `.accept()` execution loop, pausing active execution until an external socket connection is authenticated.
  * **The Client Component (`ChatClient`):** Launches a connection route target directing traffic toward the host system's loopback interface address (`localhost`) on matching port variables.
  * **Streaming Architecture:** Once linked, both programs instantiate reciprocal streaming pipes. Incoming message characters are intercepted using `BufferedReader`, while outbound communication text is flushed instantly across the wire using auto-flushing `PrintWriter` blocks.
* **Workflow Loop:** Uses an alternating messaging layout where a received socket string prints directly to the console terminal, prompting an operator to input a response via standard console streams (`System.in`).

---

### 4. Interactive Recommendation Engine (`RecommendationSystem.java`)
* **Core Function:** A fast console decision-matrix utility configured to instantly map user input selections to specific categorized data matrices.
* **Underlying Logic:**
  * Maps an array structure containing pre-defined data titles inside an immutable memory structure.
  * Deploys an interactive console interface using a terminal tracking `java.util.Scanner` block to capture precise numeric menu selections.
  * References an optimized `switch-case` mapping structure that executes choices at a constant time complexity of $O(1)$, completing tasks instantly without nesting heavy conditions.
* **System Boundaries:** Features a fallback `default:` routing block that catches out-of-bounds user selections to ensure the console interface handles mistakes gracefully without throwing a runtime exception.

---

## 🚀 Execution & Compilation Guidelines

Ensure you have the Java Development Kit (JDK 8 or higher) installed and configured in your system path environment.

### 📥 1. Global Compilation
Compile all source modules simultaneously by opening your terminal in the project directory and running:
```bash
javac FileHandlingUtility.java RestAPIClient.java ChatServer.java ChatClient.java RecommendationSystem.java



