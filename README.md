# MinAI - Zero Dependency OpenAI Client

Minimal Java client for OpenAI Chat Completions using only the JDK. No external dependencies.

## Why?

**Security:** No hidden CVEs, no supply chain risks, only trust the JDK  
**Simple:** No version conflicts, 15 KB vs 3-5 MB typical clients  
**Fast:** Better cold starts for serverless/containers  
**Control:** You own the code, fix bugs immediately

## Quick Start

```java
OpenAiCaller caller = new OpenAiCaller(
    System.getenv("OPENAI_API_KEY"),
    "gpt-4o-mini",
    "https://api.openai.com/v1"
);

// Get text response
String text = caller.generateCompletion("You are helpful.", "What is 2+2?");

// With custom temperature (0.0=deterministic, 2.0=creative)
String creative = caller.generateCompletion("You are creative.", "Write a haiku.", 1.5);

// Get full JSON (includes usage stats)
String json = caller.getFullResponse("You are helpful.", "Hello!");
```

**Build:** `mvn clean package` (Java 11+ required)

## What's Included

✅ Chat completions, configurable temperature, error handling  
✅ Works with OpenAI, Azure, LM Studio, Ollama (any compatible API)  
❌ No streaming, function calling, vision, embeddings

## Use Cases

- AWS Lambda (cold start ~200ms vs ~800ms with dependencies)
- IntelliJ/IDE plugins (no conflicts)
- Microservices, Docker containers, embedded apps
- Security-sensitive environments

## How It Works

- **HTTP:** Java 11+ `HttpClient` (built-in)
- **JSON:** Manual string building/parsing (~500 lines total)
- **Trade-off:** Less features, but zero dependencies and full control



