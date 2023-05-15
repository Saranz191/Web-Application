<template>
  <div>
    <header>
      <nav>
        <ul>
          <a href="#home">Home</a>
          <a href="#about">About</a>
          <a href="#register">Register</a>
          <a href="#contact">Contact</a>
          <a @click="open_picture(0)" id="Booking0" class="booking-button">Booking Order</a>
          
        </ul>  
        
      </nav>
    </header>
    <main>
      <section id="home">
        <img src="https://media.istockphoto.com/id/886790858/th/%E0%B8%A3%E0%B8%B9%E0%B8%9B%E0%B8%96%E0%B9%88%E0%B8%B2%E0%B8%A2/%E0%B8%84%E0%B8%A3%E0%B8%AD%E0%B8%9A%E0%B8%84%E0%B8%A3%E0%B8%B1%E0%B8%A7%E0%B8%A1%E0%B8%B5%E0%B8%84%E0%B8%A7%E0%B8%B2%E0%B8%A1%E0%B8%AA%E0%B8%B8%E0%B8%82%E0%B8%94%E0%B8%B9%E0%B9%82%E0%B8%97%E0%B8%A3%E0%B8%97%E0%B8%B1%E0%B8%A8%E0%B8%99%E0%B9%8C%E0%B8%97%E0%B8%B5%E0%B9%88%E0%B8%9A%E0%B9%89%E0%B8%B2%E0%B8%99%E0%B8%82%E0%B8%AD%E0%B8%87%E0%B8%9E%E0%B8%A7%E0%B8%81%E0%B9%80%E0%B8%82%E0%B8%B2.jpg?s=612x612&w=0&k=20&c=8Uqu3zIliwsRkch71yX2u4TFBgzKiCwuEcsvrmOrtBM=">
        <h2>Welcome to Real Estate Web Application</h2>
        <a href="#register" class="btn">Register to get started</a>
        <span class="color color--blue" :data-value="1"></span>
        <span class="color color--orange" :data-value="1"></span>
        <span class="color color--green" :data-value="1"></span>
      </section>
      <section id="services">
        <h2>Our new projects</h2>
        <ul>
          <li>
            
            <div class="service-text">
              <img @click="open_picture(1)" id="img1" class="picture" src="https://img.iproperty.com.my/angel-legacy/1110x624-crop/static/2021/04/Modern-house-with-good-design.jpg">
              <h3>Region A</h3>
              <p>Location A, Property Type A, Price A$</p>
            </div>
          </li>
          <li>
            
            <div class="service-text">
              <img @click="open_picture(2)" id="img2" class="picture" src="https://www.architect-bkk.com/imageplans/pic_small/BB-H2-42501.15_3d1_small.jpg">
              <h3>Region B</h3>
              <p>Location B, Property Type B, Price B$</p>
            </div>
          </li>
          <li>
            
            <div class="service-text">
              
              <img @click="open_picture(3)" id="img3" class="picture" src="https://img.iproperty.com.my/angel-legacy/1110x624-crop/static/2021/03/House-Plan-Idea-for-Inspiration.jpg">
              <h3>Region C</h3>
              <p>Location C, Property Type C, Price C$</p>
            </div>
          </li>
          <li>
            
            <div class="service-text">
              <img @click="open_picture(4)" id="img4" class="picture" src="https://s359.thaibuffer.com/pagebuilder/39a91297-c4df-4458-82c5-88855f5d255d.jpg">
              <h3>Region D</h3>
              <p>Location D, Property Type D, Price D$</p>
            </div>
          </li>
        </ul>
      </section>
      <ul01 id="img0" href="#01" class="modal-01" style="display: none;">
            
            <div class="modal-page-01">
              <a @click.prevent="close_page(0)" href="#" class="close-modal">&#10006;</a>
              <table>
                <thead>
                  <tr style="color: black;">
                    <th>Product</th>
                    <th>Price</th>
                    <th>Quantity</th>
                    <th>Total</th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="(product, index) in products" :key="index">
                    <td>
                      <img class="small-img" :src="product.image">
                    </td>
                    <td style="color: black;">{{ product.price }}</td>
                    <td>
                      <button @click="decrementQuantity(index)" class="quantity-btn minus-btn" type="button">-</button>
                      <input class="quantity-input" type="text" v-model="product.quantity">
                      <button @click="incrementQuantity(index)" class="quantity-btn plus-btn" type="button">+</button>
                    </td>
                    <td style="color: black;">{{ product.total }}</td>
                  </tr>
                  <tr>
                    <td colspan="3"></td>
                    <td><button id="buy-btn" @click="buy">Buy</button></td>
                  </tr>
              </tbody>
              </table>
               <!-- <table>
                <thead>
                  <tr>
                    <th style="color: rgb(134, 129, 129);">Product</th>
                    <th style="color: rgb(134, 129, 129);">Price</th>
                    <th style="color: rgb(134, 129, 129);">Quantity</th>
                    <th style="color: rgb(134, 129, 129);">Total</th>
                  </tr>
                </thead>
                <tbody>
                  <tr>
                    <td>
                      <img class="small-img" src="https://img.iproperty.com.my/angel-legacy/1110x624-crop/static/2021/04/Modern-house-with-good-design.jpg">
                    </td>
                    <td style="color: black;">$500000</td>
                    <td>
                      <button @click="decrementQuantity(index)" class="quantity-btn minus-btn" type="button">-</button>
                      <input class="quantity-input" type="text" value="0">
                      <button  @click="incrementQuantity(index)" class="quantity-btn minus-btn" type="button">+</button>
                    </td>
                    <td style="color: black;">$0</td>
                  </tr>
                  <tr>
                    <td>
                      <img class="small-img" src="https://www.architect-bkk.com/imageplans/pic_small/BB-H2-42501.15_3d1_small.jpg">
                    </td>
                    <td style="color: black;">$30000</td>
                    <td>
                      <button class="quantity-btn minus-btn" type="button">-</button>
                      <input class="quantity-input" type="text" value="0">
                      <button class="quantity-btn plus-btn" type="button">+</button>
                    </td>
                    <td style="color: black;">$0</td>
                  </tr>
                  <tr>
                    <td>
                      <img class="small-img" src="https://img.iproperty.com.my/angel-legacy/1110x624-crop/static/2021/03/House-Plan-Idea-for-Inspiration.jpg">
                    </td>
                    <td style="color: black;">$750000</td>
                    <td>
                      <button class="quantity-btn minus-btn" type="button">-</button>
                      <input class="quantity-input" type="text" value="0">
                      <button class="quantity-btn plus-btn" type="button">+</button>
                    </td>
                    <td style="color: black;">$0</td>
                  </tr>
                  <tr>
                    <td>
                      <img class="small-img" src="https://s359.thaibuffer.com/pagebuilder/39a91297-c4df-4458-82c5-88855f5d255d.jpg">
                    </td>
                    <td style="color: black;">$1000000</td>
                    <td>
                      <button class="quantity-btn minus-btn" type="button">-</button>
                      <input class="quantity-input" type="text" value="0">
                      <button class="quantity-btn plus-btn" type="button">+</button>
                    </td>
                    <td style="color: black;">$0</td>
                  </tr>
                  <tr>
                    <td colspan="3"></td>
                    <td><button id="buy-btn">Buy</button></td>
                  </tr>
                </tbody>
              </table> -->
              
                   
            </div>
      </ul01>
      <ul001 id="img_info_1" class="modal" style="display: none;">
        <div class="modal-page">
          <a @click.prevent="close_page(1)" href="#" class="close-modal">&#10006;</a>
          <img class="asset-img" src="https://img.iproperty.com.my/angel-legacy/1110x624-crop/static/2021/04/Modern-house-with-good-design.jpg" alt="Property Image">  
          <div class="modal-detail"> 
            
            <ul>
              <li>Location: <span>New York</span></li>
              <li>Price: <span>$500,000</span></li>
              <li>Bedrooms: <span>3</span></li>
              <li>Bathrooms: <span>2</span></li>
            </ul>
            <div type="button" @click="incrementQuantity(0)" class="Contact-agent"><a>Booking</a>
              <span class='color color--blue' data-value='1'></span>
              <span class='color color--orange' data-value='1'></span>
              <span class='color color--green' data-value='1'></span>
              <span class='color color--white' data-value='1'></span></div>
            <div type="button" class="request-tour"><a>Request a tour</a>
              <span class='color color--blue' data-value='1'></span>
              <span class='color color--orange' data-value='1'></span>
              <span class='color color--green' data-value='1'></span>
              <span class='color color--white' data-value='1'></span></div> 
            <div type="button" class="Contact-agent"><a>Contact agent</a>
              <span class='color color--blue' data-value='1'></span>
              <span class='color color--orange' data-value='1'></span>
              <span class='color color--green' data-value='1'></span>
              <span class='color color--white' data-value='1'></span></div> 
            
               
          </div>
        </div>
      </ul001>
      <ul002 id="img_info_2" class="modal" style="display: none;">
        <div class="modal-page">
          <a @click.prevent="close_page(2)" href="#" class="close-modal">&#10006;</a>
          <img class="asset-img" src="https://www.architect-bkk.com/imageplans/pic_small/BB-H2-42501.15_3d1_small.jpg" alt="Property Image">  
          <div class="modal-detail"> 
            
            <ul>
              <li>Location: <span>Tokyo</span></li>
              <li>Price: <span>$300,000</span></li>
              <li>Bedrooms: <span>2</span></li>
              <li>Bathrooms: <span>2</span></li>
            </ul>
            <div @click="incrementQuantity(1)" type="button" class="Contact-agent"><a>Booking</a>
              <span class='color color--blue' data-value='1'></span>
              <span class='color color--orange' data-value='1'></span>
              <span class='color color--green' data-value='1'></span>
              <span class='color color--white' data-value='1'></span></div>
            <div type="button" class="request-tour"><a>Request a tour</a>
              <span class='color color--blue' data-value='1'></span>
              <span class='color color--orange' data-value='1'></span>
              <span class='color color--green' data-value='1'></span>
              <span class='color color--white' data-value='1'></span></div> 
            <div type="button" class="Contact-agent"><a>Contact agent</a>
              <span class='color color--blue' data-value='1'></span>
              <span class='color color--orange' data-value='1'></span>
              <span class='color color--green' data-value='1'></span>
              <span class='color color--white' data-value='1'></span></div> 
            
               
          </div>
        </div>
      </ul002>
      <ul003 id="img_info_3" class="modal" style="display: none;">
        <div class="modal-page">
          <a @click.prevent="close_page(3)" href="#" class="close-modal">&#10006;</a>
          <img class="asset-img" src="https://img.iproperty.com.my/angel-legacy/1110x624-crop/static/2021/03/House-Plan-Idea-for-Inspiration.jpg" alt="Property Image">  
          <div class="modal-detail"> 
            
            <ul>
              <li>Location: <span>Moscow</span></li>
              <li>Price: <span>$750,000</span></li>
              <li>Bedrooms: <span>4</span></li>
              <li>Bathrooms: <span>2</span></li>
            </ul>
            <div @click="incrementQuantity(2)" type="button" class="Contact-agent"><a>Booking</a>
              <span class='color color--blue' data-value='1'></span>
              <span class='color color--orange' data-value='1'></span>
              <span class='color color--green' data-value='1'></span>
              <span class='color color--white' data-value='1'></span></div>
            <div type="button" class="request-tour"><a>Request a tour</a>
              <span class='color color--blue' data-value='1'></span>
              <span class='color color--orange' data-value='1'></span>
              <span class='color color--green' data-value='1'></span>
              <span class='color color--white' data-value='1'></span></div> 
            <div type="button" class="Contact-agent"><a>Contact agent</a>
              <span class='color color--blue' data-value='1'></span>
              <span class='color color--orange' data-value='1'></span>
              <span class='color color--green' data-value='1'></span>
              <span class='color color--white' data-value='1'></span></div> 
            
               
          </div>
        </div>
      </ul003>
      <ul004 id="img_info_4" class="modal" style="display: none;">
        <div class="modal-page">
          <a @click.prevent="close_page(4)" href="#" class="close-modal">&#10006;</a>
          <img class="asset-img" src="https://s359.thaibuffer.com/pagebuilder/39a91297-c4df-4458-82c5-88855f5d255d.jpg" alt="Property Image">  
          <div class="modal-detail"> 
            
            <ul>
              <li>Location: <span>Barcelona</span></li>
              <li>Price: <span>$1,000,000</span></li>
              <li>Bedrooms: <span>8</span></li>
              <li>Bathrooms: <span>4</span></li>
            </ul>
            <div type="button" @click="incrementQuantity(3)" class="Contact-agent"><a>Booking</a>
              <span class='color color--blue' data-value='1'></span>
              <span class='color color--orange' data-value='1'></span>
              <span class='color color--green' data-value='1'></span>
              <span class='color color--white' data-value='1'></span></div>
            <div type="button" class="request-tour"><a>Request a tour</a>
              <span class='color color--blue' data-value='1'></span>
              <span class='color color--orange' data-value='1'></span>
              <span class='color color--green' data-value='1'></span>
              <span class='color color--white' data-value='1'></span></div> 
            <div type="button" class="Contact-agent"><a>Contact agent</a>
              <span class='color color--blue' data-value='1'></span>
              <span class='color color--orange' data-value='1'></span>
              <span class='color color--green' data-value='1'></span>
              <span class='color color--white' data-value='1'></span></div> 
            
               
          </div>
        </div>
      </ul004>
      <section id="register">
        <h2>Registeration Form</h2>
        <form>
          <label for="name">Name:</label>
          <input type="text" id="name" name="name" required>
          <label for="lastname">Lastname:</label>
          <input type="text" id="lastname" name="lastname" required>
          <br /><label for="email">Email:</label>
          <input type="email" id="email" name="email" required>
          <br /><label for="telephone">Tel:</label>
          <input type="tel" id="telephone" name="telephone" required>
          <br /><label for="age">Age:</label>
          <input type="number" id="age" name="age" min="18" max="100" required>
          <br /><label for="occupation">Occupation:</label>
          <input type="text" id="occupation" name="occupation" required>
          <br /><button type="submit">Submit</button>
        </form>
      </section>
      <section id="contact">
        <h2>Contact Us</h2>
        <form>
          <label for="name">Name:</label>
          <input type="text" id="name" name="name" required>
          <br /><label for="email">Email:</label>
          <input type="email" id="email" name="email" required>
          <br /><label for="message">Message:</label>
          <textarea id="message" name="message" required></textarea>
          <br /><button type="submit">Submit</button>
        </form>
      </section>
      <section id="about">
        <h2>About Us</h2>
        <p>We are a real estate company committed to providing the best service to our clients.</p>
      </section>
      <section id="services">
        <h2>Our Services</h2>
        
        <ul>
          <li>Buy and sell properties</li>
          <li>Property management</li>
          <li>Real estate consulting</li>
        </ul>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [
        {
          image: 'https://img.iproperty.com.my/angel-legacy/1110x624-crop/static/2021/04/Modern-house-with-good-design.jpg',
          price: '$500000',
          quantity: 0,
          total: '$0'
        },
        {
          image: 'https://www.architect-bkk.com/imageplans/pic_small/BB-H2-42501.15_3d1_small.jpg',
          price: '$30000',
          quantity: 0,
          total: '$0'
        },
        {
          image: 'https://img.iproperty.com.my/angel-legacy/1110x624-crop/static/2021/03/House-Plan-Idea-for-Inspiration.jpg',
          price: '$750000',
          quantity: 0,
          total: '$0'
        },
        {
          image: 'https://s359.thaibuffer.com/pagebuilder/39a91297-c4df-4458-82c5-88855f5d255d.jpg',
          price: '$1000000',
          quantity: 0,
          total: '$0'
        }
      ]
      // toggle0: false,
      // toggle1: false,
      // toggle2: false,
      // toggle3: false,
      // toggle4: false,
      // close0: false,
      // close1: false,
      // close2: false,
      // close3: false,
      // close4: false
      // ...Array.from({length: 5}, (_, i) => [`toggle${i}`, false])
      // .concat(Array.from({length: 5}, (_, i) => [`close${i}`, false]))
      // .reduce((acc, [key, value]) => ({...acc, [key]: value}), {})
    }
  },
  methods: {
    open_picture(buttonnum) {
        // this.toggle0 = !this.toggle0;
        // this.toggle1 = !this.toggle1;
        // this.toggle2 = !this.toggle2;
        // this.toggle3 = !this.toggle3;
        // this.toggle4 = !this.toggle4;
        if ( buttonnum === 0) {//this.toggle0 &&
            document.getElementById("img0").style.display = "block";
            document.getElementById("Booking0").style.display = "none";
            // this.toggle0 = false;
            // buttonnum = 0;
        } else if (buttonnum === 1 ) {//this.toggle1 && 
            document.getElementById("img_info_1").style.display = "block";
            document.getElementById("Booking0").style.display = "none";
            // this.toggle1 = false;
            // buttonnum = 0;
        } else if (buttonnum === 2) {//this.toggle2 &&
            document.getElementById("img_info_2").style.display = "block";
            document.getElementById("Booking0").style.display = "none";
            // this.toggle2 = false;
            // buttonnum = 0;
        } else if (buttonnum === 3) {//this.toggle3 &&
            document.getElementById("img_info_3").style.display = "block";
            document.getElementById("Booking0").style.display = "none";
            // this.toggle3 = false;
            // buttonnum = 0;
        } else if (buttonnum === 4) {//this.toggle4 &&
            document.getElementById("img_info_4").style.display = "block";
            document.getElementById("Booking0").style.display = "none";
            // this.toggle4 = false;
            // buttonnum = 0;
        }
    },
    close_page(buttonnumber) {
        // this.close0 = !this.close0;
        // this.close1 = !this.close1;
        // this.close2 = !this.close2;
        // this.close3 = !this.close3;
        // this.close4 = !this.close4;
        // console.log(buttonnumber);
        // console.log(this.close1);
        if (buttonnumber === 0 ) { //this.close0 && 
            document.getElementById("img0").style.display = "none";
            document.getElementById("Booking0").style.display = "block";
            //this.close0 = false;
            // buttonnumber = 0;
        } else if ( buttonnumber === 1) {//this.close1 &&
            document.getElementById("img_info_1").style.display = "none";
            document.getElementById("Booking0").style.display = "block";
            //this.close1 = false;
            // buttonnumber = 0;
        } else if ( buttonnumber === 2) {//this.close2 &&
            document.getElementById("img_info_2").style.display = "none";
            document.getElementById("Booking0").style.display = "block";
            //this.close2 = false;
            // buttonnumber = 0;
        } else if ( buttonnumber === 3) {//this.close3 &&
            document.getElementById("img_info_3").style.display = "none";
            document.getElementById("Booking0").style.display = "block";
            //this.close3 = false;
            // buttonnumber = 0;
        } else if ( buttonnumber === 4) {//this.close4 &&
            document.getElementById("img_info_4").style.display = "none";
            document.getElementById("Booking0").style.display = "block";
            //this.close4 = false;
            // buttonnumber = 0;
        }
    },
    incrementQuantity(index) {
      
      this.products[index].quantity++
      this.calculateTotal(index)
      alert('The product was added!');
      
    },
    decrementQuantity(index) {
      if (this.products[index].quantity > 0) {
        this.products[index].quantity--
        this.calculateTotal(index)
        alert('The product was removed!');
      }
    },
    calculateTotal(index) {
      const price = Number(this.products[index].price.slice(1))
      const quantity = this.products[index].quantity
      const total = price * quantity
      this.products[index].total = `$${total}`
    },
    buy() {
      alert('Thank you for your purchase!');
    }

}
    
}
</script>

<style>

/* Reset Styles */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  
  /* Global Styles */
  body {
    font-family: Arial, sans-serif;
    font-size: 18px;
    line-height: 1.5;
    background-color: #222;
    color: rgb(250, 248, 248);
  }
  
  header {
    background-color: rgb(248, 252, 252);
    color: #fff;
    padding: 1rem;
  }
  
  nav {
    display: flex;
    justify-content: flex-end; /* aligns items to the right */
    align-items: center;
    height: 70px;
    background-color: #333 /* linear-gradient(125deg, #333, #222); */
  }

  nav ul {
    display: flex;
    list-style: none;
    margin: 0;
    padding: 0;
  }
  
  nav li {
    margin-right: 0 10px;
  }
  
  nav a {
    display: block;
    padding: 0 15px;
    color: #fff;
    text-decoration: none;
    font-size: 16px;
  }
  
  main {
    padding: 1rem;
  }
  
  section {
    margin-bottom: 2rem;
    background-color: rgb(37, 37, 37);
    padding: 1rem;
  }
  
  h1 {
    font-size: 2rem;
    font-weight: bold;
    margin-bottom: 1rem;
  }

  ul {
    list-style: none;
    margin: 0;
    padding: 0;
  }
  
  li {
    margin-bottom: 1rem;
  }
  
  a {
    color: #fff;
    text-decoration: none;
  }
  
  img {
    max-width: 100%;
    height: auto;
    margin-bottom: 0.5rem;
  }
  
  .property {
    display: flex;
    flex-direction: column;
    margin-bottom: 2rem;
    padding: 1rem;
    border: 1px solid #fff;
  }
  
  .property h2 {
    font-size: 1.5rem;
    font-weight: bold;
    margin-bottom: 0.5rem;
  }
  
  .property p {
    margin-bottom: 0.5rem;
  }
  
  .property p:last-of-type {
    margin-bottom: 0;
  }

  #home {
    background: none;
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  
  #home img {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    z-index: -1;
  }
  
  #home h2 {
    font-size: 60px;
    color: rgb(5, 5, 5);
    text-align: center;
    margin-bottom: 30px;
  }

  .btn {
    font-family:sans-serif;
    color:white;
    text-decoration:none;
    text-transform:uppercase;
    letter-spacing:2.8px;
    background-color: #1b8bf9;
    padding:15px 50px;
    border-radius:5rem;
    box-shadow: 1px 2.9px 16px rgba(27,139,249,0.4);
    transition:0.6s cubic-bezier(0.01, 1.69, 0.99, 0.94); 
    /* display: flex;  */
  } 

  .btn:hover {
    transform: scale(1.1);
    transition: 0.3s;
  }

  .sidebar-search {
    padding: 10px;
    border: none;
    outline: none;
    border-radius: 10px;
  }

  .sidebar-search:focus {
    border:2px solid #e61b36;
  }
  
  .asset-img {
    width: 40vw;
    height: 40vw;
    border-radius: 15px;
    object-fit: cover;
  }

  .asset-img:hover {
    transform: scale(1.1);
    transition: 0.6s;
  }
  .modal {
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.5);
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .modal-page {
    z-index: 99;
    min-width: 50vw;
    max-height: 42vw;
    background: rgb(233, 226, 226);
    border-radius: 15px;
    padding: 20px;
    display: flex;
    /* position: relative; */
  }
  
  .modal-detail {
    flex-direction: column; /* make child elements stack vertically */
    font-size: 25px;
    color: rgb(0, 0, 0);
    margin-top: 5vw; /* move the buttons down */
    margin-left: 1vw;
    display: flex;

  }

  .Booking {
    font-family:sans-serif;
    color:white;
    text-decoration:none;
    text-transform:uppercase;
    letter-spacing:2.8px;
    background-color: #1b8bf9;
    padding:15px 50px;
    border-radius:5rem;
    box-shadow: 1px 2.9px 16px rgba(27,139,249,0.4);
    transition:0.6s cubic-bezier(0.01, 1.69, 0.99, 0.94);
    margin-bottom: auto;
    margin-top: 0.5vw;
    margin-left: auto;
    cursor: pointer;
     
  }

  .request-tour {
    font-family:sans-serif;
    color:white;
    text-decoration:none;
    text-transform:uppercase;
    letter-spacing:2.8px;
    background-color: #1b8bf9;
    padding:15px 50px;
    border-radius:5rem;
    box-shadow: 1px 2.9px 16px rgba(27,139,249,0.4);
    transition:0.6s cubic-bezier(0.01, 1.69, 0.99, 0.94);
    margin-bottom: auto;
    margin-left: auto;
    margin-top: auto;
    cursor: pointer;
    
  } 
  .Contact-agent {
    font-family:sans-serif;
    color:white;
    text-decoration:none;
    text-transform:uppercase;
    letter-spacing:2.8px;
    background-color: #1b8bf9;
    padding:15px 50px;
    border-radius:5rem;
    box-shadow: 1px 2.9px 16px rgba(27,139,249,0.4);
    transition:0.6s cubic-bezier(0.01, 1.69, 0.99, 0.94);
    margin-bottom: auto;
    margin-top: auto;
    margin-left: auto;
    cursor: pointer;
     
  }
  
  
  .close-modal {
    position: absolute;
    top: 0;
    right: 0;
    margin: 10px;
    font-size: 24px;
    color: #555;
    text-decoration: none;
  }
  
  .close-modal:hover {
    color: #f00;
  }
  .booking-button {
    background-color: #1b8bf9; /* Green background */
    color: white; /* White text */
    border: none; /* Remove border */
    padding: 12px 20px; /* Padding */
    font-size: 16px; /* Font size */
    position: fixed; /* Fixed position */
    top: 100px; /* Distance from top */
    right: 20px; /* Distance from right */
    z-index: 1; /* Ensure it appears on top */
    cursor: pointer; /* Add cursor on hover */
    border-radius:5rem;
    display: flex;
  }
  
  .booking-button:hover {
    background-color: #2716c2; /* Darker green on hover */
  }

  .piture-on-cart {
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.5);
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;

  }

  .small-img {
    width: 100px; /* adjust the size as per your requirement */
    height: 100px; /* adjust the size as per your requirement */
    margin: 20px; /* adjust the margin as per your requirement */
  }
  
  .modal-page-01 {
    flex-direction: column;
    align-items: center;
    justify-content: center;
    position: fixed;
    top: 5vw;
    right: 30vw;
    z-index: 500;
    width: 30%;
    height: 80%;
    background: rgb(243, 232, 232);
    border-radius: 30px;
    padding: 20px;
    display: flex;
  }
  
  .modal-01 {   
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.5);
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .image-info {
    position: absolute;
    bottom: 0;
    width: 100%;
    background-color: rgba(0, 0, 0, 0.7);
    color: #fff;
    font-size: 16px;
    padding: 10px;
  }

  table {
    border-collapse: collapse;
    width: 100%;
  }
  
  th, td {
    text-align: center;
    border: 1px solid #ddd;
    padding: 8px;
  }
  
  .quantity-input {
    width: 40px;
    text-align: center;
  }
  
  .quantity-btn {
    font-size: 18px;
    line-height: 18px;
    width: 24px;
    height: 24px;
    border-radius: 50%;
    border: 1px solid #ccc;
    background-color: #fff;
    color: #444;
    cursor: pointer;
    margin: 0 4px;
  }
  
  .plus-btn {
    padding-left: 4px;
    padding-right: 4px;
    
  }
  
  .minus-btn {
    padding-left: 4px;
    padding-right: 7px;
  }
  
  #buy-btn {
    background-color: green;
    color: white;
    font-size: 16px;
    padding: 10px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    float: right;
  }

  .picture {
  width: 900px;
  height: auto;
  border-radius: 20px;
  }

  .picture {
  cursor: pointer;
}

.picture:hover {
  transform: scale(1.07);
  transition: 0.5s;
}

  
</style>
