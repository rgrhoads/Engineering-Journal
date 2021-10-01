# Bug List for TEMPLATE

## Solved:

- [x] ``` relation "product" does not exist ```
- Description: I was not able to query the database.
- Solution: In my .sql file I was not connecting to my database. Adding the below code resolved my issue.
  ``` javascript
    \c products_database;
  ```

## Unsolved:
