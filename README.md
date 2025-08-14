# Actix Minimal API

A minimal **Rust + Actix Web** example showing how to set up and run a basic API with a single route.

## 📦 Prerequisites

Make sure you have:

* [Rust](https://www.rust-lang.org/tools/install) installed
* `cargo` available in your terminal

Check:

```bash
rustc --version
cargo --version
```

## 🚀 Setup

1. **Create a new project**

```bash
cargo new actix-minimal-api
cd actix-minimal-api
```

2. **Add Actix Web to `Cargo.toml`**

```toml
[dependencies]
actix-web = "4"
```

3. **Replace `src/main.rs` with:**

```rust
use actix_web::{get, App, HttpResponse, HttpServer, Responder};

#[get("/")]
async fn hello() -> impl Responder {
    HttpResponse::Ok().body("Hello world!")
}

#[actix_web::main]
async fn main() -> std::io::Result<()> {
    HttpServer::new(|| App::new().service(hello))
        .bind(("127.0.0.1", 8080))?
        .run()
        .await
}
```

## ▶ Running the server

```bash
cargo run
```

Server will start at:

```
http://127.0.0.1:8080/
```

Visit in your browser or run:

```bash
curl http://127.0.0.1:8080/
```

Expected output:

```
Hello world!
```

## 📚 Learn More

* [Actix Web Docs](https://actix.rs/)
* [Rust Book](https://doc.rust-lang.org/book/)
# actix-minimal-api
