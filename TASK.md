# Frontend Live Coding Task: Product Search Page

## Overview

You will build a small product search page in React using a public API.

- **Total session:** 45 minutes
- **Coding time:** 30 minutes
- **Code walkthrough and questions:** 10 minutes

The task has 4 levels. Nobody is expected to finish everything in 30 minutes. Complete the levels in order and focus on working, readable code over speed.

## Rules

- Share your entire screen for the whole session.
- You can use Google, MDN, and the React docs.
- AI tools (ChatGPT, Copilot, Claude, etc.) are **not allowed**. Please keep all AI extensions in your editor turned off.
- Think out loud while you work. We care about how you approach problems as much as the final result.
- Ask questions any time if something is unclear.

## Setup

Use the starter project. Make sure `npm run dev` is running and the app opens at `http://localhost:5173`.

You may install small libraries if you need them, but plain React is enough for every level.

## API

Base URL: `https://dummyjson.com`

No API key or authentication is required.

| Purpose              | Endpoint                         |
| -------------------- | -------------------------------- |
| Get all products     | `GET /products`                  |
| Search products      | `GET /products/search?q=phone`   |
| Get all categories   | `GET /products/categories`       |
| Products by category | `GET /products/category/{slug}`  |
| Pagination           | `GET /products?limit=10&skip=10` |

`/products` returns 30 products by default. The response looks like this:

```json
{
  "products": [
    {
      "id": 1,
      "title": "...",
      "price": 9.99,
      "thumbnail": "https://...",
      "category": "beauty"
    }
  ],
  "total": 194,
  "skip": 0,
  "limit": 30
}
```

`/products/categories` returns a list of objects like `{ "slug": "beauty", "name": "Beauty", "url": "..." }`. Use `slug` in the category endpoint.

## Tasks

### Level 1: Product List

- Fetch products from `/products`.
- Show each product as a card with its image (`thumbnail`), title, and price.
- Show a loading state while data is being fetched.
- Show an error message if the request fails.

### Level 2: Search

- Add a search input above the product list.
- When the user types, fetch results from `/products/search?q=...` and update the list.
- Avoid sending a request on every single keystroke (for example, wait 300ms after the user stops typing).

### Level 3: Category Filter

- Add a category dropdown populated from `/products/categories`.
- Selecting a category shows only products from that category.
- Search and category filter should work together without breaking each other.
- Note: the API cannot search inside a category in a single request. Decide how you will combine them and be ready to explain your choice.

### Level 4: Pagination or Sorting

Pick **one**:

- **Pagination:** Show 10 products per page with Previous and Next buttons, using `limit` and `skip`.
- **Sorting:** Add a dropdown to sort products by price (low to high, high to low).

### Bonus

- Responsive layout that works on mobile screens.
- A clear empty state when no products match (for example, "No products found").

## After Coding

In the last 10 minutes, you will:

1. Walk us through your code and explain your decisions.
2. Answer a few follow-up questions about your implementation.
3. Ask us anything about the role or the team.

Good luck!
