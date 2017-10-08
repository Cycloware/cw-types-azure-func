# Installation
 
> First, run `npm install --save @cw-types/ambient-types`


>Then, you must add `node_modules/@cw-types` to your `tsconifg.json` file, like so:
```javascript
    "typeRoots": [
      "node_modules/@cw-types",
      "node_modules/@types"
    ]
```
> This will enable the Typescript compiler to find and use this typing since it is not installed under `node_modules/@types`.

> Please note the order is important of the entries in `typeRoots`.  If you want `node_modules/@types` to resolve first then move it up top. 

# Summary

> Typings library for common ambient (global) types.


> Here are some examples:

```typescript
// All primitive types
type TPrimitive = boolean | number | string | symbol;

type TNullOrUndefined = null | undefined;

type TPrimitiveAll = TPrimitive | TNullOrUndefined;

type TNotVoid = object | TPrimitiveAll;

type ReadonlyRecurse<T> = {readonly [P in keyof T]: ReadonlyRecurse<T>; }
type PartialRecurse<T> = {[P in keyof T]?: PartialRecurse<T[P]>; }

/**
 * Cycle all properties in T to make them a flat type from
 * a union of many types.
 */
type Cycle<T> = {
  [P in keyof T]: T[P];
};

/**
 * Make all properties in T Required
 */
type Required<T> = {
  [P in keyof T]: T[P];
};

type TEmptyObject = {};


type RecordOf<TObj, TValue> = {[P in keyof TObj]: TValue; };

type TIndexerTo<T> = { [key: string]: T; };
type TIndexerToAny = TIndexerTo<any>;
type TIndexerToString = TIndexerTo<string>;
type TIndexerToBoolean = TIndexerTo<boolean>;
type TIndexerToNumber = TIndexerTo<number>;
type TIndexerToObject = TIndexerTo<object>;

```

# Maintainers
This project is mainted by [Kavan J. Shaban](https://github.com/kavanshaban) at [Cycloware](https://github.com/cycloware) 
