<script>
import arrows from '../assets/arrows.png'
    import logo from '../assets/svelte.png'
    import react from '../assets/react.png'
    import html from '../assets/html.svg'
    import css from '../assets/css.svg'
    import js from '../assets/javascript.svg'
    import tensor from '../assets/tensorflow.png'
    import python from '../assets/python.svg'
    import macbook from '../assets/macbook.png'
    import iphone from '../assets/iphonedis.png'
    import tablet from '../assets/tablet.png'
    import driphone from '../assets/drphone.png'
    import drmacbook from '../assets/drmacbook.png'
    import drtablet from '../assets/drtablet.png'
  
    let m = { x: 0, y: 0 };
    
    let navleft = 0;
    let check = true;
    let arrowrot = 0;
    let y = 1;
    let y2 = 0;
    let x = 0;
    let worksA = 0;
    let scrollable = true;
    export let page ;
    
    function handlework(){
      if(worksA < 100){
        worksA= worksA + 2.5;
        requestAnimationFrame(handlework);
      }
    }
    function handlework2(){
      if(worksA < 200){
        worksA= worksA + 2.5;
        requestAnimationFrame(handlework2);
      }
    }
    function handlework3(){
      if(worksA > 0){
        worksA= worksA - 2.5;
        requestAnimationFrame(handlework3);
      }
    }
    function handlework4(){
      if(worksA > 100){
        worksA= worksA - 2.5;
        requestAnimationFrame(handlework4);
      }
    }
    function handleWheel(e){
     if(e.deltaX > 0){
       x=x+.1;
     }else{
       x=x-.1;
     }
    
  
    
    }
    const wheel = (node, options) => {
          let { scrollable } = options;
          
          const handler = e => {
              if (!scrollable) e.preventDefault();
          };
          
          node.addEventListener('wheel', handler, { passive: false });
          
          return {
              update(options) {
                  scrollable = options.scrollable;
              },
              destroy() {
                  node.removeEventListener('wheel', handler, { passive: false });
              }
          };
    };
    function animate(){
      
      requestAnimationFrame(animate);
      
      
      
    }
    animate();
      function handleMousemove(event) {
          m.x = event.clientX;
          m.y = event.clientY;
      
    }
    function handlecardclick(){
      console.log("clicked")
      window.scrollTo(0, 0);
      page = 1; 
    }
    
    function handlenav(){
      if(check){
        arrowrot = arrowrot + 25.71;
        navleft = navleft + 1;
        if(navleft <= 6){
          requestAnimationFrame(handlenav);
        }else{
          check= false;
        }
      }else{
        navleft = navleft - 1;
        arrowrot = arrowrot - 25.71;
        if(navleft > 0){
          requestAnimationFrame(handlenav);
        }else{
          check= true;
        }
      }
  
      
    }
    function handleback(){
      page = 0;
    }
    let pro = 1.5;
    let proopacity = 1;
    let proX= 800;
    function scrollproject(e){
      console.log("here");
      console.log(y);
      console.log("here");
      e.preventDefault;
      if(e.deltaY > 0){
        if(pro > .7){
        pro= pro -.007;
        proX = proX -5;
        proopacity = proopacity - .01;
      }
     }else{
      if(pro < 1.5){
        pro= pro +.007;
        proX = proX +5;
  
        proopacity = proopacity + .2;
      }
     }
     
      
    }
    
  </script>
  
  <main  on:mousemove={handleMousemove}>
    
<div id="five" class="transtion"></div>
<div id="six" class="transtion"></div>
<div id="seven" class="transtion"></div>
<div id="eight" class="transtion">
  <svg xmlns="http://www.w3.org/2000/svg" width="524" height="628" viewBox="0 0 524 628" fill="none">
    <path id="load1" d="M51 214V229H66H90H105V214V110.62L324.384 104.995L341.056 104.568L338.871 88.0344C337.565 78.1555 334.45 67.1631 323.54 59.4798C314.127 52.8509 301.003 50.366 285.247 49.0519L284.624 49H284H66H51V64V214ZM89.6155 81.0049L81 81.2258V79H167.808L89.6155 81.0049ZM51 448V455.658L57.2024 460.149L115.202 502.149L139 519.382V490V335H331.949C346.815 335.099 359.703 333.273 373.662 327.893C387.241 322.66 401.212 314.296 418.522 302.344L419.919 301.38L421.064 300.128C431.625 288.591 440.844 277.635 446.62 263.725C452.5 249.565 454.276 233.763 452.97 213.056L452.766 209.81L451.235 206.94C444.215 193.782 437.507 182.952 428.385 173.222C419.223 163.449 408.255 155.446 393.446 146.978L379.524 139.018L372.51 153.44C347.467 204.939 328.797 229.257 290.156 265H66H51V280V448ZM296 295H301.816L306.112 291.079C346.263 254.431 367.663 228.629 392.035 181.452C398.011 185.618 402.592 189.572 406.499 193.74C412.442 200.079 417.359 207.472 423.206 218.171C423.949 234.335 422.199 244.308 418.914 252.219C415.447 260.569 409.753 267.969 400.077 278.62C384.046 289.617 372.785 296.081 362.874 299.9C353.074 303.677 344.023 305.084 332.105 305L332.052 305H332H124H109V320V460.618L81 440.342V295H296ZM308 375H264.217L298.802 401.849L450.802 519.849L475 538.634V508V478V470.873L469.475 466.371L361.475 378.371L357.337 375H352H308ZM158 145H143V160V214V229H158H264H271.127L275.629 223.475L319.629 169.475L339.571 145H308H158ZM173 199V175H276.429L256.873 199H173ZM194.973 377.98L171 360.084V390V596.633L15 470.827V64V15H262.903L327.779 24.5405C345.698 32.6601 355.936 41.4003 363.576 52.1467C371.947 63.9209 377.805 78.8466 385.902 101.124L387.807 106.364L392.671 109.088L441.674 136.529C441.973 136.768 442.362 137.083 442.832 137.473C444.159 138.573 446.122 140.26 448.508 142.491C453.298 146.966 459.706 153.547 466.099 161.88C479.02 178.724 491 201.559 491 228C491 253.632 474.376 283.159 455.128 308.082C445.812 320.145 436.46 330.4 429.426 337.645C425.917 341.258 423.008 344.1 420.996 346.019C419.991 346.978 419.212 347.705 418.697 348.181C418.439 348.419 418.247 348.595 418.127 348.705C418.066 348.76 418.023 348.798 417.999 348.82L417.981 348.836L417.977 348.84L417.976 348.841L417.975 348.842L405.673 359.882L417.864 371.057L509 454.599V549.073L469.383 582.821L194.973 377.98Z" stroke="#00FFD1" stroke-width="10"/>
    <path  id="load2" d="M56 214V224H66H90H100V214V105.747L324.256 99.9967L335.371 99.7117L333.914 88.6896C332.677 79.3329 329.874 70.0553 320.661 63.5678C312.447 57.7833 300.548 55.3454 284.831 54.0346L284.416 54H284H66H56V64V214ZM89.7437 86.0033L80 86.2531V96V204H76V74H283.579C298.849 75.3026 305.758 77.5339 309.146 79.9199C309.347 80.0617 309.542 80.2085 309.732 80.3626L89.7437 86.0033ZM56 448V453.105L60.1349 456.099L118.135 498.099L134 509.588V490V330H331.966C346.344 330.097 358.595 328.341 371.864 323.228C384.879 318.212 398.459 310.12 415.682 298.229L416.613 297.586L417.376 296.752C427.906 285.249 436.589 274.845 442.003 261.807C447.486 248.603 449.258 233.641 447.98 213.371L447.844 211.207L446.823 209.293C439.882 196.281 433.416 185.899 424.737 176.641C416.032 167.356 405.518 159.641 390.964 151.319L381.683 146.012L377.007 155.627C351.365 208.356 332.16 233.128 292.11 270H66H56V280V448ZM296 290H299.878L302.742 287.386C343.874 249.842 364.97 224.001 390.138 174.174C398.712 179.674 404.949 184.776 410.147 190.32C416.692 197.302 421.967 205.38 428.144 216.785C429.046 234.063 427.274 245.126 423.532 254.137C419.666 263.448 413.349 271.477 403.386 282.413C387.005 293.676 375.233 300.496 364.672 304.566C354.176 308.611 344.483 310.087 332.07 310L332.035 310H332H124H114V320V470.412L76 442.895V290H296ZM308 380H278.811L301.868 397.899L453.868 515.899L470 528.423V508V478V473.249L466.317 470.248L358.317 382.248L355.558 380H352H308ZM158 150H148V160V214V224H158H264H268.751L271.752 220.317L315.752 166.317L329.047 150H308H158ZM450 487.577L337.189 400H348.442L450 482.751V487.577ZM168 204V170H286.953L259.249 204H168ZM191.982 381.986L176 370.056V390V607.089L10 473.218V64V10H263.269L329.196 19.6952C348.167 28.1916 359.318 37.5276 367.651 49.2496C376.479 61.6675 382.544 77.2469 390.602 99.416L391.871 102.909L395.114 104.725L444.467 132.363C444.814 132.636 445.341 133.058 446.024 133.624C447.419 134.781 449.456 136.533 451.922 138.837C456.865 143.457 463.471 150.24 470.066 158.837C483.347 176.149 496 200.04 496 228C496 255.421 478.417 286.106 459.085 311.138C449.625 323.388 440.14 333.788 433.013 341.128C429.455 344.792 426.5 347.678 424.448 349.636C423.423 350.615 422.624 351.36 422.09 351.854C421.823 352.1 421.622 352.284 421.492 352.402C421.427 352.461 421.38 352.504 421.352 352.53L421.322 352.556L421.321 352.558L421.319 352.56L421.318 352.56L413.115 359.921L421.243 367.372L514 452.399V551.382L469.589 589.214L191.982 381.986Z" stroke="#00A3FF" stroke-width="10"/>
    <path id="load3" d="M61 214V219H66H90H95V214V100.873L324.128 94.9984L329.685 94.8559L328.957 89.3448C327.789 80.5103 325.297 72.9476 317.782 67.6558C310.767 62.7156 300.092 60.3247 284.416 59.0173L284.208 59H284H66H61V64V214ZM89.8718 91.0016L85 91.1266V96V209H71V69H283.791C299.254 70.3038 307.428 72.5947 312.025 75.8319C315.043 77.9577 316.854 80.7462 318.012 85.1519L89.8718 91.0016ZM61 448V450.553L63.0675 452.05L121.067 494.05L129 499.794V490V325H331.983C345.873 325.096 357.488 323.41 370.066 318.562C382.518 313.764 395.707 305.944 412.841 294.115L413.306 293.793L413.688 293.376C424.186 281.907 432.333 272.055 437.385 259.889C442.471 247.642 444.241 233.519 442.99 213.685L442.922 212.603L442.412 211.647C435.548 198.779 429.326 188.846 421.09 180.061C412.841 171.262 402.78 163.835 388.482 155.659L383.841 153.006L381.503 157.813C355.265 211.769 335.52 236.997 294.058 275H66H61V280V448ZM296 285H297.939L299.371 283.693C341.407 245.324 362.132 219.523 388.117 167.036C399.396 173.82 407.306 179.979 413.794 186.9C420.956 194.54 426.585 203.315 433.075 215.395C434.137 233.75 432.36 245.916 428.15 256.054C423.876 266.346 416.92 275.009 406.693 286.207C389.974 297.726 377.69 304.907 366.47 309.231C355.278 313.544 344.943 315.09 332.035 315L332.017 315H332H124H119V320V480.206L71 445.447V285H296ZM308 385H293.406L304.934 393.95L456.934 511.95L465 518.211V508V478V475.624L463.158 474.124L355.158 386.124L353.779 385H352H308ZM158 155H153V160V214V219H158H264H266.376L267.876 217.158L311.876 163.158L318.524 155H308H158ZM455 497.789L322.594 395H350.221L455 480.376V497.789ZM163 165H297.476L261.624 209H163V165ZM188.991 385.993L181 380.028V390V617.544L5 475.609V64V5H263.634L330.603 14.8483C350.616 23.7135 362.691 33.6439 371.726 46.3525C381.012 59.414 387.283 75.6471 395.301 97.708L395.936 99.4545L397.557 100.363L447.244 128.187C447.323 128.249 447.421 128.325 447.537 128.416C447.915 128.714 448.484 129.169 449.215 129.775C450.678 130.988 452.791 132.805 455.336 135.184C460.432 139.947 467.235 146.932 474.033 155.793C487.673 173.575 501 198.52 501 228C501 257.211 482.459 289.053 463.043 314.194C453.437 326.632 443.82 337.175 436.6 344.611C432.993 348.326 429.992 351.257 427.9 353.254C426.854 354.252 426.036 355.016 425.483 355.526C425.207 355.782 424.997 355.974 424.858 356.1C424.789 356.163 424.737 356.21 424.704 356.239L424.668 356.272L424.661 356.278L424.66 356.279L424.66 356.279L420.558 359.961L424.621 363.686L519 450.199V553.691L469.794 595.607L188.991 385.993Z" stroke="#AD00FF" stroke-width="10"/>
    </svg>
</div>
<div on:click={handleback} id="backbutton">
  <img src={arrows}  />
  </div>
<div class="navbar" style={` transform: translateX(${navleft}vw);`}>
    <div class="cover"></div>
      <div on:click={handlenav} class="navbar-open">
      <img style={` transform: rotate(${arrowrot}deg);`} src={arrows} alt="failed" />
      </div>
      <div class="navbar-icons">
      <div class=navbar-icon>
        <img src={arrows} alt="failed" />
      </div>
      <div class=navbar-icon>
        <img src={arrows} alt="failed" />
      </div>
      <div class=navbar-icon>
        <img src={arrows} alt="failed" />
      </div>
      <div class=navbar-icon>
        <img src={arrows} alt="failed" />
      </div>
    </div>
    <div class=navbar-icon>
      <img src={arrows} alt="failed" />
    </div>
    </div>
<div on:wheel={scrollproject} class="box">
  <h3 id="bgcasestudy" >CASE STUDY</h3>
  <div class="devices">
    <div>
      <div class="animated-title2">
        <div class="text-top">
          <div>
            <img style={`transform: translateX(${(m.x*-3)/100}px)
             translateY(${(m.y*3)/100}px)
              scale(1.5, .8);`} id="tablet" src={drtablet} />

          </div>
        </div>
        
      </div>
    </div>
    <div>
      <div class="animated-title3">
        <div class="text-top">


          <div>
            <img style={`transform: translateX(${(m.x)/100}px)
            translateY(${(m.y*-1)/100}px)
            scale(2.5, 2.0);`} id="macbook" src={drmacbook} />
          </div>
        </div>
        
      </div>
   
    
    </div>
    <div>
      <div class="animated-title2">
        <div class="text-top">
          <div>
            <img style={`transform: translateX(${(m.x*-4)/100}px)
            translateY(${(m.y*4)/100}px)
            scale(1, 1.1);`} id="phone" src={driphone} />


          </div>
        </div>
        
      </div>
    
    </div>
  </div>
  
  <h1>Digit Recognizer</h1>
  
  <div class="coverprojecttitle"></div>
  <div class="buttonsTop">
    <button><a href="https://handwritting-bc813.web.app/">Project</a></button>
    <button>Code</button>
    </div>
  <div  class="seperator3"></div>
  {#if y > 300}
  <h2 >Description</h2>
  <div class="coverprojecth2"></div>
  {:else}
  <h2 class="transparent">Description</h2>
  <div class="coverprojecth2temp"></div>
  {/if}
  
  <p>This handwritten digit recognizer can be 
    used to recognize digits that are written by hand. 
    It is based on the MNIST dataset, which is a dataset of handwritten 
    digits that has been widely used for training and testing machine 
    learning models. The model that is used for recognition is a 
    convolutional neural network, which is a type of neural network
     that is well-suited for image recognition tasks.</p>
     <div  class="seperator3"></div>
     {#if y > 900}
     
     <h2 >Technologies</h2>
     <div class="coverprojecth2"></div>
     {:else}
    
     <h2  class="transparent">Technologies</h2>
     <div class="coverprojecth2temp"></div>
     {/if}
  <div class="coverprojecth2"></div>
  <div class="technologies">
    <img src={html}/>
    <img src={css}/>
    <img  class="imgnobg" src={js}/>
    <img  src={react}/>
    <img src={python}/>
    <img src={tensor}/>
  </div>
  <div  class="seperator3"></div>
  {#if y > 1400}
  <h2>Design</h2>
  <div class="coverprojecth2"></div>
  {:else}
  <h2 class="transparent">Design</h2>
  <div class="coverprojecth2temp"></div>
  {/if}
  <div class="coverprojecth2"></div>
  <div class="desgin">
    <div class="colorsingle">
      <p>#0000000</p>
      <div id="black" ></div>
    </div>
    <div class="colorsingle">
      <p>#FFFFFF</p>
      <div ></div>
    </div>
    <div class="colorsingle">
      <p>#D3D3D3</p>
      <div id="grey"></div>
    </div>
    <div class="colorsingle">
      <p>#FF0000</p>
      <div id="red" ></div>
    </div>
   
  </div>
  <div  class="seperator3"></div>
  
    
    
    
</div>
  
  </main>
  <svelte:window use:wheel={{scrollable}} bind:scrollY={y} />
  
  <style lang="scss">
    .transparent{
      color: transparent;
    }
    #black{
      background-color: #000000;

    }
    #grey{
      background-color: #D3D3D3;
    }
    #red{
      background-color: #FF0000;
    }
    
    #bgcasestudy{
      margin-left: 50%;
      margin-top: -.5em;
      transform: translate(-50%);
      font-family: Julius Sans One;
      position: absolute;
      font-size: 20vh;
      color: grey;
      z-index: 0;
      opacity: .3;
    }
    .technologies > img{
      height: 14vw;
      width: 14vw;
      border: none;
      border-color: white;
      border-radius: 7px;
      margin: 1vh;
    background-color: white;
   
        }
        .imgnobg{
          background-color: transparent !important; 
        }
    .technologies{
      margin-bottom: 20vh;
    }

    #backbutton{
      position: fixed;
      height: 2vw;
      width: 2vw;

    }
    a{
    color: white;
    text-decoration: none;
  }
    #backbutton:hover{
      cursor: pointer;
    }
    #backbutton > img{
      height: 4vw;
      width: 4vw;
      transition: .5s;
    }
    #backbutton:hover > img{
      
      transition: .5s;
      height: 4vw;
      width: 4vw;
      transform: rotate(180deg);
    }
    .colorsingle{
      margin-top: 3vh;
      color: white;
      display: flex;
      width: 70vw;
      margin-left: 10vw;
      justify-content: space-between;
    }
    .colorsingle > p{
      font-size: 2vw;
    }
    .colorsingle > div{
      height: 7vh;
      width: 20vw;
      background-color: white;
      border-radius: 7px;
    }
    .box > p{
      color: white;
      width: 80vw;
      font-size: 2vw;
      margin-bottom: 20vh;
    }
    .animated-title3 {
      width: 30vw;
    z-index: 0;
    color: #767676;
    font-family: Julius Sans One;
    
    
  }
  .coverprojecttitle{
    height: 12vh;
    width: 50vw;
    background-color: white;
    margin-left: 25vw;
    margin-top: -11em;
    animation: showworks 1s;
    animation-delay: 3s;
      animation-fill-mode: forwards;
      margin-bottom: 20vh;
    
  }
  .coverprojecth2{
    height: 9vh;
    width: 27vw;
    background-color: white;
    margin-left: 35vw;
      margin-bottom: 5vh;
    margin-top: -7em;
    animation: showworks 1s;
    animation-fill-mode: forwards;
  
  }
  .coverprojecth2temp{
    height: 9vh;
    width:  0vw;
    background-color: white;
    animation: showprograms2 1s;
    animation-fill-mode: forwards;
    margin-top: -7em;
    margin-bottom: 5vh;
    margin-left: 35vw;  
  }
    .animated-title2 {
      width: 20vw;
    z-index: 0;
      margin-top: 10vh;
    color: #767676;
    font-family: Julius Sans One;
    
    
  }
  .animated-title2 > div {
    
    overflow: hidden;
    
    
  }
  .animated-title2 > div div {
    font-size: 7vmin;
    padding: 2vmin 0;
    
  }
  .animated-title2 > div div span {
    display: block;
  }
  .animated-title2 > div.text-top {
   
    
  }
  .animated-title2 > div.text-top div {
    animation: showTopText 1s;
    animation-delay: 3s;
    animation-fill-mode: forwards;
    bottom: 0;
    transform: translate(0, 100%);
  }
  .animated-title2 > div.text-top div span:first-child {
    color: #fff;
  }
  .animated-title3 > div {
    
    overflow: hidden;
    
    
    
  }
  .buttonsTop{
    display:flex;
    width: 100%;
    justify-content: center;

  }
  .buttonsTop > button{
    transition: 1s;
    width: 10vw;
      height: 5vh;
      margin-left: .5vw;
      font-size: 3vh;
      background: #313131;
  box-shadow: 14px 14px 40px rgba(16, 16, 18, 0.75), -7px -7px 30px #313131;
  border: solid;
  border-color: white;
  border-radius: 7px;
  color: white;

  }
  .buttonsTop > button:hover{
    transition: 1s;
    background-color: white;
    color: #313131;
    cursor: pointer;
    transform: scale(1.1, 1.1);

  }
  .animated-title3 > div div {
    font-size: 7vmin;
    padding: 2vmin 0;
    
  }
  .animated-title3 > div div span {
    display: block;
  }
  .animated-title3 > div.text-top {
   
    
  }
  .animated-title3 > div.text-top div {
    animation: showTopText 1s;
    animation-delay: 2s;
    animation-fill-mode: forwards;
    bottom: 0;
    transform: translate(0, 100%);
  }
  .animated-title3 > div.text-top div span:first-child {
    color: #fff;
  }
  
  
  
  
    .contact > button{
      width: 8vw;
      height: 5vh;
      margin-left: 5vw;
      font-size: 3vh;
      background: #313131;
  box-shadow: 14px 14px 40px rgba(16, 16, 18, 0.75), -7px -7px 30px #313131;
  border: none;
  border-radius: 7px;
  color: white;
    }
    .contact > h2{
      color: white;
      align-self: left;
      margin-left: 5vw;
    }
    #phone{
      transform: scale(1, 1.1);
     
    }
    #tablet{
     
      transform: scale(1.5, .8);
     
    }
    .devices{
      display: flex;
     margin-top: 9vw;
     justify-content: space-evenly;
     margin-bottom: 1vh;
    }
    @keyframes devices {
    to{
     opacity: 1;
     margin-bottom:0vw;
    }
    
  }
    .box > h2{
      color: white;
      
      font-family: Julius Sans One;
      font-size: 3.0rem;
      background: #08CFBB;
  background: -webkit-linear-gradient(to bottom, #08CFBB 38%, #0685CF 100%);
  background: -moz-linear-gradient(to bottom, #08CFBB 38%, #0685CF 100%);
  background: linear-gradient(to bottom, #08CFBB 38%, #0685CF 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent; 
    }
    .devices > img{
     
      margin-right: 5vw;
      margin-left: 5vw;
      transform: scale(.1, .1);
     
    
      
      
    }
    #macbook{
      
      transform: scale(2.5, 2.0);
      
    
    
    }
    
    .contact{
      text-align: left;
      display: flex;
      margin-bottom: 5vh;
      flex-direction: column;
    }
    .contact> input{
      font-family: monospace;
  
      font-size: 3vh;
      color: white;
      align-self: center;
        height: 5vh;
    border: none;
    width: 90vw;
      background: #313131;
  border-radius: 7px;
  box-shadow: inset 30.03px 30.03px 15px #1E1E1E, inset -20px -20x 15px #2E2E2E;
      margin-bottom: 5vh;
    }
    .contact > input:focus, .contact > textarea:focus{
      outline: none;
      border: solid;
      border-width: 1px;
  
      border-color: white;
    }
    .contact > textarea{
  
      padding: 5px;
      color: white;
      font-size: 3vh;
      align-self: center;
      height: 20vh;
    border: none;
    width: 90vw;
      background: #313131;
  border-radius: 7px;
  box-shadow: inset 30.03px 30.03px 15px #1E1E1E, inset -20px -20x 15px #2E2E2E;
      margin-bottom: 5vh;
  
    }
    .contact > button{
    width: 10vw;
    height: 5vh;
    font-size: 3vh;
  }
  .contact > button:hover{
    background-color: white;
    color: #313131;
    cursor: pointer;
  }
    .programs{
      display: flex;
      flex-direction: row;
      overflow: scroll;
      padding-bottom: 4vh;
    }
    #programsheader{
      font-family: Julius Sans One;
      font-size: 4rem;
      background: #08CFBB;
  background: -webkit-linear-gradient(to bottom, #08CFBB 38%, #0685CF 100%);
  background: -moz-linear-gradient(to bottom, #08CFBB 38%, #0685CF 100%);
  background: linear-gradient(to bottom, #08CFBB 38%, #0685CF 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
    }
    .sinleprogram > h3{
      color: white;
      font-size: 4vh;
      margin-top: -3em;
    }
    .sinleprogram > span{
      color: white;
      margin: 2vh;
    }
    .sinleprogram{
      padding: 5vw;
  
      align-items: left;
      display: flex;
      flex-direction: column;
    }
    .programrow{
      display: flex;
      flex-direction: row;
      align-items: center;
      text-align: center;
      justify-content: center;
    }
    .programcover{
      align-self: left;
      z-index: 2;
      height: 7vh;
      width: 20vw;
      background-color: transparent;
      margin-left: 11vw;
      margin-top: 0em;
      
      margin-bottom: 5vh;
      
      
    }
    #programcover2{
      width: 20vw;
      
    }
    :root {
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
        Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    }
    main{
      padding: 0px;
      width: 100vw;
      overflow: hidden;
      margin: 0px;
    }
    #bgprojects{
      margin-left: 50%;
      margin-top: -.5em;
      transform: translate(-50%);
      font-family: Julius Sans One;
      position: absolute;
      font-size: 20vh;
      color: grey;
      z-index: 0;
      opacity: .3;
    }
    #bgprograms{
      margin-left: 50%;
      margin-top:  5%;
      transform: translate(-50%);
      font-family: Julius Sans One;
      position: absolute;
      font-size: 20vh;
      color: grey;
      z-index: 0;
      opacity: .3;
    }
    .programcard{
      z-index: 1;
      background: #313131;
  box-shadow: 14px 14px 40px rgba(16, 16, 18, 0.75), -7px -7px 30px #313131;
  height: 40vh;
  width: 40vw;
  border-radius: 11px;
  
  transition: 1s ease;
    animation: cardmove 1s ease;
    animation-fill-mode: forwards;
    }
    .worksall2{
      margin-top: 5vh;
      background-color: transparent;
    }
    .workall{
      
      margin-top: 5vw;
      width: 300vw;
      height:50vh;
  
    }
    #projectcard2{
      animation: cardmove2 1s ease;
     animation-fill-mode: forwards;
     margin-right: 0em;
     margin-left: 0em;
    }
    .projectcard3{
    background: transparent;
  height: 50vh;
  width: 50vw;
  border-radius: 11px;
  margin-right: -90em;
  margin-left: 90em;
  transition: 1s ease;
    animation: cardmove 1s ease;
    animation-fill-mode: forwards;
    
  
   }
   .projectcard{
    z-index: 1;
    background: #313131;
  box-shadow: 14px 14px 40px rgba(16, 16, 18, 0.75), -7px -7px 30px #313131;
  height: 50vh;
  width: 50vw;
  border-radius: 11px;
  margin-right: -90em;
  margin-left: 90em;
  transition: 1s ease;
    animation: cardmove 1s ease;
    animation-fill-mode: forwards;
    
  
   }
   .projectcard:hover{
     background-color: white;
     cursor: pointer;
   }
   @keyframes cardmove {
    to{
      margin-right: 0em;
      margin-left: 0em;
    }
    
  }
  @keyframes cardmove2 {
    to{
      margin-left: 90em;
      margin-right: -90em;
    }
    
  }
  @keyframes sign {
    to{
      stroke-dashoffset: 0;
    }
    
  }
  @keyframes sign2 {
    50%{
      stroke-dashoffset: 0;
    }
    100%{
      stroke-dashoffset: 1000;
    }
    
    
  }
  .transtion{
    
    background-color: red;
    position: fixed;
    overflow: hidden;
    top: 0;
    left: 0;
    height: 100vh;
    width: 100vw;
    
  }
  #load1{
    animation: sign 2s infinite;
    
    
  }
  #load2{
    animation: sign2 2s infinite;
    
    animation-delay: .25s;
  }
  #load3{
    animation: sign2 3s infinite;
   
    animation-delay: .5s;
  }
  #one{
    z-index: 5;
    transition: 1s ease;
    animation: move .3s ease;
    animation-fill-mode: forwards;
    background-color: #00FFD1;
  }
  #two{
    z-index: 4;
    transition: 1s ease;
    animation: move .5s ease;
    animation-fill-mode: forwards;
    animation-delay: .3s;
    background-color: #BD00FF;
  }
  #three{
    z-index: 3;
    transition: 1s ease;
    display: grid;
    place-items: center;
    animation: move .5s ease;
    animation-fill-mode: forwards;
    animation-delay: .8s;
    background-color: #00C2FF;
    
  }
  #four{
    z-index: 2;
    transition: 1s ease;
    display: grid;
    place-items: center;
    animation: move .5s ease;
    animation-fill-mode: forwards;
    animation-delay: 1.8s;
    background-color: #fff;
    
  }
  #four > svg{
    transition: 1s ease;
    height: 20vh;
    width: 20vh;
    
  }
  #five{
    z-index: 5;
    transition: 1s ease;
    animation: movepage .3s ease;
    animation-fill-mode: forwards;
    background-color: #00FFD1;
  }
  #six{
    z-index: 4;
    transition: 1s ease;
    animation: movepage .5s ease;
    animation-fill-mode: forwards;
    animation-delay: .3s;
    background-color: #BD00FF;
  }
  #seven{
    z-index: 3;
    transition: 1s ease;
    display: grid;
    place-items: center;
    animation: movepage .5s ease;
    animation-fill-mode: forwards;
    animation-delay: .8s;
    background-color: #00C2FF;
    
  }
  #eight{
    z-index: 2;
    transition: 1s ease;
    display: grid;
    place-items: center;
    animation: movepage .5s ease;
    animation-fill-mode: forwards;
    animation-delay: 1.8s;
    background-color: #fff;
    
  }
  .box{
   
    
    align-items: center;
    
  }
  .box > h1{
    position: relative;
    
      z-index: 1;
    color:white;
    margin-bottom: 12vh;
    
    font-size: 10vh;  
  }
  #eight > svg{
    transition: .5s ease;
    height: 20vh;
    width: 20vh;
    
  }
  @keyframes movepage{
    to{
      left: -100vw;
    }
    
  }
  @keyframes move{
    to{
      left: 100vw;
    }
    
  }
  @keyframes navm{
    to{
      margin-left: -6em;
    }
    
  }
  @keyframes sepera{
    to{
      width:100vw;
    }
    
  }
  #logo1{
    
    stroke-dasharray: 1000;
    stroke-dashoffset: 1000;
    animation: sign 1s ease;
    animation-delay: 4.75s;
    animation-fill-mode: forwards;
  }
  #logo2{
    
    stroke-dasharray: 1000;
    stroke-dashoffset: 1000;
    animation: sign 2s ease;
    animation-delay: 4.75s;
    animation-fill-mode: forwards;
  }
  #logo3{
    
    stroke-dasharray: 1000;
    stroke-dashoffset: 1000;
    animation: sign 3s ease;
    animation-delay: 4.75s;
    animation-fill-mode: forwards;
  }
    main {
      
      text-align: center;
      padding: 0;
      margin: 0 auto;
      background-color: #262626;
      overflow-y: hidden;
  
    }
    .cssanimation, .cssanimation span {
      animation-duration: 1s;
      animation-fill-mode: both;
  }
  
  .cssanimation span { display: inline-block }
  
  .leRotateSkateInLeft span { animation-name: leRotateSkateInLeft }
  @keyframes leRotateSkateInLeft {
      from {
          transform: scaleX(0.2) translateX(-100px);
          opacity: 0;
      }
  }
  
   
  .seperator{
    width:0vw;
    background: white;
    height: 2vh;
    margin-top: 8vh;
    margin-left: -1.5em;
    animation: sepera 3s ease;
    animation-delay: 4.5s;
    animation-fill-mode: forwards;
  }
  .seperator3{
    width:0vw;
    background: white;
    height: 2vh;
    margin-top: 8vh;
    margin-bottom: 8vh;
    margin-left: -1.5em;
    animation: sepera 3s ease;
    animation-delay: 4.5s;
    animation-fill-mode: forwards;
  }
  .seperator2{
    width:0vw;
    background: white;
    height: 2vh;
    margin-top: 0vh;
    margin-left: -1.5em;
    animation: sepera 3s ease;
    animation-delay: 4.5s;
    animation-fill-mode: forwards;
  }
    img {
      height: 16rem;
      width: 16rem;
    }
  .title{
    text-align: left;
    align-self: center;
    margin-left: 10vw;
    margin-right: 5vw;
  }
  svg{
    
    stroke-dasharray: 1000;
    stroke-dashoffset: 1000;
    animation: sign 30s ease;
    animation-delay: 6.3s;
    animation-fill-mode: forwards;
    display: hidden;
  }
    .title > h1 {
      animation: showTopText 1s;
    animation-delay: 0.5s;
    animation-fill-mode: forwards;
      
  -webkit-text-fill-color: transparent;
  font-family: Julius Sans One;
      font-size: 4rem;
      font-weight: 1;
      line-height: 1.1;
      
    }
    .title > h2{
     
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-family: Julius Sans One;
    }
    .home{
      display:flex;
      overflow: visible;
      height: 80vh;
      margin-top: 5vh;
     
  
    }
  
    p {
      max-width: 14rem;
      margin: 1rem auto;
      line-height: 1.35;
    }
  .navbar{
    z-index: 10;
    top: 13%;
    position: fixed;
    background: #313131;
  box-shadow: 14px 14px 40px rgba(16, 16, 18, 0.75), -7px -7px 30px #313131;
  border-radius: 8px;
  width: 7vw;
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 60vh;
  justify-content: space-between;
  margin-left: -7em;
  
  }
  .navbar > .navbar-icon{
    margin-bottom: 2vh;
  }
  .navbar-icons{
    margin-top: -2em;
    height: 40vh;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
  }
  .navbar-icon {
    box-shadow: 7px 7px 20px rgba(16, 16, 18, 0.75), -7px -7px 30px #262E32;
  border-radius: 8px;
  width: 7vh;
  z-index: 1;
  
  }
  #worksheader{
    padding-top: 3vh;
    font-family: Julius Sans One;
      font-size: 4rem;
      background: #08CFBB;
  background: -webkit-linear-gradient(to bottom, #08CFBB 38%, #0685CF 100%);
  background: -moz-linear-gradient(to bottom, #08CFBB 38%, #0685CF 100%);
  background: linear-gradient(to bottom, #08CFBB 38%, #0685CF 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  
  }
  .navbar-icon >img{
    height: 6vh;
      width: 6vh;
      left: 0;
      
  }
    .navbar-open > img{
      height: 6vh;
      width: 6vh;
      left: 0;
      margin-left: 9vw;
  
    }
    .navbar-open{
      transition: 1s ease;
      background: #313131;
     box-shadow: 14px 14px 40px rgba(16, 16, 18, 0.75), -7px -7px 30px #262E32;
  border-radius: 8px;
  width: 13vw;
  margin-left: 2vw;
  
    animation-fill-mode: forwards;
    animation-delay: 5.5s;
  
    }
    .coverprogram{
      z-index: 2;
      height: 10vh;
      width: 25vw;
      background-color: white;
      margin-left: 37vw;
      margin-top: -8em;
      animation: showworks 1s;
      animation-delay: 1s;
      animation-fill-mode: forwards;
      margin-bottom: 5vh;
    }
    #coverprogram2{
      width: 0vw;
      animation: showprograms2 1s;
      animation-fill-mode: forwards;
    }
    #coverworks2{
      width: 0vw;
      animation: showworks2 1s;
      animation-fill-mode: forwards;
    }
    .coverworks{
      z-index: 2;
      height: 10vh;
      width: 20vw;
      background-color: white;
      margin-left: 40vw;
      margin-top: -8em;
      animation: showworks 1s;
      animation-delay: 1s;
      animation-fill-mode: forwards;
      margin-bottom: 5vh;
    }
    .cover{
      margin-top: 5vh;
      margin-left: 0vw;
      z-index: 0;
     position:fixed;
      background: #313131;
      height: 50vh;
      width: 7vw;
    }
    .shapes > svg{
      position: absolute;
    }
    @media (min-width: 480px) {
      h1 {
        max-width: none;
      }
  
      p {
        max-width: none;
      }
    }
    
  @keyframes twister {
      10% {
          opacity: 1;
      }
    25%{
      color: #00C2FF;
    }
    50%{
      color: #00FFD1;
    }
    75%{
      color: #BD00FF;
    }
      100% {
          transform: rotate(0deg) translate(0);
          opacity: 1;
      
      }
  }
  
  @import url('https://fonts.googleapis.com/css?family=Roboto:700');
  @keyframes showTopText {
    0% {
      transform: translate3d(0, 100%, 0);
    }
    40%, 60% {
      transform: translate3d(0, 50%, 0);
    }
    100% {
      transform: translate3d(0, 0, 0);
    }
  }
  @keyframes showBottomText {
    0% {
      transform: translate3d(0, -100%, 0);
    }
    100% {
      transform: translate3d(0, 0, 0);
    }
  }
  @keyframes showworks {
    to{
      width: 0vw;
    }
  }
  @keyframes showworks2 {
    to{
      width: 20vw;
    }
  }
  @keyframes showprograms2 {
    to{
      width: 27vw;
    }
  }
  .work{
    text-align: left;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: top;
    width: 100vw;
    
    
  }
  #projecttitle{
    position: static;
    z-index: 0;
    height: 50vh;
    left: 0%;
    margin-top: 0px;
    
    transform: translate(0%, 0%);
  }
  .animated-title {
    z-index: 0;
  
    color: #767676;
    font-family: Julius Sans One;
    height: 50vh;
    left: 30%;
    position: absolute;
    top: 50%;
    transform: translate(-50%, -50%);
    width: 60vmin;
  }
  .animated-title > div {
    height: 50%;
    overflow: hidden;
    position: absolute;
    width: 100%;
  }
  .animated-title > div div {
    font-size: 7vmin;
    padding: 2vmin 0;
    position: absolute;
  }
  .animated-title > div div span {
    display: block;
  }
  .animated-title > div.text-top {
    border-bottom: 1vmin solid #fff;
    top: 0;
  }
  .animated-title > div.text-top div {
    animation: showTopText 1s;
    animation-delay: 3s;
    animation-fill-mode: forwards;
    bottom: 0;
    transform: translate(0, 100%);
  }
  .animated-title > div.text-top div span:first-child {
    color: #fff;
  }
  .animated-title > div.text-bottom {
    
    bottom: 0;
  }
  #cmps{
    font-size: 4vmin;
  }
  
  .animated-title > div.text-bottom div {
    animation: showBottomText 0.5s;
    animation-delay: 4.25s;
    animation-fill-mode: forwards;
    top: 0;
    transform: translate(0, -100%);
  }
  #projecttitle > div.text-bottom div { 
    font-size: 3vh;
    
    animation-delay: 2.5s;
    
  }
  #projecttitle > div.text-top div { 
    font-size: 5vh;
    
  
    animation-delay: 1.25s;
    
  }
  #projecttitle > div.text-top div span:first-child {
    
  }
  #projecttitle > div.text-top {
   
    top: 0;
  }
  
  
  
  
  </style>
  