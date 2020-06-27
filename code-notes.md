<!-- scratch css testing !-->
<link href="main.css" rel="stylesheet"></link>

notes on conventions & some github pages defaults
*
GitHub Pages size defualts:
max-width: 1012px;
50% = 506px i.e. max images @500 px?
bandcamp player - add trackname?
soundcloud player = remove artwork - &amp;show_artwork=false
*
Order:
Date | TITLE | Type (performance, published etc.) | Venue/Label 
*
Date values
```--------```
```00/00/00```
Empty Date / inset block
<kbd>--------</kbd>
*
Details: use html inside <details> tags
No details: write in markdown
*
Details protocol:
<details><summary>
<strong>TITLE</strong> Type <a href="#">Target</a><sup>(+)</sup>
</summary>
    <div id="details-wrap">
        <a href="#">link to project page</a><br>
        project details brief
        <blockquote>any quote</blockquote>
            <div id="bs-player">
            !! Bandcamp / Soundcloud player here !!
            </div>
        <img src="#" class="responsive-img"><br>
        <a href="#">PDF</a>
    </div>
</details>
*
Image protocol
![alt text](source)
Image link
[![alt text](preview-image-link)](source-destination-link)
HTML image-link (inside details)
<href="link"><img src="destination"></a>
*
!-->
<!-- MAIN CONTENT BELOW !-->