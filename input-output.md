# Input types

- You CANNOT make **a field optional, but, if provided, non-null** using GraphQL schema
  - You can only enforce this in validation (class-validator), not GraphQL
- If GraphQL defaultValue decorator is applied, then the defaultValue is used whenever a field is missing(undefined)
  - This should be taken into account when dealing with updates
