# Golang Interview Preparation Notes

## Target Position

Golang Developer – Remote

---

# Main Goal

Tujuan interview pertama bukan terlihat paling pintar.

Tujuan utama:

- terlihat sebagai real software engineer
- bisa komunikasi dasar
- bisa menjelaskan pengalaman
- jujur soal kemampuan
- menunjukkan willingness to learn

Jangan mencoba menjadi “perfect senior architect”.

---

# Materi Belajar Interview Golang

## 1. Goroutine

### Apa itu goroutine?

Goroutine adalah lightweight thread yang dikelola oleh Go runtime.

Digunakan untuk menjalankan task secara concurrent.

### Keunggulan

- ringan
- cepat
- cocok untuk backend service
- bagus untuk handling banyak request

### Contoh

```go
func printMessage() {
    fmt.Println("Hello")
}

func main() {
    go printMessage()

    time.Sleep(time.Second)
}
```

### Penjelasan

- keyword `go` membuat function berjalan sebagai goroutine
- task berjalan secara concurrent

### Kapan digunakan?

Biasanya untuk:

- background processing
- asynchronous task
- multiple API request
- queue processing
- notification system

### Jawaban interview

```text
A goroutine is a lightweight thread managed by the Go runtime.

It allows multiple tasks to run concurrently with low overhead.
```

---

## 2. Channel

### Apa itu channel?

Channel digunakan untuk komunikasi antar goroutine.

Channel membantu mengirim data dengan aman.

### Contoh

```go
func main() {
    ch := make(chan string)

    go func() {
        ch <- "hello"
    }()

    msg := <-ch

    fmt.Println(msg)
}
```

### Penjelasan

- `ch <-` mengirim data
- `<- ch` menerima data

### Fungsi channel

- sinkronisasi
- komunikasi antar goroutine
- menghindari race condition

### Jawaban interview

```text
Channels are used for communication between goroutines.

They help safely pass data between concurrent processes.
```

---

## 3. Concurrency vs Parallelism

### Concurrency

Beberapa task berjalan secara independent.

Tidak harus benar-benar berjalan bersamaan.

### Parallelism

Beberapa task benar-benar berjalan di waktu yang sama menggunakan multiple CPU core.

### Jawaban interview

```text
Concurrency means multiple tasks can progress independently.

Parallelism means multiple tasks are actually running at the same time using multiple CPU cores.
```

---

## 4. Struct dan Interface

### Struct

Struct digunakan untuk membuat custom data type.

### Contoh

```go
type User struct {
    Name string
    Email string
}
```

### Interface

Interface mendefinisikan behavior.

### Contoh

```go
type Animal interface {
    Speak()
}
```

### Kenapa interface penting?

- loose coupling
- flexible architecture
- memudahkan testing

---

## 5. Pointer

### Apa itu pointer?

Pointer menyimpan alamat memory.

Digunakan agar function bisa mengubah data asli.

### Contoh

```go
func updateName(name *string) {
    *name = "Jehan"
}
```

### Kenapa digunakan?

- lebih efisien
- menghindari copy data besar
- bisa modify original value

---

## 6. REST API

### Apa itu REST API?

REST API adalah cara komunikasi antar sistem menggunakan HTTP.

### Method umum

- GET → ambil data
- POST → tambah data
- PUT → update data
- DELETE → hapus data

### Contoh endpoint

```text
GET /api/products
POST /api/login
```

### Hal yang biasa dikerjakan backend

- request validation
- authentication
- database query
- JSON response
- business logic

### Jawaban interview

```text
I have experience creating REST APIs, handling authentication, request validation, database interaction, and JSON responses.
```

---

## 7. JSON Handling di Go

### Contoh

```go
type User struct {
    Name string `json:"name"`
}
```

### Convert struct ke JSON

```go
json.Marshal(user)
```

### Convert JSON ke struct

```go
json.Unmarshal(data, &user)
```

---

## 8. Error Handling

### Konsep Go

Go menggunakan explicit error handling.

### Contoh

```go
result, err := service.GetUser()

if err != nil {
    return err
}
```

### Kenapa bagus?

- jelas
- predictable
- mudah debugging

---

## 9. Database MySQL

### Hal yang perlu dipahami

- table
- primary key
- foreign key
- relation
- indexing
- CRUD

### CRUD

- Create
- Read
- Update
- Delete

### Contoh query

```sql
SELECT * FROM users;
```

```sql
INSERT INTO users(name) VALUES('Jehan');
```

### Jawaban interview

```text
I mainly have experience with MySQL, including database design, CRUD operations, and query optimization.
```

---

## 10. Authentication

### Konsep dasar

User login → server validasi → generate token/session.

### Biasanya

- JWT
- session
- bearer token

### Yang penting dipahami

- login
- logout
- authorization
- middleware

---

## 11. Middleware

### Apa itu middleware?

Middleware adalah code yang berjalan sebelum request masuk ke endpoint.

### Biasanya digunakan untuk

- authentication
- logging
- validation
- security

---

## 12. Microservices

### Apa itu microservices?

Sistem dipecah menjadi service-service kecil.

### Contoh

- auth service
- payment service
- product service

### Keuntungan

- scalable
- mudah maintenance
- independent deployment

### Kekurangan

- lebih kompleks
- communication antar service lebih sulit

### Jawaban interview

```text
I have experience building modular backend services and API integrations.
```

---

## 13. Git dan CI/CD

### Git

Digunakan untuk version control.

### Command penting

```bash
git pull
git push
git commit
```

### CI/CD

CI/CD adalah automation untuk:

- build
- testing
- deployment

### Tujuan

- faster deployment
- reduce human error
- maintain code quality

### Jawaban interview

```text
I understand the general CI/CD workflow including automated build, testing, and deployment.
```

---

## 14. Docker

### Apa itu Docker?

Docker digunakan untuk menjalankan aplikasi di container.

### Keuntungan

- environment konsisten
- mudah deployment
- portable

### Konsep penting

- image
- container
- Dockerfile

---

## 15. Agile dan Scrum

### Agile

Metode development iterative.

### Fokus

- collaboration
- fast feedback
- continuous improvement

### Scrum

Biasanya ada:

- sprint
- daily standup
- backlog
- retrospective

### Jawaban interview

```text
I have experience working in collaborative development environments and Agile workflows.
```

---

# Focus Belajar Sebelum Interview

## 1. Golang Fundamentals

Pelajari kembali:

- goroutine
- channel
- interface
- pointer
- struct
- package
- error handling
- REST API
- JSON handling
- concurrency vs parallelism
- basic Go project structure

### Yang harus bisa dijelaskan

- apa itu goroutine
- apa itu channel
- kenapa Go bagus untuk backend
- bagaimana membuat REST API sederhana

---

## 2. Backend Engineering

### Refresh

- CRUD flow
- authentication
- middleware
- REST API
- webhook
- database query
- API integration

### Yang harus bisa dijelaskan

- alur backend project
- bagaimana frontend dan backend berkomunikasi
- bagaimana API bekerja

---

## 3. Database

### Fokus

- MySQL
- relasi tabel
- query dasar
- indexing basic
- optimization basic

### Yang harus bisa dijelaskan

- pengalaman menggunakan database
- membuat table dan relasi
- CRUD operation

---

## 4. Laravel / PHP

Karena requirement mereka juga kuat di PHP.

### Refresh

- routing
- controller
- model
- migration
- authentication
- API
- middleware

---

## 5. DevOps Basic

Tidak perlu expert.

### Minimal paham

- Git workflow
- deployment process
- CI/CD basic concept
- Docker basic concept
- cloud basic concept

### Yang penting

Paham konsep umum.

---

# Pertanyaan Interview dan Jawaban

## 1. Tell me about yourself

```text
My name is Jehan Afwazi Ahmad, and I am a software developer from Indonesia.

I have experience in backend and web application development, especially using Golang, PHP, and Laravel.

I have worked on business systems, APIs, and database-related applications.

I enjoy solving technical problems and continuously learning new technologies.
```

---

## 2. Tell me about your Golang experience

```text
I have around five years of experience working with Golang, mainly for backend and API development.

I have used Golang to build REST APIs, handle database operations, authentication, and business logic.

Recently, I have not been using Golang as actively as before because I have been focusing on other development projects, but I still understand the core concepts.
```

---

## 3. What do you like about Golang?

```text
What I like about Golang is its simplicity and performance.

The language is clean, easy to maintain, and very good for backend systems and concurrent processing.
```

---

## 4. What is a goroutine?

```text
A goroutine is a lightweight thread managed by the Go runtime.

It allows multiple tasks to run concurrently with low overhead.
```

---

## 5. What are channels in Go?

```text
Channels are used for communication between goroutines.

They help safely pass data between concurrent processes.
```

---

## 6. Difference between concurrency and parallelism?

```text
Concurrency means multiple tasks can progress independently.

Parallelism means multiple tasks are actually running at the same time using multiple CPU cores.
```

---

## 7. Have you worked with REST APIs?

```text
Yes, most of my backend work involves REST APIs.

I have experience creating endpoints, request validation, authentication, database interaction, and JSON responses.
```

---

## 8. What database have you used?

```text
I mainly have experience with MySQL.

I have worked on database design, CRUD operations, reporting systems, and query optimization.
```

---

## 9. Have you worked with microservices?

```text
I have experience separating backend functionality into independent services and APIs.

Most of my experience is in modular backend architecture and service integration.
```

---

## 10. Experience with DevOps / CI-CD?

```text
I have experience using Git for version control and basic deployment workflows.

I understand the general CI/CD process such as automated build, testing, and deployment pipelines.
```

---

## 11. Kalau lupa jawaban

```text
I have worked with it before, but I would need a quick refresh because it has been some time since I used it actively.
```

atau

```text
I understand the basic concept, but I have not used it deeply in production.
```

---

## 12. Kalau tidak dengar pertanyaan

```text
Sorry, could you repeat the question?
```

```text
Sorry, the audio is not very clear.
```

```text
Let me think for a moment.
```

---

# Strategi Saat Interview

## Yang HARUS dilakukan

- bicara pelan
- gunakan kalimat pendek
- jawab sederhana
- jujur
- tenang
- fokus ke pengalaman nyata

---

## Yang JANGAN dilakukan

- pura-pura expert
- overclaim
- menjawab terlalu panjang
- panik ketika lupa
- mencoba grammar sempurna

---

# Mindset Penting

Interview ini bukan ujian hidup mati.

Tujuan utama:

- mencoba
- belajar
- mendapatkan pengalaman interview internasional
- melatih komunikasi teknis

Bahkan kalau gagal pun:

- kamu dapat pengalaman besar
- tahu gap skill market
- lebih siap untuk kesempatan berikutnya
