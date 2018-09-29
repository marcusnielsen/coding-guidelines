# coding-guidelines

This set of guidelines should strive for few rules with high consistency.

The north star (focus point) for all guidelines should be to minimize the cognitive burden on the reader of the code.

# The four pillars of CRUD
The guidelines should prioritze, in order, ease of:

#1. Deleting code. It should be simple to delete code safely in such case that a rewrite is needed.
#2. Updating code. It should be simple to update code in case of bugs or updated business needs.
#3. Reading code. It should be easy to follow the code through the application.
#4. Creating code. This is already cheap. Don't make it cheaper to write code that breaks #1-3 in favor of #4.

### Making code readable.
When creating code, you want to make sure another programmer can read the code and understand it.
The code need to state the _three questions of purpose_, in order of importance, *why*, *what*, and *how*:
* *Why* is the code written? Why are we adding this cost? A non-programmer should be able to understand this.
* *What* does the code do? There should be a clear code pipeline that describes what happens without cluttering it down with implementation details. This is only possible if the reader can *trust* your code.
* *How* does the code work? It should be simple to _gain_ understanding of how the code works. This does not mean that it should be simple to understand the code, since that would mean that every programmer need to have the same set of skills, and doing innovations would be impossible. It is important that the reader has a *curious* mindset when reading other people's code.

