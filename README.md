# Firebase Data Inconsistency: Unhandled Runtime Errors

This repository demonstrates an uncommon Firebase error related to data inconsistency within a collection.  The client-side code attempts to access a field ('displayName' in this case) that may be missing in some documents, resulting in runtime errors or silent failures.

## Bug Description:
The primary issue is that the client-side code assumes the existence of the 'displayName' field in every document of the 'users' collection.  However, if any documents lack this field, accessing `doc.data().displayName` will throw an error.

## Solution:
The best solution is to check for the existence of the field before accessing it.  This ensures robust error handling and prevents unexpected crashes.

## How to Reproduce:
1. Set up a Firebase project.
2. Create a 'users' collection.
3. Add some documents with the 'displayName' field and others without it.
4. Run the client-side code provided in `bug.js`.
5. Observe the errors.