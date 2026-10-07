# 📄 01 - Persistent File I/O and Contact Management Engine

**Domain:** Java & Backend Engineering  
**Tech Stack:** Java 17, File I/O (`BufferedReader` / `BufferedWriter`), Array Data Structures  

---

## 📌 Context & Business Problem
Describe briefly why this code was written. 
*Example:* Standard console applications often lose data after execution. This implementation introduces local text file persistence to save and load contact records reliably without external database dependencies.

---

## 🛠️ Key Technical Features
- **File Persistence:** Methods to write user data sequentially into text files and load them back at startup.
- **Dynamic Search & Parsing:** String processing logic to search entries by name or attribute.
- **Defensive Error Handling:** Standardized `try-catch` blocks to prevent `IOException` or `NullPointerException` crashes.

---

## 💻 Code Highlight & Refactoring

```java
// Example method demonstrating file reading logic
public List<String> readRecords(String filePath) {
    List<String> records = new ArrayList<>();
    try (BufferedReader reader = new BufferedReader(new FileReader(filePath))) {
        String line;
        while ((line = reader.readLine()) != null) {
            records.add(line);
        }
    } catch (IOException e) {
        System.err.println("Error reading file: " + e.getMessage());
    }
    return records;
}
