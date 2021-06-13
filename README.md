## Project Summary

In this project, you will practice various ways to control the position of elements. There is a guided video that you can follow along with to complete this project.

Click [here](https://positioning.pushcode.dev/) to see the website we will be cloning for this project.

## Goals

- Understand how the display property effects elements
- Understand the differences between block inline and inline-block
- Become familiar with flex
- Understand how to use the position property along with top, right, bottom and left
- Understand the differences between fixed, absolute, relative and sticky

## Steps

After each step, use git to add and commit the changes you have made to the project!

### Step 1.

Fork this repository to create your own copy.

### Step 2.

In the terminal on your computer, clone the repositry in your projects folder and cd into the created directory.

<details>

```
cd [path to your project directory];
git clone [github repository url goes here];
cd html-css-positioning-guided-project;
```

</details>

### Step 3.

create and html file `index.html`, and css file `style.css`.

<details>

```
touch index.html style.css
```

</details>

### Step 4.

create the basic html structure in your html file with html, head and body tags.

<details>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  </head>
  <body></body>
</html>
```

</details>

### Step 5.

Using title tags, add a title of `Positioning` within the head tags in your html.

<details>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Positioning</title>
  </head>
  <body></body>
</html>
```

</details>

### Step 6.

Link your css file to your html file using the `link` element. You may have noticed that there is a `reset.css` file in this repository. You will want to link this file in your html as well, and you want to make sure that the `reset.css` comes before your `style.css` file when you are linking them. See the details for this step to see how they should be linked.

What is the point of the reset file? Every browser implements certain default styles for many html elements. And different browsers can have different default styles as they apply their own borders, padding and margins. The `reset.css` will `reset` all of these styles to zero/none, which gives you more control of the styles applied to your page.

It is always recommended that you reset the browsers styles. If they are not reset, you will experience unwanted side-effects and things breaking. So for every project from now on, you will want to make sure to have this reset.css file applied.

<details>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Aloha!</title>

    <link
      rel="icon"
      type="image/jpeg"
      href="https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTIqcwYFMtqeikFk8F1d9J4oO4y1YDGY_YsMA&usqp=CAU"
    />
    <link href="reset.css" rel="stylesheet" />
    <link href="style.css" rel="stylesheet" />
  </head>
  <body></body>
</html>
```

</details>

### Step 7.

Let's create a header for our page. If you look at the header, we have a P on the left hand side and some navigation links on the right. Flex will be really useful here as we can use `justify-content: space-between` so that the available space is between the children.

<details>

<summary>index.html</summary>

```html
...
<header>
  <h1>P</h1>
  <nav>
    <a href="#about">about</a>
    <a href="#products">products</a>
    <a href="#contact">contact</a>
  </nav>
</header>
```

</details>

<details>

<summary>style.css</summary>

```css
* {
  box-sizing: border-box;
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 80px;
  padding: 0 48px;
  border-bottom: 1px solid rgba(0, 0, 0, 0.2);
  position: fixed;
  top: 0;
  width: 100%;
  background-color: white;
}

header > h1 {
  font-size: 24px;
}

header > nav > a {
  margin-left: 16px;
  text-decoration: none;
  color: black;
}
```

</details>

### Step 8.

In this step, we will create an info banner that we can dimiss by clicking a button.

<details>

<summary>index.html</summary>

```html
...
<div class="banner-wrapper">
  <input type="checkbox" id="dismiss" />
  <div class="banner">
    <label for="dismiss" class="dismiss-button">dismiss</label>
    <p>
      This is an informative message to let the user know some important
      information that we want to call out to them. But they have the option to
      dismiss it so it doesn't show anymore.
    </p>
  </div>
</div>
```

</details>

<details>

<summary>style.css</summary>

```css
.banner {
  background-color: rgb(210, 228, 254);
  color: rgb(0, 105, 255);
  height: 100px;
  width: 100%;
  border-bottom: 1px solid rgba(0, 0, 0, 0.2);
  position: fixed;
  top: 80px;
  padding: 16px;

  display: flex;
  align-items: center;
}

.banner > p {
  width: 80%;
}

#dismiss:checked ~ .banner {
  display: none;
}

#dismiss {
  display: none;
}

.dismiss-button {
  color: rgb(0, 105, 255);
  position: absolute;
  top: 4px;
  right: 4px;
  border: 1px solid rgba(0, 105, 255, 0.2);
  padding: 4px 8px;
  font-size: 12px;
}
```

</details>

### Step 9.

In this step, we will create the main display image for the page.

<details>

<summary>index.html</summary>

```html
...
<div class="display-picture"></div>
```

</details>

<details>

<summary>style.css</summary>

```css
.display-picture {
  background-image: url("https://images.unsplash.com/photo-1566814534947-46a09bcbb88c?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=919&q=80");
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 600px;
  position: sticky;
  top: 0;
  z-index: -1;
  margin-top: 80px;
}
```

</details>

### Step 10.

In this step, we will create the about section.

<details>

<summary>index.html</summary>

```html
...
<main>
  <section id="about">
    <h1>ABOUT SECTION</h1>
    <p>
      Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus,
      deleniti rem debitis at, perspiciatis hic blanditiis dolorum libero illo
      cumque aliquid totam nobis atque! Quod accusamus commodi minus nam omnis!
      Lorem ipsum dolor sit, amet consectetur adipisicing elit. Neque quia
      veniam quidem totam assumenda nobis ducimus, ea esse provident facere
      officia, beatae aliquam eveniet consequuntur! Repellendus a quam nesciunt
      ea.
    </p>
    <p>
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Molestiae
      adipisci necessitatibus hic numquam quaerat sint officia expedita debitis
      quidem aut facere, suscipit eligendi quos enim tenetur et modi sequi
      eaque? Lorem, ipsum dolor sit amet consectetur adipisicing elit. Accusamus
      velit culpa adipisci iure natus rerum, dolor nulla quisquam dolorem
      repellat praesentium deserunt, placeat quas ullam autem eaque, minus quod
      vitae. Lorem, ipsum dolor sit amet consectetur adipisicing elit. At
      facilis unde enim quia ea qui repellendus eos. Magni omnis tenetur illo,
      quasi at asperiores sapiente ullam quibusdam nostrum expedita quidem!
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Impedit rerum rem
      provident odio sit. Facilis, ipsum? In pariatur rem aut quas quam, dolorem
      asperiores error tenetur veniam ex. Minus, praesentium.
    </p>
    <p>
      Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus,
      deleniti rem debitis at, perspiciatis hic blanditiis dolorum libero illo
      cumque aliquid totam nobis atque! Quod accusamus commodi minus nam omnis!
      Lorem ipsum dolor sit, amet consectetur adipisicing elit. Neque quia
      veniam quidem totam assumenda nobis ducimus, ea esse provident facere
      officia, beatae aliquam eveniet consequuntur! Repellendus a quam nesciunt
      ea.
    </p>
  </section>
</main>
```

</details>

<details>

<summary>style.css</summary>

```css
main {
  padding: 48px;
  padding-top: 0;
  background: white;
}

main h1 {
  font-size: 36px;
  margin-bottom: 36px;
}

main p {
  line-height: 18px;
  font-size: 14px;
  margin-bottom: 16px;
}

section {
  padding-top: 104px;
}
```

</details>

### Step 11.

In this step, we will create the products section.

<details>

<summary>index.html</summary>
...

```html
<section id="products">
  <h1>PRODUCTS SECTION</h1>
  <div class="products-wrapper">
    <div class="product">
      <img
        width="240px"
        src="https://images.unsplash.com/photo-1601612628452-9e99ced43524?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MTR8fHByb2R1Y3RzfGVufDB8MnwwfA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=60"
        alt="product1"
      />
      <div class="product-details">
        <div class="product-name">product 1</div>
        <div class="product-description">this product is amazing!</div>
        <div class="product-price">24</div>
      </div>
    </div>
    <div class="product">
      <img
        width="240px"
        src="https://images.unsplash.com/photo-1601612628452-9e99ced43524?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MTR8fHByb2R1Y3RzfGVufDB8MnwwfA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=60"
        alt="product1"
      />
      <div class="product-details">
        <div class="product-name">product 1</div>
        <div class="product-description">this product is amazing!</div>
        <div class="product-price">24</div>
      </div>
    </div>
    <div class="product">
      <img
        width="240px"
        src="https://images.unsplash.com/photo-1601612628452-9e99ced43524?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MTR8fHByb2R1Y3RzfGVufDB8MnwwfA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=60"
        alt="product1"
      />
      <div class="product-details">
        <div class="product-name">product 1</div>
        <div class="product-description">this product is amazing!</div>
        <div class="product-price">24</div>
      </div>
    </div>
    <div class="product">
      <img
        width="240px"
        src="https://images.unsplash.com/photo-1601612628452-9e99ced43524?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MTR8fHByb2R1Y3RzfGVufDB8MnwwfA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=60"
        alt="product1"
      />
      <div class="product-details">
        <div class="product-name">product 1</div>
        <div class="product-description">this product is amazing!</div>
        <div class="product-price">24</div>
      </div>
    </div>
    <div class="product">
      <img
        width="240px"
        src="https://images.unsplash.com/photo-1601612628452-9e99ced43524?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MTR8fHByb2R1Y3RzfGVufDB8MnwwfA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=60"
        alt="product1"
      />
      <div class="product-details">
        <div class="product-name">product 1</div>
        <div class="product-description">this product is amazing!</div>
        <div class="product-price">24</div>
      </div>
    </div>
    <div class="product">
      <img
        width="240px"
        src="https://images.unsplash.com/photo-1601612628452-9e99ced43524?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MTR8fHByb2R1Y3RzfGVufDB8MnwwfA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=60"
        alt="product1"
      />
      <div class="product-details">
        <div class="product-name">product 1</div>
        <div class="product-description">this product is amazing!</div>
        <div class="product-price">24</div>
      </div>
    </div>
  </div>
</section>
```

...

</details>

<details>

<summary>style.css</summary>

```css
#products {
  margin-top: 48px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.products-wrapper {
  display: flex;
  justify-content: space-around;
  width: 900px;
  flex-wrap: wrap;
}

.product {
  box-shadow: 0px 0px 6px #e6e6e6, 2px 0px 8px #e6e6e6;
  margin-bottom: 24px;
}

.product-details {
  padding: 8px 16px;
}

.product-name {
  font-size: 18px;
  line-height: 24px;
  font-weight: 600;
}

.product-description {
  font-size: 14px;
  line-height: 18px;
}

.product-price {
  font-weight: 600;
  line-height: 24px;
}

.product-price::before {
  content: "$";
}
```

</details>

### Step 12.

In this step, we will create the contact section.

<details>

<summary>index.html</summary>
...

```html
<section id="contact">
  <h1>CONTACT SECTION</h1>
  <form>
    <div class="form-row">
      <div class="form-field">
        <label for="name">Name</label>
        <input id="name" />
      </div>

      <div class="form-field">
        <label for="email">Email</label>
        <input type="text" id="email" />
      </div>
    </div>
    <div class="form-field">
      <label for="message">Message</label>
      <textarea id="message"></textarea>
    </div>
    <button>SEND MESSAGE</button>
  </form>
</section>
```

...

</details>

<details>

<summary>style.css</summary>

```css
form label {
  display: block;
  position: relative;
  top: -4px;
}

.form-row {
  display: flex;
}

.form-field {
  margin-right: 8px;
  margin-bottom: 16px;
  flex: 1;
}

input,
textarea {
  padding: 8px;
  width: 100%;
}

button {
  padding: 8px;
}
```

</details>

## Submit project

The final step, and one of the most important! Use git to add and commit any new changes, then push those changes to your reposiroty on github.

Nice work! You learned a lot in this unit, and I hope that you are having fun while doing it! The more you practice, the easier this will become. Keep up the hard work. Make sure you submit this project in the `Guided project(s)` section for this unit. Just copy the url for your repository, paste it and click send!

## Solution

<details>

<summary>index.html</summary>

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Positioning</title>
    <link rel="stylesheet" href="reset.css" />
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <header>
      <h1>P</h1>
      <nav>
        <a href="#about">about</a>
        <a href="#products">products</a>
        <a href="#contact">contact</a>
      </nav>
    </header>
    <div class="banner-wrapper">
      <input type="checkbox" id="dismiss" />
      <div class="banner">
        <label for="dismiss" class="dismiss-button">dismiss</label>
        <p>
          This is an informative message to let the user know some important
          information that we want to call out to them. But they have the option
          to dismiss it so it doesn't show anymore.
        </p>
      </div>
    </div>
    <div class="display-picture"></div>
    <main>
      <section id="about">
        <h1>ABOUT SECTION</h1>
        <p>
          Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus,
          deleniti rem debitis at, perspiciatis hic blanditiis dolorum libero
          illo cumque aliquid totam nobis atque! Quod accusamus commodi minus
          nam omnis! Lorem ipsum dolor sit, amet consectetur adipisicing elit.
          Neque quia veniam quidem totam assumenda nobis ducimus, ea esse
          provident facere officia, beatae aliquam eveniet consequuntur!
          Repellendus a quam nesciunt ea.
        </p>
        <p>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Molestiae
          adipisci necessitatibus hic numquam quaerat sint officia expedita
          debitis quidem aut facere, suscipit eligendi quos enim tenetur et modi
          sequi eaque? Lorem, ipsum dolor sit amet consectetur adipisicing elit.
          Accusamus velit culpa adipisci iure natus rerum, dolor nulla quisquam
          dolorem repellat praesentium deserunt, placeat quas ullam autem eaque,
          minus quod vitae. Lorem, ipsum dolor sit amet consectetur adipisicing
          elit. At facilis unde enim quia ea qui repellendus eos. Magni omnis
          tenetur illo, quasi at asperiores sapiente ullam quibusdam nostrum
          expedita quidem! Lorem ipsum dolor sit amet consectetur adipisicing
          elit. Impedit rerum rem provident odio sit. Facilis, ipsum? In
          pariatur rem aut quas quam, dolorem asperiores error tenetur veniam
          ex. Minus, praesentium.
        </p>
        <p>
          Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus,
          deleniti rem debitis at, perspiciatis hic blanditiis dolorum libero
          illo cumque aliquid totam nobis atque! Quod accusamus commodi minus
          nam omnis! Lorem ipsum dolor sit, amet consectetur adipisicing elit.
          Neque quia veniam quidem totam assumenda nobis ducimus, ea esse
          provident facere officia, beatae aliquam eveniet consequuntur!
          Repellendus a quam nesciunt ea.
        </p>
      </section>
      <section id="products">
        <h1>PRODUCTS SECTION</h1>
        <div class="products-wrapper">
          <div class="product">
            <img
              width="240px"
              src="https://images.unsplash.com/photo-1601612628452-9e99ced43524?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MTR8fHByb2R1Y3RzfGVufDB8MnwwfA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=60"
              alt="product1"
            />
            <div class="product-details">
              <div class="product-name">product 1</div>
              <div class="product-description">this product is amazing!</div>
              <div class="product-price">24</div>
            </div>
          </div>
          <div class="product">
            <img
              width="240px"
              src="https://images.unsplash.com/photo-1601612628452-9e99ced43524?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MTR8fHByb2R1Y3RzfGVufDB8MnwwfA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=60"
              alt="product1"
            />
            <div class="product-details">
              <div class="product-name">product 1</div>
              <div class="product-description">this product is amazing!</div>
              <div class="product-price">24</div>
            </div>
          </div>
          <div class="product">
            <img
              width="240px"
              src="https://images.unsplash.com/photo-1601612628452-9e99ced43524?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MTR8fHByb2R1Y3RzfGVufDB8MnwwfA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=60"
              alt="product1"
            />
            <div class="product-details">
              <div class="product-name">product 1</div>
              <div class="product-description">this product is amazing!</div>
              <div class="product-price">24</div>
            </div>
          </div>
          <div class="product">
            <img
              width="240px"
              src="https://images.unsplash.com/photo-1601612628452-9e99ced43524?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MTR8fHByb2R1Y3RzfGVufDB8MnwwfA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=60"
              alt="product1"
            />
            <div class="product-details">
              <div class="product-name">product 1</div>
              <div class="product-description">this product is amazing!</div>
              <div class="product-price">24</div>
            </div>
          </div>
          <div class="product">
            <img
              width="240px"
              src="https://images.unsplash.com/photo-1601612628452-9e99ced43524?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MTR8fHByb2R1Y3RzfGVufDB8MnwwfA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=60"
              alt="product1"
            />
            <div class="product-details">
              <div class="product-name">product 1</div>
              <div class="product-description">this product is amazing!</div>
              <div class="product-price">24</div>
            </div>
          </div>
          <div class="product">
            <img
              width="240px"
              src="https://images.unsplash.com/photo-1601612628452-9e99ced43524?ixid=MXwxMjA3fDB8MHxzZWFyY2h8MTR8fHByb2R1Y3RzfGVufDB8MnwwfA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=60"
              alt="product1"
            />
            <div class="product-details">
              <div class="product-name">product 1</div>
              <div class="product-description">this product is amazing!</div>
              <div class="product-price">24</div>
            </div>
          </div>
        </div>
      </section>
      <section id="contact">
        <h1>CONTACT SECTION</h1>
        <form>
          <div class="form-row">
            <div class="form-field">
              <label for="name">Name</label>
              <input id="name" />
            </div>

            <div class="form-field">
              <label for="email">Email</label>
              <input type="text" id="email" />
            </div>
          </div>
          <div class="form-field">
            <label for="message">Message</label>
            <textarea id="message"></textarea>
          </div>
          <button>SEND MESSAGE</button>
        </form>
      </section>
    </main>
  </body>
</html>
```

</details>

<details>

<summary>style.css</summary>

```css
header {
  display: flex;
  justify-content: space-between;
  height: 80px;
  border-bottom: 1px solid rgba(0, 0, 0, 0.2);
  align-items: center;
  padding: 0 48px;
  position: fixed;
  width: 100%;
  top: 0;
  background-color: white;
}

header > h1 {
  font-size: 24px;
}

header > nav > a {
  margin-left: 16px;
  text-decoration: none;
  color: black;
}

.banner {
  background-color: rgb(210, 228, 254);
  color: rgb(0, 105, 255);
  height: 100px;
  width: 100%;
  border-bottom: 1px solid rgba(0, 0, 0, 0.2);
  position: fixed;
  top: 80px;
  padding: 16px;

  display: flex;
  align-items: center;
}

.banner > p {
  width: 80%;
}

#dismiss:checked ~ .banner {
  display: none;
}

#dismiss {
  display: none;
}

.dismiss-button {
  color: rgb(0, 105, 255);
  position: absolute;
  top: 4px;
  right: 4px;
  border: 1px solid rgba(0, 105, 255, 0.2);
  padding: 4px 8px;
  font-size: 12px;
}

.display-picture {
  background-image: url("https://images.unsplash.com/photo-1566814534947-46a09bcbb88c?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=919&q=80");
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 600px;
  position: sticky;
  top: 0;
  z-index: -1;
  margin-top: 80px;
}

main {
  padding: 48px;
  padding-top: 0;
  background: white;
}

main h1 {
  font-size: 36px;
  margin-bottom: 36px;
}

main p {
  line-height: 18px;
  font-size: 14px;
  margin-bottom: 16px;
}

section {
  padding-top: 104px;
}

#products {
  margin-top: 48px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.products-wrapper {
  display: flex;
  justify-content: space-around;
  width: 900px;
  flex-wrap: wrap;
}

.product {
  box-shadow: 0px 0px 6px #e6e6e6, 2px 0px 8px #e6e6e6;
  margin-bottom: 24px;
}

.product-details {
  padding: 8px 16px;
}

.product-name {
  font-size: 18px;
  line-height: 24px;
  font-weight: 600;
}

.product-description {
  font-size: 14px;
  line-height: 18px;
}

.product-price {
  font-weight: 600;
  line-height: 24px;
}

.product-price::before {
  content: "$";
}

form label {
  display: block;
  position: relative;
  top: -4px;
}

.form-row {
  display: flex;
}

.form-field {
  margin-right: 8px;
  margin-bottom: 16px;
  flex: 1;
}

input,
textarea {
  padding: 8px;
  width: 100%;
}

button {
  padding: 8px;
}
```

</details>
