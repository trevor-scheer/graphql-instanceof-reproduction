To reproduce, use scripts:

- `npm test`
- `npm run test:debug` (for node debugging)

These scripts do a fresh install in order to ensure the node modules and lockfile are in the intended state. Once the project is setup, they attempt to run `apollo client:codegen` on a simple project. The failure branch, when debugged, reveals an `instanceof` check failing near the source of the thrown `GraphQLError`.

Branches:

- `master`: Functioning - graphql versions aligned. `npm ls graphql` reveals an ideal state.
- `version-mismatch`: Breaks - graphql versions intentionally misaligned. `npm ls graphql` reveals multiple versions of graphql within the project.
