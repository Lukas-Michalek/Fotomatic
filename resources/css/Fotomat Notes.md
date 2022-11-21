# Fotomat Notes

## Problemy
1. Problem nastal ked sa mi div s navigaciou zmensil po aplikovani display: flex (vsetko som mal pekne rozmiestnene no zrazu sa mi tie medzery stratili)

`RIESENIE` <br>
The problem was solved by removing margins from main container(header) and I have rather use the required margins directly on elemets within header(logo and instagram)<br><br>

2. Problem - **Items overflowing flexbox** <br>
 In order to fix this problem I had to use for every flex item inside box(lower gallery in this case) min-width: 0, so all the items would fit inside flexbox

 3. Problem - **Div would not take top and bottom margins**<br>
   Problem was caused due to `Collapsing Margin Property` I was able to solve it with `overflow: auto` however I need to find a better way
   
   4. `Problem` .... When resizing the webpage elements overflow one into another<br><br>
  `SOLUTION => `I have change the flex container the items were in to `lex-wrap: nowrap` so the items(pictures in this case) has just shrunk to fit the container

  # !!!  DO NOT USE FIXED DIMENSIONS FOR DIVS !!!
  A better way is to just use paddings and margins
   <br><br>
Also it is wise to use percentage for final margins as they will scale down(when resizing browser window) evenly. Far better than pixels

4. Problem -> **How to make sure that gallery which has originally 4 pictures upon reaching breakpoint(changing viewport to mobile scree) will display only 3 image?**
   <br><br>
   `SOLUTION => ` In HTML I will name the picture I do not want to see as `#optional` and in `@media screen only and (max-width=480px)` - for example I will target the specific image. Example can be <br>
   ```
    .gallery #optional{
      display: none;
    }
    ```

    # !!! REMEMBER !!!

    1. Use % for utmost margins

    2. DO NOT! use fixed heights and widths in px. It makes problems when scalling and resizing the browser window. Where possible use rather `Margins and Paddings` it si much better for scaling.

    3. When there is background image with margins around its content use 
    ``` 
    overflow: hidden;

    background-position: center;
    background-repeat: no-repeat;
    background-size:cover;
    ```
      To make sure it will cover the whole area.