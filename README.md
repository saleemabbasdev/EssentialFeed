# Essential Feed — iOS Architecture Practice

An iOS learning project focused on test-driven development, modular boundaries, networking, caching behavior, and memory management.

> **Attribution:** This repository contains exercises created while studying the Essential Developer program. It demonstrates my implementation and learning progress and is not presented as an independently originated product or as official Essential Developer material.

## Learning objectives

- Build features through test-driven development
- Separate domain logic from infrastructure details
- Apply dependency inversion through small protocols
- Map transport and HTTP failures into domain-facing errors
- Verify behavior with spies and deterministic unit tests
- Detect memory leaks during tests
- Explore local feed caching behavior

## Current implementation

- `FeedLoader` abstraction
- `RemoteFeedLoader` use case
- `HTTPClient` abstraction
- `URLSessionHTTPClient` production adapter
- HTTP response and JSON mapping
- Feed domain model
- Remote-loader tests covering requests, failures, JSON mapping, deallocation, and memory leaks
- Early cache use-case exploration

## Architecture

```text
Feed domain
    ↑
RemoteFeedLoader
    ↓
HTTPClient protocol
    ↓
URLSessionHTTPClient
```

The domain-facing loader does not depend directly on `URLSession`. Infrastructure is injected through `HTTPClient`, making the core behavior independently testable.

## Requirements

- Xcode 15 or newer
- An iOS simulator supported by the project

## Running the project

1. Clone the repository.
2. Open `EssentialFeed.xcodeproj`.
3. Select an iOS simulator.
4. Build the `EssentialFeed` scheme.

## Running tests

Use the shared `CI` or `EssentialFeedTests` scheme and run **Product → Test**, or press `⌘U`.

## Repository status

This is a learning repository rather than a production application. The remote-feed path has meaningful test coverage, while the cache implementation is incomplete.

## Author

**Saleem Abbas** — Senior iOS & Mobile Engineer

- [Website](https://abbasdigital.de/)
- [LinkedIn](https://www.linkedin.com/in/saleemabbas/)
