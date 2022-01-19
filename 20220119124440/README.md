# CRUD with `jq`

* **Create**
    Assigning/updating a value that does not exists will create it.
    See **Update** Below for example

* **Read**
  - lists

    If you want the output to be a list

    ```sh
    jq '.items' input.json
    ```

    If you want the output to be just the objects

    ```sh
    jq '.items[]' input.json
    ```
  - values

    ```sh
    jq '.items[0].key' input.json
    jq '.nested.key' input.json
    ```

  - item from a list with key that has specific value

    ```sh
    jq '.items[] | select(.name | contains("value"))' input.json
      ```

* **Update**
  - Updating a value

    ```sh
    jq '.nested.key = "new_value"' input.json
    ```
  - Adding to a list

    ```sh
    jq '.items += [{"name":"new_value"}]' input.json 
    ```

* **Delete**
  - a key

    ```sh
    jq 'del(.nested.key)' input.json
    ```
---

References:

* `man jq`
* How to add a field to a JSON object with the jq command? - Stack Overflow: <https://stackoverflow.com/questions/49632521/how-to-add-a-field-to-a-json-object-with-the-jq-command>
* json - How to filter an array of objects based on values in an inner array with jq? - Stack Overflow: <https://stackoverflow.com/questions/26701538/how-to-filter-an-array-of-objects-based-on-values-in-an-inner-array-with-jq>
* Add new element to existing JSON array with jq - Stack Overflow: <https://stackoverflow.com/questions/42245288/add-new-element-to-existing-json-array-with-jq>


Tags:

    #literature-note #unix #tools
