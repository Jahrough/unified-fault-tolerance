# unified-fault-tolerance

A lightweight fault-tolerance library for Node.js and TypeScript.

## Features
- Retry with backoff
- Timeout
- Circuit breaker
- Fallback logic

## Usage

```ts
import { faultTolerant } from 'unified-fault-tolerance';

const safeCall = faultTolerant(() => fetchData(), {
  retry: { attempts: 3, delay: 'exp-jitter' },
  timeout: { ms: 1000 },
  fallback: () => 'Fallback!',
});
