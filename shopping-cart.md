{Curly brackets}

(Parentheses)

"quotes"

Photo by Vojtech Okenka from Pexels
Photo by Genaro Servín from Pexels



# Introduction

Hello everybody whats up today we are going to buld a shoping cart using jqery.

If we click the buy button we add the cupcake to the cart

Here we have the aount of cupcakes and the total price all right

Lets open visual studio code and start building our shoping cart

Here we have a html file and an image folder with the images that we are going to use

we are going to create all of the content dynamically so our html
only consists of one div with a class name of products

We have the jquery cdn and the script tags for our code

I have prepared an array with the products that Im gong to paste here

 Its an array with three objects and they all have an

an id

a name

an image

a price

and quantity

```javascript
//Products   
const products = [
            { "id": 1, "name": "Cupcake white frosting", "image": "./images/cake1.jpg", "price": 90, "quantity": 4 },
            { "id": 2, "name": "Cupcake strawberry toppings", "image": "./images/cake2.jpg", "price": 90, "quantity": 2 },
            { "id": 3, "name": "Cupcake fruit toppings", "image": "./images/cake3.jpg", "price": 100, "quantity": 0 }
        ]
```

I am going to collapse it to make our code easier to read

# Start building

Then Im going to store our products div in a variable

```javascript
        //Variables
        const $productsDiv = $(".products");
```



### Display products using for of loop

and now to display our products we need to loop through them  and define elements dynamically for each product 

To do this I will use a for of loop and say

```javascript
        for (let product of products) {

            //Display products dynamically
            $product = $(
                "<div class='product'>" +
                "<h3>" + product.name + "</h3>" +
                "<div class='product-image'>" +
                "<img src='" + product.image + "'/>" +
                "</div>" +
                "<p><b>Price: </b> " + product.price + "</p>" +
                "</div>"

            );
        }
```

In jquery we create an elelent dynamically the same way we would create a variable, we use the dollar signs and in parentheses we type the html in quotes, like a string.

So here we have a div with a class name of product and inside we have our product name, image and the price

Now we just need to append this to the products div to display it

```javascript
        for (let product of products) {

            //Display products dynamically
            $product = $(
                "<div class='product'>" +
                "<h3>" + product.name + "</h3>" +
                "<div class='product-image'>" +
                "<img src='" + product.image + "'/>" +
                "</div>" +
                "<p><b>Price: </b> " + product.price + "</p>" +
                "</div>"

            );
           $productsDiv.append($product);
        }
```

And if we look in the browser here are our products



### Paste in css

To make this look beautiful Im goint to paste some css that I have prepared

```css
    <style>
        .products {
            padding-top: 100px;
            display: grid;
            grid-template-columns: 20% 20% 20%;
            gap: 1rem;
            justify-content: center;
        }

        .product {
            display: flex;
            flex-direction: column;
            justify-content: flex-start;
            align-items: center;
            padding: 0.5rem;
            border: 0.0625rem solid #aaaaaa;
        }
    </style>
```

and now it looks much better



# Buy buttons

The next step is to add a button to each product. The button will say buy if we have the product in stock and it will say not in stock  if we have run out of the product. So to make that happen Im first going to create a button dynamically in our existing for loop . And then Im going to use a if statement and say

```javascript
            if (product.quantity == 0) {
                $buttonBuy.html("Not in stock");
                $buttonBuy.prop("disabled", true);
            } else {
                $buttonBuy.html("buy");

            }
```

If product quantity is 0 the button innerHTML will say not in stock and we will give it the disabled property

Else the button will say buy

And then we append our button to the product

```javascript
            //Display products dynamically
            $product = $(
                "<div class='product'>" +
                "<h3>" + product.name + "</h3>" +
                "<div class='product-image'>" +
                "<img src='" + product.image + "'/>" +
                "</div>" +
                "<p><b>Price: </b> " + product.price + "				</p>" +
                "</div>"

            );
            //Appending buy button to product
            $product.append($buttonBuy);
            //Appending product to products div
            $productsDiv.append($product);
```



stopped at website building LS2  2/6 at 02:26:32



















