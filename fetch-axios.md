# Decide About Data Fetching

- Status: Proposed
- Deciders: Nariman Adam
- Date: 20 June 2022

## Context and Problem Statement

We were working on a Voucher Management system which has authentication and the users are using old browsers, we need to look for a data fetching techniue to support Old browsers and make it easy for handling authentication

<!-- ## Decision Drivers

- [driver 1, e.g., a force, facing concern, …]
- [driver 2, e.g., a force, facing concern, …] -->

## Considered Options

- Fetch
- Axios

## Decision Outcome

Chosen option: Axios, because we need to create JWT interceptor as we have authentication in our web application, Also our users are still operating on Old browsers so we need to be supported

<!-- ### Positive Consequences

* [e.g., improvement of quality attribute satisfaction, follow-up decisions required, …]
* …

### Negative Consequences

* [e.g., compromising quality attribute, follow-up decisions required, …]
* … -->

## Pros and Cons of the Options

### Fetch

- Good, Already built in no need to install a package
- Good, Simultaneous requests wityh `Promise.all()`
- Bad, because you need to stringify the output from the server by yourself
- Bad, Supporting Chrome 42+, Firefox 39+, Edge 14+, and Safari 10.3+ only
- Bad, Setting Timeout for request with `AbortController` Interface a bit complex
- Bad, Work Around is needed to implement HTTP Interceptors

### Axios

- Good, because It converts data to JSON automatically
- Good, because Wide range of browser support even old browsers because of using `XMLHttpRequest` under the hood
- Good, because setting timeout before the request is aborted with timeout property
- Good, HTTP Interceptors
- Good, Because of handling download progress indicators easily
- Good, Simultaneous requests with `axios.all()`
- Bad, because it is an extra package you add to your project

## Links

- Fetch: https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API
- Axios: https://axios-http.com/
- https://www.measurethat.net/Benchmarks/Show/14128/0/xhr-vs-fetch-vs-axios



