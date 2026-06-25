<img width="100%" alt="Nylas" src="https://github.com/user-attachments/assets/137517ae-244d-47a5-8ca7-b12984971fc4" />

# Nylas Java SDK

> ⚠️ **This is the legacy v2 Nylas Kotlin & Java SDK, and is no longer maintained.**
> Nylas API v2 is deprecated. For new projects, use the **[v3 Kotlin & Java SDK](https://github.com/nylas/nylas-java)** —
> start with the [SDK guide](https://developer.nylas.com/docs/v3/sdks/).

This is the GitHub repository for the Nylas Java SDK and this repo is primarily for anyone who wants to make contributions to the SDK or install it from source. If you are looking to use Java to access the Nylas Email, Calendar, or Contacts API you should refer to our official [Java SDK Quickstart Guide](https://developer.nylas.com/docs/v3/sdks/).

The Nylas Communications Platform provides REST APIs for [Email](https://developer.nylas.com/docs/v3/email/), [Calendar](https://developer.nylas.com/docs/v3/calendar/), and [Contacts](https://developer.nylas.com/docs/v3/email/contacts/), and the Java SDK is the quickest way to build your integration using Java.

Here are some resources to help you get started:

- [Nylas SDK Tutorials](https://developer.nylas.com/docs/v3/getting-started/)
- [Get Started with the Nylas Communications Platform](https://developer.nylas.com/docs/v3/getting-started/)
- [Sign up for your Nylas developer account.](https://nylas.com/register)
- [Nylas API Reference](https://developer.nylas.com/docs/api/v3/)

If you have a question about the Nylas Communications Platform, please reach out to support@nylas.com to get help.

# Install
**Note:** The Nylas Java SDK requires Java 8 or above.

**Setup via Gradle**: If you're using Gradle, add the following to your dependencies section of build.gradle:

    implementation("com.nylas.sdk:nylas-java-sdk:1.22.0")

**Setup via Maven**: For projects using Maven, add the following to your POM file:

    <dependency>
      <groupId>com.nylas.sdk</groupId>
      <artifactId>nylas-java-sdk</artifactId>
      <version>1.22.0</version>
    </dependency>
    
**Build from source**: To build from source, clone this repo and build the project with Gradle.

    git clone https://github.com/nylas/nylas-java.git && cd nylas-java
    ./gradlew build

This will create a new jar file in the `build/libs` subdirectory.

See Gradle documentation on [Building Java Libraries](https://guides.gradle.org/building-java-libraries/)
or the [Gradle User Manual](https://docs.gradle.org/current/userguide/userguide.html) for more information.

# Usage

To use this SDK, you first need to [sign up for a free Nylas developer account](https://nylas.com/register).

Then, follow our guide to [setup your first app and get your API access keys](https://developer.nylas.com/docs/v3/getting-started/).

For code examples that demonstrate how to use this SDK, take a look at our [Java SDK Quickstart Guide](https://developer.nylas.com/docs/v3/sdks/).

## Logging

The SDK uses [SLF4J](http://www.slf4j.org) for logging.  Applications using the SDK can
[choose what logging framework to use with it](http://www.slf4j.org/manual.html#projectDep).
Common choices are log4j, logback, java.util.logging. If the application doesn't specify any logging framework,
then SLF4J will emit one warning and then be completely silent.

By default, the HTTP client is configured with the `com.nylas.HttpLoggingInterceptor`
which provides 3 loggers for HTTP requests that only log at DEBUG level.
- `com.nylas.http.Summary` logs one line for each request, containing method, URI, and content size
and one line for each response containing status code, message, content size and duration.
- `com.nylas.http.Headers` logs the request and response HTTP headers (except Authorization value by default).
- `com.nylas.http.Body` logs request and response bodies (first 10kB by default).

Enabling or disabling those loggers is done via the logging framework being used.
For example, if using log4j2 and with an xml configuration file, include this line to enable all three:
`<Logger name="com.nylas" level="DEBUG"/>`

Configuring the logging of the HTTP Authorization header values and the body size limit can be done by using a 
`NylasClient.Builder` with a customized `HttpLoggingInterceptor`

# Contributing

Please refer to [Contributing](Contributing.md) for information about how to make contributions to this project. We welcome questions, bug reports, and pull requests.

# License

This project is licensed under the terms of the MIT license. Please refer to [LICENSE](LICENSE) for the full terms. 
