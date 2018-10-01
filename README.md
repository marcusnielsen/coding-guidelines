# coding-guidelines

This set of guidelines should strive for few rules with high consistency.

## The four pillars of CRUD

The guidelines should prioritze, in order of importance, ease of:

1. **Deleting** code safely when a rewrite is needed.
2. **Updating** code in case of bugs or updated business needs.
3. **Reading** code to understand the application.
4. **Creating** code so it adds features while minimizing the overall complexity.

Now, let's look at these in more detail in CRUD-order.

TODO: Don't split things up based on CRUD. The subchapters overlap too much. Go straight to the current subchapters instead.

### Creating code

TODO:

- Modularized folders and files.
- Testing.
  - Arrange, Act, Assert.
  - Mocking vs integration.

### Readable code

The code need to state **three questions of purpose**, in order of importance:

- **Why** was the code written? A non-programmer should be able to understand the business value.
- **What** does the code do? There should be a clear pipeline that describe what functions data flow through.
- **How** does the code work? It should be simple to **gain** understanding of how the code works.

### Updatable code

TODO:

- Prepare for low cognitive load. 3-6 bits.
- Single purpose functions.
  - Logic vs composition.
- Separate logic from data structure.
- Sharing data / immutable data / function purity.

### Deletable code

All code has an upkeep cost. If we optimize for deletion, it means that we encourage a low upkeep of our code, and spend less time updating code with low business value.

A function can be deleted if you know that noone is calling that function. Your challange is to make it easier to track code usage.

An example where it is easier to create code than deleting is a classic MVC structure:

```
/models
-- user-model.ts
-- company-model.ts
/views
-- user-view.ts
-- company-view.ts
/controllers
-- user-controller.ts
-- company-controller.ts
```

It's easy to figure out where to create your code, but harder to know if a model can be deleted safely.

Here's an alternative that's more modular, making it easy to delete code:

```
/user
-- index.ts
-- model.ts
-- view.ts
-- controller.ts
/company
-- index.ts
-- model.ts
-- view.ts
-- controller.ts
```
