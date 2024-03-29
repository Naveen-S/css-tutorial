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
    
    
   - Pseudo classes (state selectors)
   - 
     
     ```html
        <div>
          <label>Email</label>
          <input type="email" class="email" disabled />
        </div>
        <div>
          <label>My Name is</label>
          <input type="text" class="name" />
        </div>
        <button class="submit" type="submit">Send</button>
      ```
     
     ```css   
        .submit:hover {
            background-color: red;
          }
          .submit:focus {
            background-color: cyan;
          }
          .email:disabled {
            background-color: green;
          }
          .name:hover {
            background-color: purple;
          }
          .name:required {
            background-color: yellow;
          }
      ```
      
      - `span:first-child` : Add style to first child of span in a container. If the first child of a container is a div or anything else this style won't be applied.
      
      - `p:last-child`: Similar to above.
      
      - `span:first-of-type`: If you want the first span of the container (not first child of the container, span:first-child is applied only when the first child of the container is span, but span:first-of-type add the style to first child of the conatiner irrespective of whether it is the first child or not, but it should be first span in the container.)
      -  `:last-of-type`: Similar.
      -  `span:nth-child(2)`: If the 2nd child of the container is span apply these styles.
      -  `span:nth-child(even)`; Even children will get those styles.
      -  `span:nth-child(odd)`: Odd children.
      -  `span:nth-child(2n+3)`; We can also use the formula. 
      -  `span:nth-last-child(2n+1)`: Reverse of `nth-child`.
      -  `nth-first-of-type`:
      -  `nth-last-of-type`:

      
     - Box Model
        - margin-collapsing
        - box-sizing: `border-box` - size will be inclusive of padding and border.  Say width: 100px and height: 100px, if we provide padding 10px content's height and width will be adjusted (shrunken down) so that height and width still remains 100.
        - `content-box`: padding and border is additional, even though we specify width and height to be 100px padding and border will add on to that, so technically container's height and width will be greater than 100px.
        
        
        
 - Layout and Positioning.
    - Column layout:
        ```html 
         <style>
          .parent {
            height: 100vh;
            column-width: 400px; /* Minimum width the column.*/
            column-count: 5; /* Maximum columns that could be accomadated.*/
            column-rule: 30px solid lightgreen; /* Similar to border, but it can overlap the content not exactly like border. */
            column-gap: 40px; /* Now gap is increased so 30px border can be easily accomadated without overlap.*/
            column-fill: balance; /* By default it is balance which means content should be equally distributed between all the columns. If its auto if fills the first column first and then second and then third.*/
          }
          h2 {
            column-span: all;
          }
        </style>
        <div class="parent">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Non, accusantium. Lorem ipsum dolor sit amet consectetur, adipisicing elit. Non impedit modi iusto repellat, adipisci quam. Repellat ducimus expedita ipsam quaerat.
          <h2>
            Vijaya Karnataka
          </h2>
          <hr>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quis omnis accusamus deserunt. Laudantium similique mollitia praesentium ab ipsam veniam dignissimos consectetur. Culpa sapiente impedit autem iste perferendis et. Odio, laborum quia fugiat quo numquam quam magnam eveniet dolores incidunt, quasi blanditiis distinctio commodi ratione ad recusandae provident quod sint. Adipisci!
          <hr>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Eum voluptatibus quidem distinctio ratione, consequatur similique natus odit maxime fugit vel eveniet illum ipsum, repudiandae reiciendis. Perspiciatis officiis atque inventore fugit eius reprehenderit iste natus sapiente quo, delectus quas molestias, eos dignissimos accusamus corporis velit. Molestias eum minus numquam esse illum quod libero beatae dignissimos perspiciatis doloribus possimus fugiat, quibusdam soluta.
        </div>
        ```

     - Default position is `static`.
       
     - Fixed:
          - To fix the position on the div/item irrespective of the parent to a fixed position.

      - Sticky:
          - Similar to fixed but moves out of the screen if you scroll the page. Basically position will be fixed within the parent container. Majorly can be used a table header. 
      
      - Relative & Absolute: You know those.  
       
