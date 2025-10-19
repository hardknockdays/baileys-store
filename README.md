# Baileys Store (Support Baileys v7.0.0-rc.5)

A lightweight and flexible storage implementation for Baileys WhatsApp Web API.

---

## 📚 Table of Contents

* [Installation](#installation)
* [Usage](#usage)

  * [In-Memory Store](#in-memory-store)
  * [Cache Manager Auth State](#cache-manager-auth-state)
* [Disclaimer](#disclaimer)
* [License](#license)

---

A storage implementation for [Baileys](https://github.com/WhiskeySockets/Baileys) - the WebSocket-based WhatsApp Web API library.

![GitHub License](https://img.shields.io/github/license/renpwn/baileys-store)
![npm](https://img.shields.io/npm/v/baileys-store)
![GitHub issues](https://img.shields.io/github/issues/renpwn/baileys-store)

# Installation

```bash
npm install @renpwn/baileys-store baileys
# or
yarn add @renpwn/baileys-store baileys
```

Note: This package requires `baileys` as a peer dependency. Make sure to install it alongside this package.

# Usage

This package provides different storage implementations for Baileys:

1. In-Memory Store
2. Cache Manager Auth State

## In-Memory Store

```typescript
import { makeInMemoryStore } from '@renpwn/baileys-store'

const store = makeInMemoryStore({})
// You can bind the store to your Baileys instance
store.bind(baileysSock)
```

## Cache Manager Auth State

```typescript
import { makeCacheManagerAuthState } from '@renpwn/baileys-store'
import { caching } from 'cache-manager'

// Create a store with cache-manager
const store = await caching('memory')
// or any other cache-manager storage
const authState = await makeCacheManagerAuthState(store, 'session-key')
// Use the auth state in your baileys connection
const sock = makeWASocket({ auth: authState })
```

# Disclaimer

This project is not affiliated, associated, authorized, endorsed by, or in any way officially connected with WhatsApp or any of its subsidiaries or its affiliates. The official WhatsApp website can be found at whatsapp.com. "WhatsApp" as well as related names, marks, emblems and images are registered trademarks of their respective owners.

The maintainers of Baileys do not in any way condone the use of this application in practices that violate the Terms of Service of WhatsApp. The maintainers of this application call upon the personal responsibility of its users to use this application in a fair way, as it is intended to be used. Use at your own discretion. Do not spam people with this. We discourage any stalkerware, bulk or automated messaging usage.

# License

Copyright (c) 2025 Renpwn

Licensed under the MIT License:
Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Thus, the maintainers of the project can't be held liable for any potential misuse of this project.