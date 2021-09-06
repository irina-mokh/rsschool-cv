# **Irina Mokh**

* Saint-Petersburg, Russia
* +7(911)7390359
* telegram: <https://t.me/mokh_irina>
* imoh91@gmail.com
* github: <https://github.com/irina-mokh>

## **About:**
I'm a 30yo Construction Cost Engineer with 7-year experience. I intend to change my profession because of personal interests to IT and modern tendentions of changing labour market.
Soft skills:
* Easy-learning
* Teamwork
* Problem-solving 
* Independence

## Education
Saint-Petersburg State University of Economics(2013), Construction managment and economics
[HTML Academy - #30 HTML и CSS](https://irina-mokh.github.io/1662375-technomart-30/)


## **Skills:**
* HTML
* CSS
* JavaScript - basic
* Gulp
* Git
* English - B2-C1

___
## **Portfolio:**
[Training project YEBO](https://irina-mokh.github.io/yebo/)  
[HTML Academy - graiding](https://irina-mokh.github.io/hanters_plants/)  
[Training project Uber Eats](https://irina-mokh.github.io/uber_eats/)  
[Training project Funiro](https://irina-mokh.github.io/funiro/)

**Code example:**
```
  class Slider {
    constructor (slider, alignSide, i, gap) {
      this.sliderName = slider;
      this.slider = document.querySelector(slider + " .slider");

      this.slides = Array.prototype.slice.call(document.querySelectorAll(slider + " .slide:not(.slide_pseudo)"));
      this.gap = gap;

      this.sliderDots = Array.prototype.slice.call(
      document.querySelectorAll(slider + " .slider-dot"));
      let self = this;
          
      this.alignSide = alignSide;
      this.i = i;

      this.sliderDots.forEach((index) =>{
        index.addEventListener("click", (evt) => {
          evt.preventDefault;
          this.i = this.sliderDots.indexOf(index); 
          this.sliderRefresh();
        })
      });
    
      this.btnNext = document.querySelector(slider + " .arrow-next");
      this.btnPrev = document.querySelector(slider + " .arrow-prev");
    
      this.btnPrev.addEventListener("click", function(evt){
        evt.preventDefault();
        self.i--; 
        if (self.i < 0) {
          self.i = self.slides.length - 1;
        };
        self.sliderRefresh();
      });
      
      this.btnNext.addEventListener("click", function(evt){
        evt.preventDefault();
        self.i++;
        if (self.i >= self.slides.length){
          self.i = 0;
        };
        self.sliderRefresh();
      });

      this.pseudoLast = this.slides[0].cloneNode(true);
      this.pseudoLast.classList.remove("slide_active", "slide");
      this.pseudoLast.classList.add("slide_pseudo");

      this.pseudoFirst = this.slides[this.slides.length-1].cloneNode(true);
      this.pseudoFirst.classList.remove("slide_active", "slide");
      this.pseudoFirst.classList.add("slide_pseudo");

      this.slider.appendChild(this.pseudoLast);
      this.slider.insertBefore(this.pseudoFirst, this.slides[0]); 
    }

    sliderRefresh() {
      this.activeDot = document.querySelector(this.sliderName + " .slider-dot_active");
      this.activeDot.classList.remove("slider-dot_active");
      this.sliderDots[this.i].classList.add("slider-dot_active");

      this.activeSlide = document.querySelector(this.sliderName + " .slide_active");
      this.activeSlide.classList.remove("slide_active");
      this.slides[this.i].classList.add("slide_active");

      let slideWidth = document.querySelector(this.sliderName + " .slide:not(.slide_active)").offsetWidth + this.gap;

      if (this.alignSide === "right") {
        this.slider.style.marginRight = -slideWidth * (this.slides.length + 1 - this.i - 1) + 'px';
      } else if (this.alignSide === "left") {
        this.slider.style.marginLeft = -slideWidth * (this.i + 1)  + 'px';
      };
    };
  };
```