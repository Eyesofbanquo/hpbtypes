# Half Price Books Types

This project is meant to provide the types used in the `HPB React Native` mobile application.
These types are based on the `HPB GraphQL` web service.

## Supported Types

### Book

This is a dummy type. Was being used for testing purposes .

```typescript
interface Book {
  id: string;
  name: string;
}
```

### Category

This type represents the category for a given `Product`.

```typescript
interface Category {
  id: number;
  name: string;
}
```

### Product

This type matches to the content that can be sold at `Half Price Books`. So this could be a book, music, art, etc etc.

```typescript
interface Product {
  author: string;
  categories: Category[];
  description: string;
  firstEdition: boolean;
  genre: string;
  hpbUsedPrice: number;
  id: number;
  name: string;
  publicationDate: Date;
  rareFind: boolean;
  signed: boolean;
  slug: string;
  subtitle: string;
  synopsis?: string;
}
```

## Supported Types: Search

### Top Search

This type represents the top search results **after** completing a search. So these objects should be the recommended objects for the current search.

```typescript
interface TopSearch {
  author: string;
  categories: Category[];
  description: string;
  firstEdition: boolean;
  genre: string;
  hpbUsedPrice: number;
  id: number;
  name: string;
  publicationDate: Date;
  rareFind: boolean;
  signed: boolean;
  slug: string;
  subtitle: string;
  synopsis?: string;
}
```

### Live Search

This type represents the objects returned while doing a live search. This is an event heavy interaction with the backend and is intended to constantly hit the server to return live results.

```typescript
interface LiveSearch {
  bucket: string;
  by: string[];
  dedupe: string;
  id: number;
  name: string;
  rareFind: boolean;
  salesRankHpbStore?: string;
  slug: string;
  type: string;
  upc: string;
}
```

### Normal Search

This is the type that represents what's returned after `live search`. Live search is used for quick text results while normal search is what's returned after selecting an option from live search.

```typescript
interface NormalSearch {
  author: string;
  categories: Category[];
  description?: string;
  firstEdition: boolean;
  genre: string;
  hpbUsedPrice?: any;
  id: number;
  name: string;
  publicationDate?: string;
  rareFind: boolean;
  signed: boolean;
  slug: string;
  synopsis: string;
}
```
