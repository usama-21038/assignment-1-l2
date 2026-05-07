## Why any is called a “Type Safety Hole”
The any type completely disables TypeScript’s type checking. Once a variable is declared as any, you can perform any operation on it—even unsafe ones—without errors.

That’s why any is called a type safety hole: it allows you to “escape” TypeScript’s safety system.
Problem with any
code:
let data: any = "Hello";
data.toFixed(2); // No compile error, but runtime crash possible

## Why unknown is the safer choice
The unknown type is a safer alternative to any. It still accepts any value, but prevents you from using it until you confirm its type.

Safe behavior of unknown
code:
let data: unknown = "Hello";

// data.toUpperCase();// Error: must check type first

if (typeof data === "string") {
  console.log(data.toUpperCase()); //Safe
}

## What is Type Narrowing?
Type narrowing is the process of refining a broad type into a more specific type using conditions.
It helps TypeScript understand exactly what type a variable is at a certain point in the code.