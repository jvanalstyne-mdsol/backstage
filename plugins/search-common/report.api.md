## API Report File for "@backstage/plugin-search-common"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts
/// <reference types="node" />

import { JsonObject } from '@backstage/types';
import { Permission } from '@backstage/plugin-permission-common';
import { Readable } from 'stream';
import { Transform } from 'stream';
import { Writable } from 'stream';

// @public
export interface DocumentCollatorFactory {
  getCollator(): Promise<Readable>;
  readonly type: string;
  readonly visibilityPermission?: Permission;
}

// @public
export interface DocumentDecoratorFactory {
  getDecorator(): Promise<Transform>;
  readonly types?: string[];
}

// @public
export type DocumentTypeInfo = {
  visibilityPermission?: Permission;
};

// @public
export type IndexableDocument = SearchDocument & {
  authorization?: {
    resourceRef: string;
  };
};

// @public (undocumented)
export type IndexableResult = Result<IndexableDocument>;

// @public (undocumented)
export type IndexableResultSet = ResultSet<IndexableDocument>;

// @public @deprecated
export type QueryRequestOptions = {
  token?: string;
};

// @public @deprecated
export type QueryTranslator = (query: SearchQuery) => unknown;

// @public (undocumented)
export interface Result<TDocument extends SearchDocument> {
  document: TDocument;
  highlight?: ResultHighlight;
  rank?: number;
  type: string;
}

// @public
export interface ResultHighlight {
  // (undocumented)
  fields: {
    [field: string]: string;
  };
  postTag: string;
  preTag: string;
}

// @public (undocumented)
export interface ResultSet<TDocument extends SearchDocument> {
  // (undocumented)
  nextPageCursor?: string;
  // (undocumented)
  numberOfResults?: number;
  // (undocumented)
  previousPageCursor?: string;
  // (undocumented)
  results: Result<TDocument>[];
}

// @public
export interface SearchDocument {
  location: string;
  text: string;
  title: string;
}

// @public @deprecated
export interface SearchEngine {
  getIndexer(type: string): Promise<Writable>;
  query(
    query: SearchQuery,
    options?: QueryRequestOptions,
  ): Promise<IndexableResultSet>;
  setTranslator(translator: QueryTranslator): void;
}

// @public (undocumented)
export interface SearchQuery {
  // (undocumented)
  filters?: JsonObject;
  // (undocumented)
  pageCursor?: string;
  // (undocumented)
  pageLimit?: number;
  // (undocumented)
  term: string;
  // (undocumented)
  types?: string[];
}

// @public (undocumented)
export type SearchResult = Result<SearchDocument>;

// @public (undocumented)
export type SearchResultSet = ResultSet<SearchDocument>;

// Warnings were encountered during analysis:
//
// src/types.d.ts:8:1 - (ae-undocumented) Missing documentation for "SearchQuery".
// src/types.d.ts:9:5 - (ae-undocumented) Missing documentation for "term".
// src/types.d.ts:10:5 - (ae-undocumented) Missing documentation for "types".
// src/types.d.ts:11:5 - (ae-undocumented) Missing documentation for "filters".
// src/types.d.ts:12:5 - (ae-undocumented) Missing documentation for "pageLimit".
// src/types.d.ts:13:5 - (ae-undocumented) Missing documentation for "pageCursor".
// src/types.d.ts:30:5 - (ae-undocumented) Missing documentation for "fields".
// src/types.d.ts:41:1 - (ae-undocumented) Missing documentation for "Result".
// src/types.d.ts:64:1 - (ae-undocumented) Missing documentation for "ResultSet".
// src/types.d.ts:65:5 - (ae-undocumented) Missing documentation for "results".
// src/types.d.ts:66:5 - (ae-undocumented) Missing documentation for "nextPageCursor".
// src/types.d.ts:67:5 - (ae-undocumented) Missing documentation for "previousPageCursor".
// src/types.d.ts:68:5 - (ae-undocumented) Missing documentation for "numberOfResults".
// src/types.d.ts:73:1 - (ae-undocumented) Missing documentation for "SearchResult".
// src/types.d.ts:77:1 - (ae-undocumented) Missing documentation for "SearchResultSet".
// src/types.d.ts:81:1 - (ae-undocumented) Missing documentation for "IndexableResult".
// src/types.d.ts:85:1 - (ae-undocumented) Missing documentation for "IndexableResultSet".
```