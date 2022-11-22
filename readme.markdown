# ISTE-240 Midterm Project

## Overview

### Built With:
* [![HTML5][HTML-badge]][HTML-url]
* [![CSS3][CSS-badge]][CSS-url]

# Information Architecture

## Ontology
This website is all about green energy and how we can harness it for a greener future. I discuss electricity demand, some forms of renewable energy, how carbon emmissions can affect our planet, and who is taking action on behalf of humanity.

## Taxonomy
The website is comprised of six webpages, each discussing one of the topics mentioned above.

1. Home
    - Earth Video with button to electricity page
        - Introduction to discussed topics
        - Questions for the reader to internalize
2. Electricity
    - Power Plant Video with text
        - Introduction to discussed topics
    - Information from ExxonMobil regarding global energy use
        - Demand, current sources, future sources
3. Renewables
    - Hoover Dam video with text
        - Introduction to discussed topics
    - Information discussing forms of renewabale energy
        - Hydroelectric, Solar, Geothermal
    - Discussing the difficulty of transitioning to renewable energy
4. Emissions
    - Carbon Emissions video with text
        - Introduction to discussed topics
    - Carbon Footprint
        - Percentages from the EPA
    - Reducing emissions
        - Discussing the good and the bad
5. Action
    - Abstract green globe with text introducing the topic
        - Introduction to discussed agencies and groups
    - Listing of groups and agencies and what they're known for
6. Sources
    - Same Earth video as the home page
        - Just a list of sources used for the project

## Choreography
My intended choreography for the project is simple, just let the user flow through the webpage by scrolling and learning about the topics. The top of each of the pages is the same: a video relating to the topic, a simple but modern navigation bar, some informative text, and a very nice "scroll down" CSS animation. This gently tells the user "hey, it looks like I can scroll down to learn more!". On the bottom of each page is an included shortcut button: this simply and smoothly scrolls the user back to the top/nav section, since they will be scrolling through the page anyway. The user will be greeted with a video for each page, and then a list of information regarding the topic. The majority of images used are SVG images. They're included on each page to help break up the text and make the page more visually appealing, but not to the point where they become distracting. On the Taking Action page, there is a list of groups and agencies relating to climage change. This page has a logo from each group/agency and all of them link to each of their websites, so the user can learn more about them and what they're doing.

# Site Wireframes
[Three Column Layout](https://xd.adobe.com/view/77d662c8-cb39-4dee-ada4-aaf2aec01767-2285/screen/c62acec7-1b69-4ef7-a062-3cd890090c4b/)
[Two Column Layout](https://xd.adobe.com/view/77d662c8-cb39-4dee-ada4-aaf2aec01767-2285/screen/c62acec7-1b69-4ef7-a062-3cd890090c4b)

# Advanced CSS Properties
Some advanced CSS that I used comes in the form of the videos on each page. I wanted to really add to the user's overall view of the website by giving them a relevant video behind a transparent overlay. I used this animation to further drive home the fact this website is very vertical; more information comes with scrolling.

<div class="mouse_scroll">
    <div class="mouse">
            <div class="wheel"></div>
    </div>
    <div>
        <span class="m_scroll_arrows one"></span>
        <span class="m_scroll_arrows two"></span>
        <span class="m_scroll_arrows three"></span>
    </div>
</div>


I also added small but convienent shortcut buttons at the bottom of each page. This was accomplished by adding a smooth scroll behavior in the CSS. Using HTML IDs, I was able to tell the button to scroll the viewport towards the very top of the page, returning the user to the video and the navigation bar. The resulting button looks as follows. 

## Test it out to see the smooth scrolling in action!

<a href="#top" class="center-btn">Back to Top of Page</a>


```
@media screen {
    html {
        scroll-behavior: smooth;
      }
}
```

Finally, the color pallete I used was (in my opinion), modern but exciting. It was this sort-of muted but bright green/teal color, and the off-white text reads nice on top of it. I also wanted to make sure I had some sort of dark screen in front of the videos, so I used a CSS Linear Gradient. It allows the video to stay visible, but not distract from the text. 

```
.header {
    min-height: 100vh;
    width: 100%;
    background-position: center;
    background-image: linear-gradient(rgba(4,9,30,0.7),rgba(4,9,30,0.7));
    background-size: cover;
    position: relative;
}
```

[HTML-badge]: https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=HTML5&logoColor=white
[HTML-url]: https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5
[CSS-badge]: https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=CSS3&logoColor=white
[CSS-url]: https://developer.mozilla.org/en-US/docs/Web/CSS

<style>
    /* Animation */
*, *:before, *:after {
    -moz-box-sizing: border-box; -webkit-box-sizing: border-box; box-sizing: border-box;
   }
  
  
  .mouse_scroll {
      display: block;
      margin: 0;
      width: 24px;
      height: 100px;
  }
  
  
  .m_scroll_arrows
  {
    display: block;
    width: 5px;
    height: 5px;
    -ms-transform: rotate(45deg); /* IE 9 */
    -webkit-transform: rotate(45deg); /* Chrome, Safari, Opera */
    transform: rotate(45deg);
     
    border-right: 2px solid #EDF5E1;
    border-bottom: 2px solid #EDF5E1;
    margin: 0 0 3px 4px;
    
    width: 16px;
    height: 16px;
  }
  
  
  .one
  {
    margin-top: 1px;
  }
  
  .one, .two, .three
  {
      -webkit-animation: mouse-scroll 1s infinite;
      -moz-animation: mouse-scroll 1s infinite;
      animation: mouse-scroll 1s infinite;
    
  }
  
  .one
  {
    -webkit-animation-delay: .1s;
    -moz-animation-delay: .1s;
    -webkit-animation-direction: alternate;
    
    animation-direction: alternate;
    animation-delay: alternate;
  }
  
  .two
  {
    -webkit-animation-delay: .2s;
    -moz-animation-delay: .2s;
    -webkit-animation-direction: alternate;
    
    animation-delay: .2s;
    animation-direction: alternate;
    
    margin-top: -6px;
  }
  
  .three
  {
    -webkit-animation-delay: .3s;
    -moz-animation-delay: .3s;
    -webkit-animation-direction: alternate;
    
    animation-delay: .3s;
    animation-direction: alternate;
    
    
    margin-top: -6px;
  }
  
  .mouse {
    height: 42px;
    width: 24px;
    border-radius: 14px;
    transform: none;
    border: 2px solid #EDF5E1;
    top: 170px;
  }
  
  .wheel {
    height: 5px;
    width: 2px;
    display: block;
    margin: 5px auto;
    background: #EDF5E1;
    position: relative;
    
    height: 4px;
    width: 4px;
    border: 2px solid #EDF5E1;
    -webkit-border-radius: 8px;
            border-radius: 8px;
  }
  
  .wheel {
    -webkit-animation: mouse-wheel 0.6s linear infinite;
    -moz-animation: mouse-wheel 0.6s linear infinite;
    animation: mouse-wheel 0.6s linear infinite;
  }
  
  @-webkit-keyframes mouse-wheel{
     0% {
      opacity: 1;
      -webkit-transform: translateY(0);
      -ms-transform: translateY(0);
      transform: translateY(0);
    }
  
    100% {
      opacity: 0;
      -webkit-transform: translateY(6px);
      -ms-transform: translateY(6px);
      transform: translateY(6px);
    }
  }
  @-moz-keyframes mouse-wheel {
    0% { top: 1px; }
    25% { top: 2px; }
    50% { top: 3px;}
    75% { top: 2px;}
    100% { top: 1px;}
  }
  @-o-keyframes mouse-wheel {
  
     0% { top: 1px; }
    25% { top: 2px; }
    50% { top: 3px;}
    75% { top: 2px;}
    100% { top: 1px;}
  }
  @keyframes mouse-wheel {
  
     0% { top: 1px; }
    25% { top: 2px; }
    50% { top: 3px;}
    75% { top: 2px;}
    100% { top: 1px;}
  }
  
  @-webkit-keyframes mouse-scroll {
  
    0%   { opacity: 0;}
    50%  { opacity: .5;}
    100% { opacity: 1;}
  }
  @-moz-keyframes mouse-scroll {
  
    0%   { opacity: 0; }
    50%  { opacity: .5; }
    100% { opacity: 1; }
  }
  @-o-keyframes mouse-scroll {
  
    0%   { opacity: 0; }
    50%  { opacity: .5; }
    100% { opacity: 1; }
  }
  @keyframes mouse-scroll {
  
    0%   { opacity: 0; }
    50%  { opacity: .5; }
    100% { opacity: 1; }
  }

  /* Button */
  .center-btn{
    display: inline-block;
    text-decoration: none;
    color: #EDF5E1;
    border: 1px solid #EDF5E1;    
    padding: 12px 34px;
    font-size: 20px;
    background: transparent;
    position: relative;
    cursor: pointer;
}

.center-btn:hover{
    border: 1px solid #379683;
    background: #379683;
    transition: 1s;

}

@media screen {
    html{
        scroll-behavior: smooth;
    }
}
</style>