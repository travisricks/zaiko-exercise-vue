# zaiko-exercise-vue

# Notes
- Implementation **does not** have to be pixel-perfect to the provided mock ups; you can also make changes you believe would improve readability, accessibility, etc. We may ask about the rationale behind large changes.
- A base Vue 3 + Bootstrap installation is provided, but feel free to use your preference of framework or libraries.
- Base components containing the required text are provided. Feel free to change the HTML or create new files, but all text in the component must be used.

---

# Task 0: Set up

1. Install
   ```
   npm install
   ```
2. Compile with hot-reloads
   ```
   npm run serve
   ```

---

# Task 1: Coupon Component
1. Update `./src/CouponComponent.vue` to match the following mock up:

   <center>
   <img src="https://d38fgd7fmrcuct.cloudfront.net/1_3xcb9oxm04axv5axgexku.jpg" />
   
   <i>Task 1 Mock up: Wide screen view</i>
   </center>
   <center><img src="https://d38fgd7fmrcuct.cloudfront.net/1_3xcb9p04umy5xcm4btn2m.jpg" />
   
   <i>Task 1 Mock up: Mobile view</i>
   </center>

2. The component must be responsive and display well on both PC and mobile view.
3. **Stretch goal:** We've provided an asset for the coupon in `./src/assets/coupon.png`, but if you're feeling ambitious you can try converting this to SVG or pure CSS.

---

# Task 2: Premium Component
1. Update `./src/PremiumComponent.vue` to match the following mock up:
   <center>
   <img src="https://d38fgd7fmrcuct.cloudfront.net/1_3xcbbnxjprnkhtgwrqjj1.jpg" />

   <i>Task 2 Mock up: Wide screen view</i>
   </center>
   <center><img src="https://d38fgd7fmrcuct.cloudfront.net/1_3xcbbnvx9mktw7go0fxoy.jpg" />

   <i>Task 2 Mock up: Mobile view</i>
   </center>

2. GIF and ribbon assets are available at `./src/assets/premium_mobile_coin.gif` and `./src/assets/premium_ribbon.png`
3. The component must be responsive and display well on both PC and mobile view.
4. **Stretch goal:** We've provided an asset for the ribbon in `./src/assets/premium_ribbon.png`, but if you're feeling ambitious you can try converting this to SVG or pure CSS.

---

# Task 3: API Interaction
1. `./src/MenuComponent.vue` contains a loading spinner and a table.
2. Add an API call that fills the table with data from `public/data/menu.json`.
3. Before the data is loaded, the loading spinner should be shown and the table should be hidden. After the data is loaded, the loading spinner should be hidden and the table should be shown.
4. Items in the menu can be hot or cold, designated by their category. Hot menu items should be red and cold menu items should be blue. 
5. **Hint:** While the server is running, the JSON file should be accessible by default at `http://localhost:8080/data/menu.json`
6. **Hint:** We've already installed axios but you're free to use whatever library or implementation you're comfortable with.
<center><img src="https://d38fgd7fmrcuct.cloudfront.net/1_3xd57oayx7a7dhic3414w.jpg" />

*Task 3 Sample*
</center>