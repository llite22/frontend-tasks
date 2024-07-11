# TechAuditBI_FE_Test

## task_1
The ChildComponent is memoized in order to prevent unnecessary re-rendering.
But now this memoization doesn't work. 
1. Explain why memoization doesn't work.
2. Fix the code so that the ChildComponent does not re-render every time MainComponent re-renders.

```
import { Fragment, memo } from 'react';

const MainComponent = () => {
	const makeLog = () => console.log('hi from MainComponent');

	return (
		<Fragment>
			<ChildComponent makeLog={makeLog} />
		</Fragment>
	);
};

// memoized component
const ChildComponent = memo(({ makeLog }) => (
	<button onClick={makeLog}>say Hi from ChildComponent</button>
));
```

## task_2
Rewrite this part of code using class-based components.

```
const FunctionalCounter = ({ count }) => {
	// do smth...

	useEffect(() => {
		// This code runs when `count` changes.
		console.log(`Count has changed to: ${count}`);
	}, [count]);  // Dependency array includes `count`, so effect runs on count change.

	return (
		<div>Count: {count}</div>
	);
};
```

## task_3
Transform an array of nested arrays into a structured array of objects.
The input data is an array of nested arrays. Each sub-array contains key-value pairs in the format `[key, value]`.
Convert the data into an array of objects where each object has a label property formatted as "Name, Age" and a value property holding the ID.
The answer should be a function: 
```typescript
const transformData: TransformDataFunction = (data) => { .... }
```
#### Example Input
```typescript
const inputData: UserArray[] = [
    [["id", 1], ["name", "Ivan"], ["age", 23]],
    [["id", 2], ["name", "Maria"], ["age", 30]],
    [["id", 3], ["name", "Anna"], ["age", 28]],
];
```
#### Example Output
```typescript
const inputData: TransformedData[] = [
   	{ label: "Ivan, 23", value: 1 },
    { label: "Marina, 30", value: 2 },
    { label: "Anna, 28", value: 3 },
];
```

## task_4
Define TypeScript types from the previous task.
Use union of tuples to define UserData type.
```typescript
type UserData = ...
type UserArray = UserData[];

type TransformedData = {
	...
};

type TransformDataFunction = ...
```

