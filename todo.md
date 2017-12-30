## To Do

- Consider changing the breakpoint for the essential info section to be a bit wider. Many phones don't switch to the mobile view when horizontal and I'm not sure if I like how that looks.
- Add higher quality images. Keep the same cropping, just use higher quality compression.
- See about using Cloudflare as a way of using https on Github pages with my custom domain.
- Maybe make the caption font color a touch darker (this color might be being used elsewhere too and it should be changed everywhere).
- I now have Lato 300. I've used it in a few places, but I think a lot of places could improve by using it.
- Add additional reviews and recheck my current reviews for any changes or additions.
- Add a favicon.
- Run through Google's mobile/page speed test to see if there's anything obvious I should fix that I'm missing.
- Consider ways to improve the trail listing table, esp. for mobile. Also maybe add a simple (clickable?) map showing where the trails are located.
- Improve about page. Make styling nicer, maybe include and image.
- Maybe have images go full width on mobile so I can get them slightly bigger?
- Improve the styling for the additional info section. I did a few things to make it be set off a bit more from the main section, but it could still be improved.
- I've left the hr element that I use above the additional info section unstyled except for margins. Each browser renders it a touch differently, but all that I've seen look similar and fine for now. However, I might consider adding more styles here.
- There is a weird quirk with how safari handles srcset images. I have a reasonable solution, but consider finding a better one if I have time. See Safari Image Note for details.
- The image on the homepage is a div with a background image. Is a good way to do responsive background images? Right now I serve up the same image for everyone. Maybe switch to something like the picture element? Would be nice to be able to have 2x image for larger screens and something smaller for small devices.


### Safari Image Note

Safari (on mobile and desktop) does something weird with srcset images. It will pick the correct image size, but if the window size changes or device orientation changes, it does get a new image when one is needed. Not only that, but if the original image was shrunken to fit its containing parent, it doesn't even expand back to its full size. For example, on a 320x480 2x phone in portrait the correct body image size to download is the 700 px size, which gets shrunken down to something like 290/580 once padding is taken in to account. Then, when the phone is switched to landscape, the image should be somewhere in the neighborhood of 430/860, but it is still displayed as 290/580 with lots of white space. It doesn't even go back to its full size. My solution isn't ideal, but it works reasonably well. I set the min-width of all img elements that are direct children of a figure to have a min-width of 100% (in base.css: figure > img {min-width: 100%;}). Here the percentage refers to the containing block, not the image size. This ensures that the image always takes up the full size it is supposed to. Of course, this means that in some cases the image could appear pixilated if it expands beyond its natural size. In practice this seems not to be a problem for three reasons. First, most changes in window size are likely to be relatively minor such as going from portrait to landscape or slightly increasing a desktop window size. Second, many devices are already taking images at 2x, so there is a lot of room to play with before things start looking bad. Third, images are often larger than they need to be to begin with, so there is room for things to be increased. I wish I had a better way to deal with this, but it's the best that I've found. Also, this method does not appear to prevent other browsers from using their behavior.
