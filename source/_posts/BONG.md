---
title: BONG
cover_image: images/kaku.jpg
date: 2020-07-02 17:12:11
tags:
---
 1 <!DOCTYPE html>
 2 <html lang="en">
 3 
 4 <head>
 5     <meta charset="UTF-8">
 6     <title>多图无缝循环翻页效果</title>
 7     <style>
 8     * {
 9         margin: 0;
10         padding: 0;
11     }
12 
13     .carousel {
14         width: 1000px;
15         height: 500px;
16         margin: 0 auto;
17         overflow: hidden;
18     }
19 
20     .carousel ul li {
21         width: 1000px;
22         height: 500px;
23         list-style-type: none;
24         float: left;
25     }
26 
27     .carousel ul li a img {
28         width: 100%;
29         height: 100%;
30         object-fit: contain;
31     }
32     </style>
33 </head>
34 
35 <body>
36     <div class="carousel">
37         <ul>
38             <li>
39                 <a href="#">
40                     <img src="https://s2.loli.net/2022/01/12/pLkD2oPaKFNtbQy.jpg" alt="1">
41                 </a>
42             </li>
43             <li>
44                 <a href="#">
45                     <img src="https://s2.loli.net/2022/01/12/TsqVp17I9F6rGcl.jpg" alt="2">
46                 </a>
47             </li>
48             <li>
49                 <a href="#">
50                     <img src="https://s2.loli.net/2022/01/12/7vhLsVr3xo9a8jk.jpg" alt="3">
51                 </a>
52             </li>
53         </ul>
54     </div>
55 </body>
56 
57 </html>
58 <script src="https://code.jquery.com/jquery-3.2.1.min.js"></script>
59 <script>
60 var carousel = $('.carousel ul'),
61     li = $('.carousel ul li');
62 carousel.css('width', li.width() * li.length);
63 setInterval(function() {
64     carousel.animate({
65         'marginLeft': -li.width()
66     }, 500, function() {
67         $(this).animate({ 'marginLeft': 0 }, 0)
68             .find('li').eq(0).appendTo($(this));
69     });
70 }, 3000);
71 </script>