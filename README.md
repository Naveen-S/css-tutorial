### CSS 101

#### Selectors

- Universal selector

```css
 * {
   margin: 0;
 }
```

- Combining selectors

  ```html
    <div>
      <p class="class-name"> Hello </p>
      <p class="red"> Hi I'm Red! </p>
      <h1>
        <p class="class-name red"> Reddish class! </p>
      </h1>
    </div>
  ```

  - AND

    ```css
      p.class-name.red {

      }
    ```

  - OR

    ```css
      p.class-name.red, .red {

      }
    ```

  - Every Child
    - Selects all the p tags even the ones inside h1 tag.

    ```css
      div p {

      }
    ```
