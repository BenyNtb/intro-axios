<template>
  <div class="hello">
    <body>
    <div class="root">
      <div class="app-header">
        <input type="checkbox" id="nav-visible" tabindex="-1" />

        <div class="navbar">
          <a href="/" class="navbar-brand">
            <img src="../assets/images/logo.svg" alt="Shortly's logo" class="logo" />
          </a>

          <label for="nav-visible" class="toggle-nav">
            <svg class="icon-menu" width="25" viewBox="0 0 512 512">
              <g>
                <path
                  d="M492,236H20c-11.046,0-20,8.954-20,20c0,11.046,8.954,20,20,20h472c11.046,0,20-8.954,20-20S503.046,236,492,236z"
                ></path>
              </g>
              <g>
                <path
                  d="M492,76H20C8.954,76,0,84.954,0,96s8.954,20,20,20h472c11.046,0,20-8.954,20-20S503.046,76,492,76z"
                ></path>
              </g>
              <g>
                <path
                  d="M492,396H20c-11.046,0-20,8.954-20,20c0,11.046,8.954,20,20,20h472c11.046,0,20-8.954,20-20
                  C512,404.954,503.046,396,492,396z"
                ></path>
              </g>
            </svg>
          </label>

          <nav class="navbar-nav">
            <a href="/">Features</a>
            <a href="/">Pricing</a>
            <a href="/">Resources</a>

            <div class="separator-mobile"></div>

            <button type="button" class="btn btn-small btn-secondary btn-login">Login</button>
            <button type="button" class="btn btn-small btn-primary">Sign Up</button>
          </nav>
        </div>
      </div>

      <div class="intro">
        <div class="content">
          <h1 class="title">More than just shorter links</h1>
          <p class="desc">
            Build your brand’s recognition and get detailed insights on how your links are
            performing.
          </p>
          <button class="btn btn-primary">Get Started</button>
        </div>

        <div class="img-wrapper">
          <img src="../assets/images/illustration-working.svg" alt="" role="presentation" />
        </div>

        <form class="shorten-url-form" @submit.prevent="submit(url)">
          <input type="url" placeholder="Shorten a link here" class="form-control" v-model="url" />
          <button type="submit" class="btn btn-primary">Shorten It!</button>
        </form>
      </div>
          <div class="for-group" v-show="shortUrl">
              <p class="shorten">
                Here is your shorten link: 
                <a :href="shortUrl" class="text-primary">{{shortUrl}}</a>
              </p>
            </div>

      <div class="stats">
        <div class="content">
          <h1 class="title">Advanced Statistics</h1>
          <p class="desc">
            Track how your links are performing across the web with <br />our advanced statistics
            dashboard.
          </p>

          <div class="cards">
            <div class="card">
              <div class="card-icon">
                <img src="../assets/images/icon-brand-recognition.svg" alt="" role="presentation" />
              </div>
              <div class="card-title">Brand Recognition</div>
              <div class="card-body">
                Boost your brand recognition with each click. Generic links don’t mean a thing.
                Branded links help instil confidence in your content.
              </div>
            </div>
            <div class="card">
              <div class="card-icon">
                <img src="../assets/images/icon-detailed-records.svg" alt="" role="presentation" />
              </div>
              <div class="card-title">Detailed Records</div>
              <div class="card-body">
                Gain insights into who is clicking your links. Knowing when and where people engage
                with your content helps inform better decisions.
              </div>
            </div>
            <div class="card">
              <div class="card-icon">
                <img src="../assets/images/icon-fully-customizable.svg" alt="" role="presentation" />
              </div>
              <div class="card-title">Fully Customizable</div>
              <div class="card-body">
                Improve brand awareness and content discoverability through customizable links,
                supercharging audience engagement.
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="start-now">
        <h1 class="title">Boost your links today</h1>
        <button class="btn btn-primary">Get Started</button>
      </div>

      <div class="app-footer">
        <div class="content">
          <svg width="121" height="33" alt="Shortly's logo" class="logo">
            <path
              fill="white"
              d="M16.715 7.932c-.068-.09-.306-.26-.714-.51s-.918-.51-1.53-.782-1.281-.51-2.006-.714a8.005 8.005 0 00-2.176-.306c-1.995 0-2.992.669-2.992 2.006 0 .408.107.748.323 1.02.215.272.532.516.952.731.419.215.946.414 1.58.595l1.406.393.805.219c1.156.317 2.198.663 3.128 1.037.929.374 1.717.839 2.363 1.394a5.647 5.647 0 011.496 2.023c.35.793.527 1.745.527 2.856 0 1.36-.255 2.51-.765 3.451-.51.94-1.185 1.7-2.023 2.278-.84.578-1.802.997-2.89 1.258-1.088.26-2.21.391-3.366.391a19.68 19.68 0 01-5.44-.799c-.884-.26-1.74-.572-2.567-.935A14.358 14.358 0 01.53 22.28l2.448-4.862c.09.113.385.329.884.646.498.317 1.116.635 1.853.952.736.317 1.558.6 2.465.85.906.25 1.824.374 2.754.374 1.972 0 2.958-.6 2.958-1.802 0-.453-.148-.827-.442-1.122-.295-.295-.703-.561-1.224-.799a12.455 12.455 0 00-1.504-.56l-1.702-.495-.976-.288c-1.111-.34-2.074-.708-2.89-1.105-.816-.397-1.49-.856-2.023-1.377a5.003 5.003 0 01-1.19-1.802c-.261-.68-.391-1.473-.391-2.38 0-1.27.238-2.391.714-3.366a7.266 7.266 0 011.938-2.465 8.435 8.435 0 012.839-1.513c1.076-.34 2.215-.51 3.417-.51.838 0 1.666.08 2.482.238.816.159 1.598.363 2.346.612.748.25 1.445.533 2.09.85.647.317 1.242.635 1.786.952l-2.448 4.624zM40.139 25h-5.44V14.97c0-1.156-.227-2.006-.68-2.55-.454-.544-1.077-.816-1.87-.816-.318 0-.663.074-1.037.221a4.173 4.173 0 00-1.088.646 5.827 5.827 0 00-.97 1.003 4.4 4.4 0 00-.68 1.292V25h-5.44V.18h5.44v9.962a6.786 6.786 0 012.602-2.465c1.076-.578 2.26-.867 3.553-.867 1.201 0 2.17.21 2.907.629.736.42 1.303.952 1.7 1.598.396.646.663 1.371.799 2.176.136.805.204 1.592.204 2.363V25zm12.34.34c-1.519 0-2.873-.25-4.063-.748-1.19-.499-2.193-1.173-3.01-2.023a8.54 8.54 0 01-1.852-2.958 9.97 9.97 0 01-.63-3.519c0-1.224.21-2.397.63-3.519a8.54 8.54 0 011.853-2.958c.816-.85 1.819-1.53 3.009-2.04s2.544-.765 4.063-.765c1.519 0 2.867.255 4.046.765 1.179.51 2.176 1.19 2.992 2.04a8.754 8.754 0 011.87 2.958 9.736 9.736 0 01.646 3.519 9.97 9.97 0 01-.63 3.519 8.54 8.54 0 01-1.852 2.958c-.816.85-1.82 1.524-3.01 2.023-1.19.499-2.543.748-4.062.748zM48.5 16.092c0 1.405.374 2.533 1.122 3.383.748.85 1.7 1.275 2.856 1.275a3.59 3.59 0 001.564-.34c.476-.227.89-.544 1.24-.952a4.57 4.57 0 00.834-1.479 5.632 5.632 0 00.306-1.887c0-1.405-.374-2.533-1.122-3.383-.748-.85-1.689-1.275-2.822-1.275a3.702 3.702 0 00-2.84 1.292 4.57 4.57 0 00-.832 1.479 5.632 5.632 0 00-.306 1.887zm27.776-4.284c-1.315.023-2.505.238-3.57.646-1.065.408-1.836 1.02-2.312 1.836V25h-5.44V7.15h4.998v3.604c.612-1.201 1.4-2.142 2.363-2.822.963-.68 1.989-1.031 3.077-1.054h.544c.113 0 .227.011.34.034v4.896zm14.074 12.24a21.71 21.71 0 01-2.567.884c-.963.272-1.932.408-2.907.408-.68 0-1.32-.085-1.92-.255a4.286 4.286 0 01-1.582-.816c-.453-.374-.81-.867-1.07-1.479-.262-.612-.392-1.349-.392-2.21v-9.316h-2.278V7.15h2.278V1.472h5.44V7.15h3.638v4.114h-3.638v7.446c0 .59.147 1.014.442 1.275.295.26.669.391 1.122.391.408 0 .827-.068 1.258-.204.43-.136.805-.283 1.122-.442l1.054 4.318zM92.627.18h5.44v18.462c0 1.36.578 2.04 1.734 2.04.272 0 .572-.04.901-.119.329-.08.63-.198.901-.357l.714 4.08c-.68.317-1.462.567-2.346.748-.884.181-1.711.272-2.482.272-1.564 0-2.765-.408-3.604-1.224-.839-.816-1.258-1.995-1.258-3.536V.18zm11.456 27.506c.454.159.879.272 1.275.34a6.4 6.4 0 001.071.102c.658 0 1.168-.227 1.53-.68.363-.453.692-1.27.986-2.448l-6.8-17.85h5.61l4.148 13.192 3.57-13.192h5.1l-6.8 20.74a7.106 7.106 0 01-2.55 3.587c-1.224.918-2.674 1.377-4.352 1.377a8.17 8.17 0 01-1.377-.119 7.516 7.516 0 01-1.41-.391v-4.658z"
            />
          </svg>

          <div class="company-links">
            <div class="group">
              <h5 class="title">Features</h5>
              <div class="links">
                <a href="">Link Shortening</a>
                <a href="">Branded Links</a>
                <a href="">Analytics</a>
              </div>
            </div>
            <div class="group">
              <h5 class="title">Resources</h5>
              <div class="links">
                <a href="">Blog</a>
                <a href="">Developers</a>
                <a href="">Support</a>
              </div>
            </div>
            <div class="group">
              <h5 class="title">Company</h5>
              <div class="links">
                <a href="#">About</a>
                <a href="#">Our Team</a>
                <a href="#">Careers</a>
                <a href="#">Contact</a>
              </div>
            </div>
          </div>

          <div class="social-links">
            <a href="#">
              <img src="../assets/images/icon-facebook.svg" alt="Facebook page" />
            </a>
            <a href="#">
              <img src="../assets/images/icon-twitter.svg" alt="Twitter page" />
            </a>
            <a href="#">
              <img src="../assets/images/icon-pinterest.svg" alt="Pinterest page" />
            </a>
            <a href="#">
              <img src="../assets/images/icon-instagram.svg" alt="Instagram page" />
            </a>
          </div>
        </div>
      </div>
    </div>
  </body>
  </div>
    <!-- <div class="row">
      <div class="col col-12 offset-0 mt-2">
        <h1 class="jumbotron text-center text-white bg-primary">Create Click-Worthy Links</h1>
      </div>
    <div class="col col-8 align-middle mt-5 offset-2">
      <div class="card">
        <div class="card-body">
          <form @submit.prevent="submit(url)">
            <div class="form-group">
              <label for="url">Enter Url</label>
              <textarea type="url" class="form-control" v-model="url" style="height:150px" />
            </div>
            <div class="for-group" v-show="shortUrl">
              <p>
                Short URL: :
                <a :href="shortUrl" class="text-primary">{{shortUrl}}</a>
              </p>
            </div>
            <div class="form-group">
              <button class="btn btn-primary" type="submit">Shorten URl</button>
            </div>
          </form>
        </div>
      </div>
    </div>
    </div> -->
 
  <!-- </div> -->
</template>

<script>
import axios from 'axios'
export default {
  data: () => {
    return {
      url: "",
      shortUrl: "",
    }
  },

  methods: {
    submit(url) {
        axios.get('https://api.shrtco.de/v2/shorten?url='+url)
        .then(response => this.shortUrl = response.data.result.full_short_link)
    },
  }
};
// export default {
//   name: 'HelloWorld',
//   data(){
//     return{
//       link: null,
//     }
//   },
//   props: {
//     msg: String
//   },
//   mounted () {
//     axios
//     .get('https://app.shrtco.de/')
//     .then((response) => {
//       this.link = response;
//     console.log(this.link)
//   });
//   },
// }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.for-group {
    /* display: block; */
    font-size: 2em;
    /* padding: 18px 40px; */
    
}
.shorten {
  /* border: 2px solid green */
  box-sizing: content-box;
width: 100%;
border: solid #5B6DCD 10px;
padding: 5px;
}
.btn {
  font-family: sans-serif;
  border-radius: 30px;
  padding: 18px 40px;
  border: none;
  cursor: pointer;
  font-size: 20px;
  line-height: 1;
}

.btn-small {
  line-height: 1.5;
  font-size: 16px;
  padding: 8px 25px;
}

.btn-primary {
  background-color: hsla(180, 66%, 49%, 0.6);
  color: white;
}

.btn-secondary {
  background-color: hsla(180, 66%, 49%, 0.6);
  color: var(--grayish-violet);
}

/* .btn-secondary:active {
  color: var(--dark-violet);
}

.btn-primary:active {
  background-color: hsla(180, 66%, 49%, 0.6);
} */

.btn-primary:focus,
.btn-secondary:focus {
  outline: none;
}

/* #endregion */

/* #region App Header */

.app-header {
  height: 160px;
  grid-column: 1/4;

  display: grid;
  grid-template-columns: inherit;
}

.app-header .navbar {
  grid-row: 1;
  grid-column: 2/3;

  display: flex;
  align-items: center;
}

.app-header .navbar-brand {
  line-height: 0;
  margin-right: 45px;
}

.app-header .toggle-nav {
  display: none;
  line-height: 0;
  cursor: pointer;
}

.app-header .toggle-nav .icon-menu {
  fill: var(--gray);
}

.app-header .navbar-nav {
  display: flex;
  align-items: center;
  flex: 1;
  font-size: 14px;
}

.app-header .navbar-nav a {
  margin-right: 30px;
  text-decoration: none;
  color: var(--grayish-violet);
}

.app-header .navbar-nav a:active {
  color: var(--dark-violet);
}

.app-header .navbar .actions {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: flex-end;
}

.app-header .btn-login {
  margin-left: auto;
}

#nav-visible {
  position: absolute;
  left: -100px;
  top: 0;
  opacity: 0;
  pointer-events: none;
}

.separator-mobile {
  height: 0;
}

@media (max-width: 1439px) {
  .app-header {
    height: 90px;
  }

  .app-header .toggle-nav {
    display: block;
  }

  .app-header .navbar {
    justify-content: space-between;
  }

  .app-header .navbar-nav {
    position: absolute;
    top: 90px;
    left: 15px;
    right: 15px;
    background-color: var(--dark-violet);
    display: flex;
    flex-direction: column;
    padding: 20px 24px 40px;
    border-radius: 9px;
  }
  .app-header .navbar-nav a {
    padding: 15px 0;
    margin-right: 0;
    font-size: 18px;
    color: white;
  }

  .app-header .navbar-nav a:active {
    color: var(--gray);
  }

  .app-header .btn {
    align-self: stretch;
    font-weight: var(--font-weight-bold);
    font-size: 18px;
  }

  .app-header .btn-login {
    margin-left: 0;
    color: white;
    background-color: transparent;
    margin-bottom: 15px;
  }

  .app-header .btn-login:active {
    color: var(--gray);
  }

  .separator-mobile {
    background: var(--gray);
    height: 1px;
    align-self: stretch;
    margin: 20px 0 30px;
  }

  #nav-visible:not(:checked) ~ .navbar .navbar-nav {
    display: none;
  }
}

/* #endregion */

/* #region Intro  */

.intro {
  grid-column: 1/4;

  display: grid;
  grid-template-columns: inherit;

  overflow: hidden;
}

.intro .img-wrapper {
  grid-column: 2/4;
  justify-self: end;
  grid-row: 1;
}

.intro .content {
  grid-column: 2/3;
  grid-row: 1;

  display: flex;
  flex-direction: column;
  align-items: flex-start;

  max-width: 60%;
}

.intro .content > * {
  margin-bottom: 40px;
}

.intro .content .btn {
  padding: 19px 40px;
}

.intro .title {
  font-size: 80px;
  line-height: 1.1;
}

.intro .desc {
  display: block;
  max-width: 70%;
  color: var(--grayish-violet);
}

.intro .shorten-url-form {
  grid-row: 2;
  grid-column: 2/3;

  display: flex;
  align-items: center;
  z-index: 1;

  margin-top: 67px;
  padding: 50px;

  background: var(--dark-violet) url(../assets/images/bg-shorten-desktop.svg) no-repeat;
  background-size: cover;
  border-radius: 9px;
}

.intro .shorten-url-form input {
  flex: 1;
  font-size: 20px;
  padding: 17px 32px;
  border-radius: 4px;
  margin-right: 25px;
  border-radius: 9px;
  border: none;
}

.intro .shorten-url-form .btn {
  padding-top: 22px;
  padding-bottom: 22px;
  border-radius: 9px;
}

@media (max-width: 1439px) {
  .intro .content {
    grid-row: 2;
    max-width: none;
    align-items: center;
  }

  .intro .title {
    font-size: 42px;
    text-align: center;
    margin-bottom: 25px;
  }

  .intro .desc {
    color: var(--grayish-violet);
    text-align: center;
    max-width: none;
    margin-bottom: 35px;
  }

  .intro .img-wrapper {
    width: 530px;
    padding-left: 15px;
  }
  .intro img {
    margin-bottom: 40px;
    object-position: 0px 0;
    width: 100%;
  }

  .intro .shorten-url-form {
    grid-row: 3;
    flex-direction: column;
    align-items: stretch;
  }

  .intro .shorten-url-form {
    background: var(--dark-violet) url(../assets/images/bg-shorten-mobile.svg) no-repeat;
    background-position: right top;
    padding: 25px;
  }

  .intro .shorten-url-form input {
    width: 100%;
    margin-bottom: 15px;
    padding: 12px 23px;
    font-size: 16px;
  }

  .intro .shorten-url-form .btn {
    padding: 16px 40px;
  }
}

/* #endregion */

/* #region Stats */

.stats {
  grid-column: 1/4;

  display: grid;
  grid-template-columns: inherit;

  background-color: #f0f1f6;
  padding: 210px 0 120px;
  margin-top: -12px;
}

.stats .content {
  grid-column: 2/3;
}

.stats .title {
  font-size: 40px;
  text-align: center;
  margin-bottom: 35px;
}

.stats .desc {
  font-size: 18px;
  color: var(--grayish-violet);
  text-align: center;
  margin-bottom: 100px;
}

.cards {
  display: flex;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  column-gap: 30px;
  align-items: start;
}

.cards .card {
  border-radius: 6px;
  background-color: white;
  display: flex;
  flex-direction: column;
  padding: 80px 32px 40px;
  position: relative;
}

.card .card-icon {
  width: 90px;
  height: 90px;
  border-radius: 50%;
  background-color: #3D2F52;
  display: flex;
  justify-content: center;
  align-items: center;
  line-height: 0;
  position: absolute;
  top: 0;
  left: 0;
  transform: translate(32px, -50%);
}

.card .card-title {
  font-size: 21px;
  font-weight: 700;
  margin-bottom: 20px;
}

.card .card-body {
  color: var(--grayish-violet);
  font-size: 15px;
}

.card:not(:last-child)::after {
  position: absolute;
  content: '';
  background-color: var(--cyan);
  width: 8px;
  height: 47px;
  left: 50%;
  top: 100%;
  transform: translateX(-50%);
}

.card:nth-child(2) {
  margin-top: 45px;
}

.card:nth-child(3) {
  margin-top: 90px;
}
.card:nth-child(1)::after {
  top: 150px;
  right: -19px;
  left: auto;
  transform: rotateZ(90deg);
  height: 30px;
}

.card:nth-child(2)::after {
  top: 105px;
  right: -19px;
  left: auto;
  transform: rotateZ(90deg);
  height: 30px;
}

@media (max-width: 1439px) {
  .stats .title {
    font-size: 28px;
  }

  .stats .desc {
    line-height: 1.8;
  }

  .stats .desc br {
    display: none;
  }

  .cards {
    grid-template-columns: 1fr;
    row-gap: 92px;
  }

  .cards .card {
    text-align: center;
  }

  .card:not(:last-child)::after {
    position: absolute;
    content: '';
    background-color: var(--cyan);
    width: 8px;
    height: 47px;
    left: 50%;
    top: 100%;
    right: auto;
    transform: translateX(-50%);
  }

  .card .card-icon {
    left: 50%;
    transform: translate(-50%, -50%);
  }

  .card .card-body {
    font-size: 15px;
    line-height: 1.8;
  }

  .card:nth-child(2) {
    margin-top: 0;
  }

  .card:nth-child(3) {
    margin-top: 0px;
  }
}

/* #endregion */

/* #region Start Now */

.start-now {
  grid-column: 1/4;
  background: #3D2F52 url(../assets/images/bg-boost-desktop.svg) 0 0 no-repeat scroll;
  background-size: cover;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  padding: 40px 15px 60px;
}

.start-now .title {
  font-size: 40px;
  margin-bottom: 25px;
  color: white;
}

@media (max-width: 1439px) {
  .start-now {
    background-image: url(../assets/images//bg-boost-mobile.svg);
  }

  .start-now .title {
    font-size: 28px;
  }
}

/* #endregion */

/* #region App Footer */

.app-footer {
  grid-column: 1/4;

  display: grid;
  grid-template-columns: inherit;
  padding: 70px 15px 75px;

  background-color: #232027;
}

.app-footer .content {
  grid-column: 2/3;
  display: grid;
  grid-template-columns: 1fr repeat(2, auto);
  align-items: start;
}

.app-footer .logo {
  grid-column: 1;
}

.app-footer .company-links {
  grid-column: 2;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  column-gap: 105px;
  padding: 0 15px;
}

.company-links .title {
  color: white;
  margin-bottom: 30px;
  font-size: 16px;
}

.company-links .links {
  display: flex;
  align-items: flex-start;
  flex-direction: column;
}

.company-links a {
  text-decoration: none;
  color: var(--gray);
  font-size: 15px;
  line-height: 1.8;
}

.app-footer .social-links {
  grid-column: 3;
  display: grid;
  grid-auto-flow: column;
  align-items: center;
  column-gap: 25px;
}

.social-links a {
  line-height: 0;
  text-decoration: none;
}

@media (max-width: 1439px) {
  .app-footer {
    grid-template-columns: 1fr;
  }

  .app-footer .logo {
    margin-bottom: 54px;
  }

  .app-footer .content {
    grid-column: 1;
    justify-items: center;
    grid-auto-flow: row;
    grid-template-columns: 1fr;
  }

  .app-footer .company-links {
    grid-row: 2;
    grid-template-columns: 1fr;
    grid-auto-flow: row;
    grid-column: 1;
  }

  .company-links .group {
    margin-bottom: 40px;
  }

  .company-links .title {
    margin-bottom: 30px;
    text-align: center;
  }

  .company-links .links {
    align-items: center;
  }

  .company-links a {
    line-height: 2;
  }

  .app-footer .social-links {
    grid-row: 3;
    grid-column: 1;
  }
}
</style>
