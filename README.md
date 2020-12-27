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
    <p class="class-name">Hello</p>
    <p class="red">Hi I'm Red!</p>
    <h1>
      <p class="class-name red">Reddish class!</p>
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
    p.class-name.red,
    .red {
    }
    ```

  - Every Child

    - Selects all the p tags even the ones inside h1 tag.

    ```css
    div p {
    }
    ```

- Inheritance

  - Few properties are inherited by default. (Ones which makes sense.)

  ```html
  <div>
    <p>
      Lorem Ipsum is simply dummy text of the printing and typesetting industry.
      Lorem Ipsum has been the industry's standard dummy text ever since the
      1500s.
    </p>
    <p>
      It is a long established fact that a reader will be distracted by the
      readable content of a page when looking at its layout.
    </p>
  </div>
  ```

  ```css
  div {
    color: 'yellow'; /* Inherited by all the p tags */
    border: 1px solid red; /* Not inherited by default.*/
  }

  p {
    color: inherit; /* Default */
    color: initial; /* Way to prevent*/
  }
  ```

  - Specificity

    - https://specificity.keegan.st/
    - It contains 4 numbers.
      - 0 0 0 0
      - important ids classes elements

    ```html
    <h2 id="heading-id" class="header">
      <span
        >Lorem Ipsum is simply dummy text of the printing and typesetting
        industry.</span
      >
      Something else here as well.
    </h2>

    <p id="para" class="paragraph">
      It is a long established fact that a reader will be distracted by the
      readable content of a page when looking at its layout.
    </p>
    ```

    ```css
    /* 0 0 1 2 */
    h2.header span {
      color: 'pink';
    }

    /* More specific */
    /* 0 1 0 1 */
    #heading-id span {
      color: 'purple';
    }
    ```
