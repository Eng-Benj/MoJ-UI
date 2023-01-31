<h1>THIS PROGRAM ACTS TO SERVE AS A SHOP'S CHECKOUT MACHINE</h1>


<section id="user-guide">
<h2>DIRECTIONS FOR USE</h2>

<p>The functionality of the UI available to the user is outlined below:</p>

<ul>
   <li>Use the plus and minus buttons to add and remove items from the cart.</li>
   <li>Use the standard checkout button to calculate the discount to apply to the current cart and the balance due.</li>
   <li>Use the express checkout button to clear the existing cart and follow prompts to select item quantities to checkout.</li>
   <li>After successfully checking out, press any button to clear the UI and start a new cart.</li>
   <li>Use the admin price and discount buttons to follow prompts and change product prices and discounts. DOING SO STARTS A FRESH CART.</li>
</ul>
</section>



<section id="dev-log">
<h2>DEV LOG</h2>

<p><strong>Development notes below:</strong></p>


<p>A checkout machine must be able to...
<ol>
  <li>Store product codes, unit prices, and discount information</li>
 
  <li>Change unit prices and discount information</li>
 
  <li>Store a live shopping cart with each individual item added</li>
 
  <li>Both add and remove items from the shopping cart</li>
 
  <li>Calculate the cart value before discounts</li>
 
  <li>Calculate discounts, where appropriate</li>
 
  <li>Checkout the cart, outputting a discounted total</li>
 </ol></p>

<p>JavaScript will form the core of this algorithm, and both array methods and functions will be utilised in majority. Each of the seven functionality points above is discussed below as they are built out:</p>


<p><strong>1 - Store product codes, unit prices, and discount information</strong>
<ul>
  <li>"products" and "discounts" were intitialised as arrays containing relevant information provided in the task.</li>
  <li>On a second pass, discounts[] was absorbed into products[] for simplicity, and all references to it were updated appropriately.
</ul></p>

<p><strong>2 - Change unit prices and discount information</strong>
<ul>
  <li>changePrice() and changeDiscount() were defined as functions to change the price and discount applied to a product respectively.</li>
  <li>Appropriate tests were implemented at the top of the function.</li>
  <li>On a second pass, a logic error in the productId test for both functions was fixed to account for its iterative nature.</li>
  <li>On a third pass, the logic of the number-based tests in both functions was changed to endsure only valid inputs would pass.</li>
  <li>On a fourth pass, test failures were changed to return "false" and console.log the error prompt instead of returning it directly</li>
</ul></p>

<p><strong>3 - Store a live shopping cart with each individual item added</strong>
<ul>
  <li>"cart" was initialised as an empty array.</li>
</ul></p>

<p><strong>4 - Both add and remove items from teh shopping cart</strong>
<ul>
  <li>addItem() was defined as a function to add a specified number of a specified item to the cart.</li>
  <li>The cart stores each individual item added as a copy of the associated array item in "products".</li>
  <li>removeItem() was defined as a funtion to remove a specified number of a specified item from the cart.</li>
  <li>If there are enough items to do so, the function removes an item of the correct product from "products" as many times as needed.</li>
  <li>Appropriate tests were implemented at the top of both functions.</li>
  <li>On a second pass, test failures were changed to return "false" and console.log the error prompt instead of returning it directly</li>
</ul></p>

<p><srong>5 - Calculate the cart value before discounts</strong>
<ul>
  <li>simplifyCart() was defined to reduce the cart down to a single entry for each product type, with a quantity and sub-total cost.</li>
  <li>sumCart() was defined to sum the sub-total costs in the simplified cart to output a total cart value as a number.</li>
  <li>Both functions had a test implemented which ensures they only proceed if there are items in the cart.</li>
</ul></p>

<p><strong>6 - Calculate discounts, where appropriate</strong>
<ul>
  <li>bulkFree() and bulkDiscount() were defined to apply each of the two types of discount respectively when called.</li>
</ul></p>

<p><strong>7 - Checkout the cart, outputting a discounted total</strong>
<ul>
  <li>chackout(), expressCheckout(), and clear() were all defined.</li>
  <li>checkout() chooses and calls appropriate functions to sum the cart, apply discounts, and output both balance due and total saved.</li>
  <li>expressCheckout() takes an amount of each product and calls checkout(), essentially performing a purchase in a single function.</li>
  <li>clear() simply empties the cart and associated variables after checkout() is performed, essentially saying "next customer".</li>
  <li>upon a later pass, the selection logic within expressCheckout() was changed such that 0 quantities would be skipped</li>
</ul></p>

<p><strong>HTML/CSS work</strong>
<ul>
  <li>After the JavaScript work above was completed, index.html was created and a reference to script.js was added to embed the code automatically when index.html is opened.</li>
  <li>A basic structure for the checkout was outlined in html.</li>
  <li>styles.css was linked to index.html, and a basic layout for the UI ws styled within.</li>
</ul></p>

<p><strong>JS query selector work</strong>
<ul>
  <li>After the above HTML/CSS work was completed, script.js was extended to include query selectors for each button which would select the correct functions to execute based on the button</li>
  <li>They would then call new functions to display the cart and totals</li>
</ul></p>