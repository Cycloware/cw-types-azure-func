# Installation

> First, run `npm install --save @cw-types/azure-func`


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

> Typings library for Azure Function Applications


> Here are some examples:

```typescript
import '@cw-types/azure-func';
import * as moment from 'moment';

export async function run(context: Context<IData>, data: IData): Promise<void> {
export async function run(context: Context<IData>, data: IData): Promise<void> {

    context.log(`starting function '${context.req.method}'=>'${context.req.method}'...`)
    if (data.first && data.last) {
        context.res = {
            status: 200,
            body: { greeting: `Hello ${data.first} ${data.last}!` }
        };
    }
    else {
        context.res = {
            status: 400,
            body: { error: "Please pass first/last properties in the input object" }
        }
    }
    context.done();
}

interface IData {
    first: string;
    last: string;
}

```

# Maintainers
This project is mainted by [Kavan J. Shaban](https://github.com/kavanshaban) at [Cycloware](https://github.com/cycloware)
