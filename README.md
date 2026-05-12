# Spring Boot MVC Project

## Description

This project is a simple Java Spring Boot MVC web application.

The application:

* accepts parameters from the URL,
* displays personalized greeting messages,
* renders HTML pages using Thymeleaf,
* displays a static image on the webpage.

The project was created using:

* Java
* Spring Boot
* Spring MVC
* Thymeleaf
* Maven

---

# Technologies Used

* Java
* Spring Boot
* Spring MVC
* Thymeleaf
* Maven
* IntelliJ IDEA

---

# Project Structure

```text id="k3m8w1"
src
 └── main
     ├── java
     │    └── pl.edu.vistula.firstprojectjavaspring
     │          └── controller
     │                └── HelloController.java
     │
     └── resources
          ├── templates
          │      └── greeting.html
          │
          └── static
                └── images
                      └── vistula.png
```

---

# How the Application Works

The application uses the MVC (Model View Controller) architecture.

## Controller

The controller handles incoming HTTP requests.

File:

```text id="h6p4v9"
HelloController.java
```

Example controller method:

```java id="x8f1y3"
@GetMapping("/greeting")
public String greeting(
        @RequestParam(name = "name", required = false, defaultValue = "World")
        String name,
        Model model) {

    model.addAttribute("name", name);

    return "greeting";
}
```

### Explanation

* `@GetMapping("/greeting")`

  * handles HTTP GET requests for `/greeting`

* `@RequestParam`

  * reads the `name` parameter from the URL

* `model.addAttribute("name", name)`

  * sends the value to the HTML template

* `return "greeting"`

  * opens the `greeting.html` page

---

# HTML Template

File:

```text id="t2g7n4"
greeting.html
```

The HTML page:

* displays greeting text,
* displays the user name,
* displays an image.

Example:

```html id="q1d9r5"
<h1 th:text="'Hello, ' + ${name} + '!'"></h1>

<img src="/images/vistula.png">
```

---

# HTTP Methods

## GET Request

Example:

```text id="p4z7m1"
http://localhost:8080/greeting?name=Vistula
```

The application reads the `name` parameter from the URL and displays a personalized greeting page.

---

# Use Cases

## Use Case 1 — Personalized Greeting Page

### HTTP Method
GET

### URL

http://localhost:8080/greeting?name=Vistula

### Description
The application reads the `name` parameter from the URL and displays a personalized greeting page using Thymeleaf templates.

The page also displays:
- additional MVC text,
- a static Vistula image loaded from the resources directory.

### Result

- Hello, Vistula!
- This is my first Spring Boot MVC page.
- Vistula image/logo is displayed.

---

## Use Case 2 — Display Static Image

### HTTP Method

GET

### URL

```text id="n5v3k1"
http://localhost:8080/images/vistula.png
```

### Description

The application loads and displays a static image from the `resources/static/images` directory.

### Result

The Vistula image/logo is displayed on the webpage.

---

# How to Run the Project

1. Open the project in IntelliJ IDEA
2. Run:

```text id="b2h8m4"
FirstProjectJavaSpringApplication
```

3. Open browser:

```text id="f1t6q9"
http://localhost:8080/greeting?name=Vistula
```

---

# Screenshots

## Browser Result

<img width="440" height="525" alt="Screenshot 2026-05-12 at 22 45 31" src="https://github.com/user-attachments/assets/9e803869-36d0-4376-8129-27a3d38ec3cf" />



## IntelliJ Project Structure

<img width="460" height="868" alt="Screenshot 2026-05-12 at 22 49 17" src="https://github.com/user-attachments/assets/daf1edb0-f32c-4c94-b96b-53704f71b4f3" />

## Controller Code

<img width="460" height="868" alt="Screenshot 2026-05-12 at 22 49 17" src="https://github.com/user-attachments/assets/daf1edb0-f32c-4c94-b96b-53704f71b4f3" />

## Static Image Result

<img width="1259" height="868" alt="Screenshot 2026-05-12 at 23 02 51" src="https://github.com/user-attachments/assets/b2fd4e8a-6653-473d-8a97-401330afef12" />


---

# GitHub Repository

Repository link:

```text id="w8n2d5"
https://github.com/rib-2006/first-project-java-spring
```

---

# .gitignore

The project contains a `.gitignore` file to prevent unnecessary files from being uploaded to the repository.

Ignored files include:

* `.idea`
* `target`
* system files
* temporary files

---

# Author

RibRib phukan
























