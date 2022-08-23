# Postman circular dependency import error

This is an example that fails, to reproduce:

1. Click Import on the upper left.
2. Choose to import a folder, and choose this project's repository as the folder.
3. Choose whichever options you want and import it
4. No Collection is created, or the collection is empty

To fix this, you can just edit either Type-A.yaml or Type-B.yaml and remove the reference to the other. Following the steps above the import will now work

# Why this should work

In our case we know that if we request a Type-A, then its type-a may only have OnlyIntegers in their type-b, and the same is the other way around, so this circular dependency is not an issue.

Maybe see also https://github.com/OAI/OpenAPI-Specification/issues/822
