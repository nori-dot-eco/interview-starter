# Before you begin

Fork this repository, clone it to your machine, and run `yarn install` (or `npm install`). 

# The Problem

Our application matches orders for carbon removal with available supply to determine which carbon removals are used for an order.

To facilitate this order matching, we want to design an algorithm that, given an order and a list of available carbon removals, will give you a list of carbon removals to be used for that order.

Our list of available supply is an array that looks something like this:

|id    |project_name      |quantity|location|year|
|------|------------------|--------|--------|----|
|abc123|Tea Time Farm     |1.0     |WA      |2020|
|efg456|Tea Time Farm     |2.5     |WA      |2021|
|hij789|Oppenlander Supply|3.0     |ID      |2021|
|klm012|Yee Produce       |4.25    |CA      |2019|
|nop345|Yee Produce       |0.75    |CA      |2020|
|qrs678|Yee Produce       |2.0     |CA      |2021|

Use the following function to implement a matching algorithm that returns a list of carbon removals that can be used to fulfill the order.

```typescript
export const allocateRemovalsToOrder = async ({
  orderQuantity,
}: {
  orderQuantity: number;
}): any => {}
```

To get started, you can use the starter code in `lib/allocateRemovalsToOrder.ts` and the test located at `test/allocateRemovalsToOrder.test.ts`. You can then run your tests using `yarn test`, which will automatically rerun your tests as you make changes to your code.

### Extension 1

Our customers wish to filter carbon removals based on their location or year of removal. Extend your algorithm with this behavior using the following filters parameter.

```typescript
export const allocateRemovalsToOrder = async ({
  orderQuantity,
  filters,
}: {
  orderQuantity: number;
  filters?: {
    years?: number[];
    locations?: string[];
  };
}): any => {}
```

### Extension 2

We want to keep track of which carbon removals have been allocated so we don't assign the same carbon removal to multiple orders. Extend your algorithm so that allocations of carbon removals are tracked across multiple runs.
