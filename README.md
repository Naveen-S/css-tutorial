### CSS 101

#### Selectors

- Universal selector

```
 * {
   margin: 0;
 }
```

- Combining selectors

  ```
    <div>
      <p class="class-name"> Hello </p>
      <p class="red"> Hi I'm Red! </p>
      <h1>
        <p class="class-name red"> Reddish class! </p>
      </h1>
    </div>
  ```

  - AND

    ```
      p.class-name.red {

      }
    ```

  - OR

    ```
      p.class-name.red, .red {

      }
    ```

  - Every Child
    Selects all the p tags even the ones inside h1 tag.

    ```
      div p {

      }
    ```
