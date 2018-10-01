# Coding-guidelines.

This set of guidelines should strive for few rules with high consistency.

## The four pillars of CRUD.

The guidelines will prioritze ease of:

1. **Deleting** code safely when a rewrite is needed.
2. **Updating** code in case of bugs or updated business needs.
3. **Reading** code to understand the application.
4. **Creating** code so it adds features while minimizing the overall complexity.

## File structure.

All code has an upkeep cost. If we optimize for deletion, it means that we encourage a low upkeep of our code, and spend less time updating code with low business value.

A function can be deleted if you know that noone is calling that function. Your challange is to make it easier to track code usage.

Here's a file structure that encourages easy creation of code:

```
/models
-- users-model.ts
-- companies-model.ts
/views
-- users-view.ts
-- companies-view.ts
/controllers
-- users-controller.ts
-- companies-controller.ts
```

It's easy to figure out where to create your code, but harder to know if `users-model.ts` can be deleted safely.

Here's a slightly modified example that's more modular:

```
/users
-- index.ts
-- model.ts
-- view.ts
-- controller.ts
/companies
-- index.ts
-- model.ts
-- view.ts
-- controller.ts
```

Here we have two stand-alone modules; `users` and `companies`.
The entry point for a module is `/index.ts`.
The file starts with a code comment about **why** it exists.
It then imports private submodules, followed by the exports of the public API that says **what** it does.

## Testing.

- Arrange, Act, Assert.
- Mocking vs integration.

## Documentation.

The code need to state **three questions of purpose**, in order of importance:

- **Why** was the code written? A non-programmer should be able to understand the business value.
- **What** does the code do? There should be a clear pipeline that describe what functions data flow through.
- **How** does the code work? It should be simple to **gain** understanding of how the code works.

## Cognitive load.

- Prepare for low cognitive load. 3-6 bits.
- Single purpose functions.
  - Logic vs composition.
- Separate logic from data structure.
- Sharing data / immutable data / function purity.
