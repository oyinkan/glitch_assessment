<template>
  <div class="profile-wrapper">
    <div class="social-icons">
      <a href="https://instagram.com/`${data.social_media.instagram}`" target="_blank">
        <img 
          src="https://res.cloudinary.com/shakirah/image/upload/v1610115858/instagram.png"
          alt="Instagram icon"
        />
      </a>
      <a href="https://twitter.com/`${data.social_media.twitter}`" target="_blank">
        <img 
          src="https://res.cloudinary.com/shakirah/image/upload/v1610115858/twitter.png"
          alt="Twitter icon"
        />
      </a>
      <a href="https://snapchat.com/`${data.social_media.snapchat}`" target="_blank">
        <img 
          src="https://res.cloudinary.com/shakirah/image/upload/v1610115858/snapchat.png"
          alt="Snapchat icon"
        />
      </a>
      <a href="mailto:`${data.social_media.email}`">
        <img 
          src="https://res.cloudinary.com/shakirah/image/upload/v1610115858/message.png"
          alt="Message icon"
        />
      </a>
    </div>
    <h1>{{data.name}}</h1>
    <div class="profile-picture">
      <img 
        src="https://res.cloudinary.com/shakirah/image/upload/v1610112753/profile-picture.png"
        alt="profile picture"
      />
    </div>
    <nav>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><img src="https://res.cloudinary.com/shakirah/image/upload/v1610114643/picture.png" alt="my picture"></li>
        <li><a href="#">Gallery</a></li>
        <li><a href="#">Contact</a></li>
      </ul> 
    </nav>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  data(){
    return{
      data: {}
    }
  },
  created(){
    this.getData()
  },
  methods:{
    async getData(){
      try{
        const response = await axios.get('https://hirng-x2021.glitch.me/api');
        console.log(response);
        this.data = response.data
      }
      catch(err){
        console.log(err)
      }
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  html {
    font-size: 62.5%;
  }
  body {
    height: 100%;
    background: linear-gradient(90deg, #BD0F4D 50%, #CB2964 50%);
    padding: 7.5rem 0;
    text-align: center;
  }
  img {
    max-width: 100%;
    height: auto
  }
  .profile-wrapper h1 {
    font-size: 4rem;
    text-transform: uppercase;
    letter-spacing: 1.5rem;
    font-weight: 100;
    color: #fff;
  }
  .profile-picture {
    width: 44%;
    margin: 5rem auto;
    background-color: #CB2964;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
  }
  .social-icons {
    position: absolute;
    top: 50%;
    right: 1.5rem;
    -webkit-transform: translateY(-50%);
    -ms-transform: translateY(-50%);
    transform: translateY(-50%);
  }
  .social-icons a {
    display: block;
    transition: all 0.3s ease;
  }
  .social-icons img {
    height: 4.5rem;
    margin-bottom: 1.5rem;
  }
  nav {
    width: 55%;
    margin: auto;
    margin-top: 6rem;
  }
  ul {
    display: flex;
    justify-content: space-between;
    list-style-type: none;
  }
  li a {
    text-decoration: none;
    text-transform: uppercase;
    color: #fff;
    font-size: 1.6rem;
  }
  li a:hover {
    color: #fff;
    opacity: 0.6;
    text-decoration: none;
  }
  li img {
    height: 10rem;
    margin-top: -3.5rem;
  }

  @media screen and (max-width: 768px) {
    .profile-picture {
      width: 60%;
    }
    nav {
      width: 70%;
    }
  }
</style>
