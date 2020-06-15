<template>
  <div class="container">
   <header>
    <!-- Header content -->
    <h1>10 Best Photo Apps For Incredible iPhone Photography (2020 Edition)</h1>
    <div class="borderline"></div>
    
  </header>

  <main>
    <!-- Main content -->
    <div class="containerItems">
      <p class="containerItems__paragraph1">
        How do you capture more interesting travel photos with your iPhone? How do you avoid taking the same cliché vacation photos that everyone else takes? I recently interviewed Steffen Geldner – a talented iPhone photographer with a passion for travel. In this article, Steffen reveals 7 tips for shooting beautiful travel photos that will preserve the amazing memories of your trip. Read on to discover how to take better travel photos with your iPhone!
      </p>
      <img class="containerItems__img"  v-bind:src="img" alt="image" />
     </div>
     <header class="header2">
       <h2>
         1. Research Your Destination To Find The Best Photo Opportunities
       </h2>
     </header>
     <div class="containerItems1">
      <p class="containerItems1__paragraph2">
      Before your trip, I recommend researching the destination to find the most interesting photo opportunities.
      I always research the location I’m traveling to. I do this extensively and obsessively!
      It’s up to you how much research you do. But you should definitely spend a bit of time looking up some great places to take pictures.
      So, what kind of research can you do?
      First, you could search for photos that other people have taken at the locations you’re planning to visit.
      Search on Instagram or Google to get an idea of the kinds of photos people take there.
      </p>
     </div>

     <header class="header3">
       <h2>
         2. Capture Your Journey To Tell The Complete Story Of Your Travels
       </h2>
     </header>

     <div class="containerItems2">
       <p class="containerItems2__paragraph3">
        Travel photography isn’t just about photographing the destination.
        For a more complete photographic story, capture your journey to and from the location you’re visiting.
        If you’re traveling by plane, try to get a window seat where you have a view of the wing or propeller.
        And of course,you could capture a beautiful aerial view of clouds,mountains, or city lights as you’re flying above.
        Your journey will often involve several different types of transport.And they all offer great photo opportunities.
        Whether you’re traveling by car, taxi, bus, train, boat, or plane, try to capture some interesting photos.
       </p>
     </div>
  </main>

  <aside>
    <!-- Sidebar / Ads -->
    <div class="sidebar">
      <transition name="modal">
        <div  v-if="isOpen" class="overlay">
          <div class="modal">
            <div class="close__btn">
            <button class="close" @click="toggleModal">X</button>  
            </div>
            <div class="step">
              <p>Step 1 of 2</p>
            </div>
            <div class="line">
              <div class="dist" style="background:#AC519C; width:50%; height:0.95px">.
              </div>
            </div>
            <div class="form1">
              <h3 class="form1__text">Enter Your Email To Get <span style="color:green">FREE</span> <br />
              iPhone Photography Email Tips:</h3>
              <form>
                  <input 
                  type="email" 
                  placeholder="Please enter your email here developerstest@iphonephotographyschool.com" 
                  v-model="email"
                  class="emailInput" 
                  required> <br>
                  <span v-if="msg.email">{{msg.email}}</span>
                  <input 
                  type="submit" 
                  value="Send Me The Tips >>"
                  class="submitBtn">
              </form>
            </div>
          </div>
        </div>
    </transition>
    <button class="button__top" @click="toggleModal">
        <div class="button__top__text">Send Me The Tips</div>
    </button>
    
     
    </div>
  </aside>

  </div>
</template>

<script>
const imgLink = require('../assets/img@2x.png')
export default {
  name: 'Ips',
   data(){
        return{
            img: imgLink,
            isOpen: false,
            email: '',
            msg: [],
        }
        
    },
    watch: {
    email(value){
      // binding this to the data value in the email input
      this.email = value;
      this.validateEmail(value);
    }
  },
     methods:{
      toggleModal(){
        this.isOpen = !this.isOpen;
      },
      validateEmail(value){
      if (/^w+([.-]?w+)*@w+([.-]?w+)*(.w{2,3})+$/.test(value))
  {
    this.msg['email'] = '';
  } else{
    this.msg['email'] = 'Please enter a valid email address';
  } 
    }
  } 
 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style  lang="scss" scoped>
*, *::before, *::after{
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
/* Header scss */
$myFont: 'Lato', sans-serif;
$myHeaderColor:#101010;
$myHeaderFontSize: 26px;
$myHeaderWidth: 560px;

/* Paragraph scss */

$myParaFontStyle: normal;
$myParaFontWeight: 300;
$myParaFontSize: 16px;
$myParaLineHeight: 24px;

/* image specs */

$myImageWidth: 560px;
$myImageHeight: 331px;


/* sub-para scss */
$mySubHeaderFontStyle: normal;
$mySubHeaderFontWeight: bold;
$mySubHeaderFontSize: 18px;
$mySubHeaderLineHeight: 22px;
$mySubHeaderColor: #101010;

/* sidebar */
$mySidebarWidth: 270px;
$mySidebarHeight: 640px;
$mySidebarBackground: #F5F5F5;

/* button */
$myButtonWidth:220px;
$myButtonHeight:40px;
$myButtonBackground:linear-gradient(90deg, #AC519C 0.83%, #E5424F 100%);
$myButtonBoxshadow: 0px 3px 10px rgba(104, 104, 104, 0.5);

/* button text */

$myButtonTextFontStyle: normal;
$myButtonTextFontWeight: bold;
$myButtonTextFontSize: 15px;
$myButtonTextLineHeight: 18px;
$myButtonTextTextAlign: center;
$myButtonTextColor: #FFFFFF;
$myButtonHoverBackground: linear-gradient(90deg, #B678AA 1.29%, #E28990 100%);
$myButtonHoverBoxshadow: 0px 3px 10px rgba(104, 104, 104, 0.5);
$myButtonActiveBackground: linear-gradient(90deg, #AC519C 0.74%, #E5424F 100%);
$myButtonActivebox-shadow: 0px 3px 10px rgba(104, 104, 104, 0.5);

$myFormHeaderFontStyle: normal;
$myFormHeaderFontWeight: bold;
$myFormHeaderFontSize: 23px;
$myFormHeaderLineHeight: 28px;
$myFormDisplay: flex;
$myFormAlignItems: center;
$myFormHeaderTextAlign: center;
$myFormHeaderWidth: 440px;
$myFormHeaderHeight: 56px;
$myFormFlexDirection:column;

/*Email Input*/

$myInputWidth:'400px';
$myInputHeight:'54px';
$myInputMargin:'10px auto';

.container {
  display: grid;
  
  grid-template-areas:
    "header header header"
    "nav content side";

  grid-template-columns: 300px 1fr 300px;
  grid-template-rows: auto 1fr auto;
  grid-gap: 10px;
  width: 90%;
  height: 100vh;
}


header {
  grid-area: header;
}

header h1{
  width: 560px;
  height: 62px;
  font-weight: bold;
  font-size: 26px;
  line-height: 31px;
  color: #101010;
  text-align: justify;
  margin: auto;
}

header .borderline{
  border-bottom: 2px solid #AC519C;
  margin: auto;
  margin-top: 30px;
  width: 560px;
}


main {
  grid-area: content;
  margin-right: 10px;
}

 h2{
  text-align: justify;
  font-style: normal;
  font-weight: bold;
  font-size: 18px;
  line-height: 22px;
  color: #101010;
}

.containerItems__paragraph1{
  font-size: $myParaFontSize;
  font-weight: $myParaFontWeight;
  font-style: $myParaFontStyle;
  line-height: $myParaLineHeight;
  margin-bottom: 30px;
  text-align: justify;
}

.containerItems1__paragraph2{
  font-size: $myParaFontSize;
  font-weight: $myParaFontWeight;
  font-style: $myParaFontStyle;
  line-height: $myParaLineHeight;
  margin: 20px 0;
  text-align: justify;
  

} 
.containerItems2__paragraph3{
  font-size: $myParaFontSize;
  font-weight: $myParaFontWeight;
  font-style: $myParaFontStyle;
  line-height: $myParaLineHeight;
  margin-top: 20px;
  text-align: justify;
  

}

.containerItems__img{
  width: $myImageWidth;
  height: $myImageHeight;
  margin-bottom: 10px;
}

aside {
  grid-area: side;
  margin-right: 0.5rem;
  width: $mySidebarWidth;
  height:$mySidebarHeight;
  background: $mySidebarBackground;
}
.button__top{
  width: $myButtonWidth;
  height:$myButtonHeight;
  background: $myButtonBackground;
  border: none;
  box-shadow: $myButtonBoxshadow;
  margin-top: 50px;
  padding:5px
}

.button__top:hover{
  background: $myButtonHoverBackground;
  box-shadow: $myButtonHoverBoxshadow;
}

.button__top:active{
  background: $myButtonActiveBackground;
  box-shadow: $myButtonActivebox-shadow;
}

.button__top__text{
  color: $myButtonTextColor;
  font-size: $myButtonTextFontSize;
  font-style: $myButtonTextFontStyle;
  line-height: $myButtonTextLineHeight;
  text-align: $myButtonTextTextAlign;
  font-weight: $myButtonTextFontWeight;
}

.modal {
  width: 570px;
  height: 310px;
  margin: 0px auto;
  padding: 20px;
  background: #FFFFFF;
  box-shadow: 0px 0px 60px rgba(0, 0, 0, 0.5);
  border-radius: 2px;
  transition: all 0.2s ease-in;
  font-family: Helvetica, Arial, sans-serif;
}
.fadeIn-enter {
  opacity: 0;
}

.fadeIn-leave-active {
  opacity: 0;
  transition: all 0.2s step-end;
}

.fadeIn-enter .modal,
.fadeIn-leave-active.modal {
  transform: scale(1.1);
}


.overlay {
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  background: #00000094;
  opacity: 0.99;
  z-index: 999;
  transition: opacity 0.2s ease;
}

.close{
  font-weight: bold;
  font-size: 38px;
  line-height: 46px;
  color: #464646;
}

.close__btn{
  display: flex;
  align-content: flex-end;
  justify-content: flex-end;
  align-items: flex-end;
  border: none;
}

.step{
  display: flex;
  align-items: center;
  justify-content: center;
  align-self: center;
}
.step p{
  font-style: normal;
  font-weight: 300;
  font-size: 14px;
  line-height: 17px;
  display: flex;
  align-items: center;
  color: #848484;
  margin-bottom:10px;
}
.line{
  border: 3px solid #E5E5E5;
  width: 70%;
  margin: auto;
}


.form1{
   display: $myFormDisplay;
   flex-direction: $myFormFlexDirection ;
   align-items: $myFormAlignItems;
   justify-content: $myFormAlignItems;
}

.form1__text{
  width: $myFormHeaderWidth;
  height: $myFormHeaderHeight;
  text-align: justify;
  line-height: $myFormHeaderLineHeight;
  font-size: $myFormHeaderFontSize;
  font-style: $myFormHeaderFontStyle;
  font-weight: $myFormHeaderFontWeight;
  margin: 10px 0 0 70px;
}

.emailInput, .submitBtn{
  width: 400px;
  height: 54px;
  margin: 10px auto;

}

.emailInput{
  background: #FFFFFF;
  border: 1px solid #E51323;
  box-shadow: inset 0px 1px 5px rgba(142, 142, 142, 0.5);
}

.submitBtn{
  background: linear-gradient(90deg, #AC519C 0.83%, #E5424F 100%);
  box-shadow: 0px 3px 10px rgba(104, 104, 104, 0.5);
  font-weight: bold;
  font-size: 18px;
  line-height: 22px;
  text-align: center;
  color: #FFFFFF;
}

@media (max-width: 768px) {

  
  .container {
    grid-template-areas:
      "header"
      "nav"
      "content"
      "side"
      "footer";

    grid-template-columns: 1fr;
    grid-template-rows:
      auto /* Header */
      minmax(75px, auto) /* Nav */
      1fr /* Content */
      minmax(75px, auto) /* Sidebar */
      auto; /* Footer */
      margin: auto 20px;
  }

 aside {
    width: 340px;
    height: 426px;
    background: #F5F5F5;
    margin: 10px auto;
  }
}

</style>
