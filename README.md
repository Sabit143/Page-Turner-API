# 📚 Go Bookstore API

A simple RESTful API for managing a bookstore, built using **Golang**, **Gorilla Mux**, and **GORM** with a **MySQL** database.

## 🚀 Features
- Add new books 📖
- Retrieve all books 📚
- Get book details by ID 🔍
- Update book information ✏️
- Delete a book ❌

---

## 🛠️ Setup Instructions

### **1️⃣ Clone the Repository**
```sh
git clone https://github.com/Sabit143/Page-Turner-API.git
cd Page-Turner-API
```

### **2️⃣ Install Dependencies**
Ensure you have Go installed and set up properly. Then, install the required modules:
```sh
go mod tidy
```

### **3️⃣ Configure Database**
Update the MySQL credentials in `config/config.go`:
```go
func Connect(){
    d, err := gorm.Open("mysql", "your-username:your-password@tcp(localhost:3306)/your-database?charset=utf8&parseTime=True&loc=Local")
    if err != nil{
        panic(err)
    }
    db = d
}
```

### **4️⃣ Run the Application**
```sh
go run main.go
```
The server will start at **http://localhost:9010**.

---

## 🔥 API Endpoints

### **1️⃣ Create a New Book**
- **Method:** `POST`
- **Endpoint:** `/book/`
- **Request Body:**
  ```json
  {
    "name": "The Go Programming Language",
    "author": "Alan A. A. Donovan",
    "publication": "Addison-Wesley"
  }
  ```

### **2️⃣ Get All Books**
- **Method:** `GET`
- **Endpoint:** `/book/`

### **3️⃣ Get a Book by ID**
- **Method:** `GET`
- **Endpoint:** `/book/{bookId}`
- **Example:** `/book/1`

### **4️⃣ Update a Book**
- **Method:** `PUT`
- **Endpoint:** `/book/{bookId}`
- **Request Body:**
  ```json
  {
    "name": "Updated Book Name",
    "author": "Updated Author",
    "publication": "Updated Publication"
  }
  ```

### **5️⃣ Delete a Book**
- **Method:** `DELETE`
- **Endpoint:** `/book/{bookId}`
- **Example:** `/book/1`

---

## 🧪 Testing the API
You can use **Postman** or **cURL** to test the endpoints:

#### **Create a Book**
```sh
curl -X POST http://localhost:9010/book/ -H "Content-Type: application/json" -d '{
  "name": "The Go Programming Language",
  "author": "Alan A. A. Donovan",
  "publication": "Addison-Wesley"
}'
```

#### **Get All Books**
```sh
curl -X GET http://localhost:9010/book/
```

#### **Get a Book by ID**
```sh
curl -X GET http://localhost:9010/book/1
```

#### **Update a Book**
```sh
curl -X PUT http://localhost:9010/book/1 -H "Content-Type: application/json" -d '{
  "name": "Updated Book Name",
  "author": "Updated Author",
  "publication": "Updated Publication"
}'
```

#### **Delete a Book**
```sh
curl -X DELETE http://localhost:9010/book/1
```

---

## 🏗️ Project Structure
```
📂 go-bookstore
│-- 📂 package
│   ├── 📂 config       # Database connection
│   ├── 📂 controllers  # API handlers
│   ├── 📂 models       # Database models
│   ├── 📂 routes       # Routes configuration
│   ├── 📂 utils        # Helper functions
│-- 📜 main.go          # Entry point
```







