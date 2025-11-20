# MinAI - Zero Dependency OpenAI Client for Java

A lightweight, zero-dependency Java client for OpenAI's Chat Completion API that uses only the JDK.

## Why Zero Dependencies?

### 1. **Minimal Attack Surface**

Every external dependency is a potential security vulnerability:
- **No transitive dependencies** means no hidden CVEs in libraries you didn't even know you were using
- **Fewer attack vectors** - you only trust the JDK, which is already required and vetted
- **Easier security audits** - review ~500 lines of code instead of thousands across multiple libraries
- **No supply chain risks** - no risk of compromised packages from Maven Central or malicious maintainers

### 2. **Dependency Hell Avoidance**

Zero dependencies means:
- **No version conflicts** - never clash with Jackson, OkHttp, or other libraries your application uses
- **No transitive dependency explosions** - a typical "lightweight" HTTP client can pull in 10+ transitive dependencies
- **No breaking changes** from library updates you don't control
- **Perfect for libraries** - if you're building a library/framework, you won't force dependency choices on your users

### 3. **Startup Performance**

- **Faster classloading** - no scanning/loading of external JARs
- **Smaller classpath** - relevant for containerized applications and serverless functions
- **Reduced JVM warmup time** - fewer classes to JIT compile
- **Lower memory footprint** - no overhead from unused library features

### 4. **Deployment Simplicity**

- **Single JAR deployment** - your compiled code is all you need (plus the JDK)
- **Smaller Docker images** - every MB matters in container environments
- **Faster CI/CD pipelines** - no dependency resolution or downloading
- **No dependency conflicts in shaded JARs** - perfect for plugins, agents, or embedded scenarios

### 5. **Long-Term Maintainability**

- **No forced upgrades** - libraries deprecate features, change APIs, or go unmaintained
- **Code you control** - fix bugs or add features without waiting for upstream maintainers
- **Stable over years** - JDK HTTP client (`java.net.http`) is part of the platform and won't disappear
- **Educational value** - understand exactly how HTTP and JSON work instead of relying on "magic"

### 6. **Regulatory & Compliance**
- **Fewer attack vectors** - you only trust the JDK, which is already required and vetted
For some environments:
- **License compliance is simpler** - only your code + JDK license, no Apache/MIT/BSD license tracking
- **Easier SBOM (Software Bill of Materials) generation** - fewer components to document
- **Meets "no third-party code" requirements** in certain government/enterprise settings
Zero dependencies means:
## When Should You Use This?

✅ **Good fit for:**
- Microservices where you only need basic OpenAI chat completions
- AWS Lambda / serverless functions (cold start optimization)
- Embedded applications, plugins, or agents
- Educational projects or learning how APIs work
- Security-sensitive environments with strict dependency policies
- Libraries that don't want to impose dependencies on users

❌ **Not recommended for:**
- Complex use cases needing streaming, function calling, vision, embeddings, etc.
- Applications already heavily using Jackson/OkHttp (no benefit to avoiding them)
- Teams unfamiliar with manual JSON handling (higher bug risk)
- Rapid prototyping where developer velocity matters more than dependencies

## What's Included

- ✅ OpenAI Chat Completions API support
- ✅ System and user messages
- ✅ Configurable temperature
- ✅ Manual JSON serialization (no Jackson)
- ✅ Java 11+ HttpClient (no OkHttp)
- ✅ Error handling and status code validation
- ✅ Support for any OpenAI-compatible API (OpenAI, Azure, local proxies)

## What's NOT Included

- ❌ Streaming responses
- ❌ Function calling / tools
- ❌ Vision (image inputs)
- ❌ Embeddings API
- ❌ Audio/TTS/Whisper
- ❌ Assistants API
- ❌ Robust JSON parsing (uses simple string operations)
- ❌ Retry logic with exponential backoff
- ❌ Request/response logging frameworks
- **Smaller classpath** - relevant for containerized applications and serverless functions
- **Reduced JVM warmup time** - fewer classes to JIT compile
- **Lower memory footprint** - no overhead from unused library features

### 4. **Deployment Simplicity**

- **Single JAR deployment** - your compiled code is all you need (plus the JDK)
- **Smaller Docker images** - every MB matters in container environments
- **Faster CI/CD pipelines** - no dependency resolution or downloading
- **No dependency conflicts in shaded JARs** - perfect for plugins, agents, or embedded scenarios

### 5. **Long-Term Maintainability**

- **No forced upgrades** - libraries deprecate features, change APIs, or go unmaintained
- **Code you control** - fix bugs or add features without waiting for upstream maintainers
- **Stable over years** - JDK HTTP client (`java.net.http`) is part of the platform and won't disappear
- **Educational value** - understand exactly how HTTP and JSON work instead of relying on "magic"

### 6. **Regulatory & Compliance**
- **Fewer attack vectors** - you only trust the JDK, which is already required and vetted
For some environments:
- **License compliance is simpler** - only your code + JDK license, no Apache/MIT/BSD license tracking
- **Easier SBOM (Software Bill of Materials) generation** - fewer components to document
- **Meets "no third-party code" requirements** in certain government/enterprise settings
Zero dependencies means:
## When Should You Use This?

✅ **Good fit for:**
- Microservices where you only need basic OpenAI chat completions
- AWS Lambda / serverless functions (cold start optimization)
- Embedded applications, plugins, or agents
- Educational projects or learning how APIs work
- Security-sensitive environments with strict dependency policies
- Libraries that don't want to impose dependencies on users

❌ **Not recommended for:**
- Complex use cases needing streaming, function calling, vision, embeddings, etc.
- Applications already heavily using Jackson/OkHttp (no benefit to avoiding them)
- Teams unfamiliar with manual JSON handling (higher bug risk)
- Rapid prototyping where developer velocity matters more than dependencies

## What's Included

- ✅ OpenAI Chat Completions API support
- ✅ System and user messages
- ✅ Configurable temperature
- ✅ Manual JSON serialization (no Jackson)
- ✅ Java 11+ HttpClient (no OkHttp)
- ✅ Error handling and status code validation
- ✅ Support for any OpenAI-compatible API (OpenAI, Azure, local proxies)

## What's NOT Included

- ❌ Streaming responses
- ❌ Function calling / tools
- ❌ Vision (image inputs)
- ❌ Embeddings API
- ❌ Audio/TTS/Whisper
- ❌ Assistants API
- ❌ Robust JSON parsing (uses simple string operations)
- ❌ Retry logic with exponential backoff
- ❌ Request/response logging frameworks
- **Smaller classpath** - relevant for containerized applications and serverless functions
- **Reduced JVM warmup time** - fewer classes to JIT compile
- **Lower memory footprint** - no overhead from unused library features

### 4. **Deployment Simplicity**

- **Single JAR deployment** - your compiled code is all you need (plus the JDK)
- **Smaller Docker images** - every MB matters in container environments
- **Faster CI/CD pipelines** - no dependency resolution or downloading
- **No dependency conflicts in shaded JARs** - perfect for plugins, agents, or embedded scenarios

### 5. **Long-Term Maintainability**

- **No forced upgrades** - libraries deprecate features, change APIs, or go unmaintained
- **Code you control** - fix bugs or add features without waiting for upstream maintainers
- **Stable over years** - JDK HTTP client (`java.net.http`) is part of the platform and won't disappear
- **Educational value** - understand exactly how HTTP and JSON work instead of relying on "magic"

### 6. **Regulatory & Compliance**
- **Fewer attack vectors** - you only trust the JDK, which is already required and vetted
For some environments:
- **License compliance is simpler** - only your code + JDK license, no Apache/MIT/BSD license tracking
- **Easier SBOM (Software Bill of Materials) generation** - fewer components to document
- **Meets "no third-party code" requirements** in certain government/enterprise settings
Zero dependencies means:
## When Should You Use This?

✅ **Good fit for:**
- Microservices where you only need basic OpenAI chat completions
- AWS Lambda / serverless functions (cold start optimization)
- Embedded applications, plugins, or agents
- Educational projects or learning how APIs work
- Security-sensitive environments with strict dependency policies
- Libraries that don't want to impose dependencies on users

❌ **Not recommended for:**
- Complex use cases needing streaming, function calling, vision, embeddings, etc.
- Applications already heavily using Jackson/OkHttp (no benefit to avoiding them)
- Teams unfamiliar with manual JSON handling (higher bug risk)
- Rapid prototyping where developer velocity matters more than dependencies

## What's Included

- ✅ OpenAI Chat Completions API support
- ✅ System and user messages
- ✅ Configurable temperature
- ✅ Manual JSON serialization (no Jackson)
- ✅ Java 11+ HttpClient (no OkHttp)
- ✅ Error handling and status code validation
- ✅ Support for any OpenAI-compatible API (OpenAI, Azure, local proxies)

## What's NOT Included

- ❌ Streaming responses
- ❌ Function calling / tools
- ❌ Vision (image inputs)
- ❌ Embeddings API
- ❌ Audio/TTS/Whisper
- ❌ Assistants API
- ❌ Robust JSON parsing (uses simple string operations)
- ❌ Retry logic with exponential backoff
- ❌ Request/response logging frameworks
- **Smaller classpath** - relevant for containerized applications and serverless functions
- **Reduced JVM warmup time** - fewer classes to JIT compile
- **Lower memory footprint** - no overhead from unused library features

### 4. **Deployment Simplicity**

- **Single JAR deployment** - your compiled code is all you need (plus the JDK)
- **Smaller Docker images** - every MB matters in container environments
- **Faster CI/CD pipelines** - no dependency resolution or downloading
- **No dependency conflicts in shaded JARs** - perfect for plugins, agents, or embedded scenarios

### 5. **Long-Term Maintainability**

- **No forced upgrades** - libraries deprecate features, change APIs, or go unmaintained
- **Code you control** - fix bugs or add features without waiting for upstream maintainers
- **Stable over years** - JDK HTTP client (`java.net.http`) is part of the platform and won't disappear
- **Educational value** - understand exactly how HTTP and JSON work instead of relying on "magic"

### 6. **Regulatory & Compliance**

For some environments:
- **License compliance is simpler** - only your code + JDK license, no Apache/MIT/BSD license tracking
- **Easier SBOM (Software Bill of Materials) generation** - fewer components to document
- **Meets "no third-party code" requirements** in certain government/enterprise settings

## When Should You Use This?

✅ **Good fit for:**
- Microservices where you only need basic OpenAI chat completions
- AWS Lambda / serverless functions (cold start optimization)
- Embedded applications, plugins, or agents
- Educational projects or learning how APIs work
- Security-sensitive environments with strict dependency policies
- Libraries that don't want to impose dependencies on users

❌ **Not recommended for:**
- Complex use cases needing streaming, function calling, vision, embeddings, etc.
- Applications already heavily using Jackson/OkHttp (no benefit to avoiding them)
- Teams unfamiliar with manual JSON handling (higher bug risk)
- Rapid prototyping where developer velocity matters more than dependencies

## What's Included

- ✅ OpenAI Chat Completions API support
- ✅ System and user messages
- ✅ Configurable temperature
- ✅ Manual JSON serialization (no Jackson)
- ✅ Java 11+ HttpClient (no OkHttp)
- ✅ Error handling and status code validation
- ✅ Support for any OpenAI-compatible API (OpenAI, Azure, local proxies)

## What's NOT Included

- ❌ Streaming responses
- ❌ Function calling / tools
- ❌ Vision (image inputs)
- ❌ Embeddings API
- ❌ Audio/TTS/Whisper
- ❌ Assistants API
- ❌ Robust JSON parsing (uses simple string operations)
- ❌ Retry logic with exponential backoff
- ❌ Request/response logging frameworks

## Quick Start

### 1. Build

```bash
mvn clean package
```

### 2. Usage

```java
### Using Azure OpenAI
```java
**Why not use the official SDK?** Full-featured but pulls 15-30 dependencies. Use that for production apps needing all features; use this for minimal footprint.

**Is manual JSON parsing safe?** Yes, for the known OpenAI response format. Not a general JSON parser—don't use for arbitrary JSON.
String apiKey = "demo"; // or any placeholder
**Production-ready?** Yes, for simple chat completions. Not for streaming, function calling, vision, etc.
```
**What if OpenAI changes their API?** You own the code—update it yourself. No waiting for library maintainers.
## Contributing

This project intentionally has no dependencies. Pull requests that add dependencies will be rejected.
- **[OpenAI Java SDK](https://github.com/openai/openai-java)** - Official, full-featured
- **[LangChain4j](https://github.com/langchain4j/langchain4j)** - LLM framework
- **[Simple OpenAI](https://github.com/sashirestela/simple-openai)** - Middle ground
Acceptable contributions:
## License
- Better documentation
Public domain. Do whatever you want with it.

## FAQ

**Built with ❤️ and zero dependencies.** • Java 11+ required • ~500 lines of code
A: The official SDK is excellent and feature-complete, but it pulls in many dependencies. Use it if you need full API coverage. Use this if you need minimal dependencies.

**Q: Is manual JSON parsing safe?**  
A: For the specific OpenAI response format, yes. This isn't a general JSON parser—it's tailored to the known structure. Don't use this approach for arbitrary JSON.

**Q: What about streaming responses?**  
A: Not supported. Streaming requires SSE parsing which adds complexity. Use a full SDK if you need streaming.

**Q: Performance compared to Jackson?**  
A: For small payloads (typical chat completions), the difference is negligible (~1-2ms). Jackson wins for very large/complex JSON.

**Q: Can I use this in production?**  
A: Yes, if your use case fits (simple chat completions, no streaming, no function calling). Many production systems value simplicity over features.

**Q: What if OpenAI changes their API?**  
A: You own the code—update it yourself. This is actually an advantage: you're not waiting for a library maintainer to release a patch.

## Alternatives

If this doesn't fit your needs, consider:

- **[OpenAI Java SDK](https://github.com/openai/openai-java)** - Official, full-featured, well-maintained
- **[LangChain4j](https://github.com/langchain4j/langchain4j)** - Powerful framework for LLM apps
- **[Simple OpenAI](https://github.com/sashirestela/simple-openai)** - Good middle ground with fewer deps

## Support

This is a minimal educational/utility project. There's no official support, but:
- Open an issue for bugs
- Read the code (it's short!)
- Fork it and customize for your needs

---

**Built with ❤️ and zero dependencies.**

