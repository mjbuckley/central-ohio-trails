## To Do

- ***Trails To Review/Recheck:***
  - Camp Chase Trail. Add links to review in Scioto Trail and Battelle Darby Creek reviews because the Camp Chase goes through both of them.
  - Chestnut Ridge. There are 3 new sections: Squatch, Fireball, and More Cowbell. I have seen parts of the More Cowbell (has lots of jumps and other things, called a flow trail), but not ridden it. I did do the Squatch. It is listed as a advanced, but it it basically like everything else, although it does at a decent amount of mileage. I have not done the Fireball. Be sure to ride the two sections I haven't and then add that info to the trail review.
  - Alum Creek mtb trail
  - Alum creek trail running trail (might be called roots and rocks?)
  - Is John Bryan and the other Yellow Springs stuff too far away to be considered Central Ohio? If ok the review them.
  - AW Marion mtb trail?
  - Right now I don't have a review of the Hellbranch Trail because it is too incomplete feeling, but I suspect it will continue to be improved. I last rode it in fall of 2018. Maybe check again in a year. Right ow I have a mention of it on the Heritage Trail review because it joins up with that trail. If I make a review be sure to link it to the Heritage Trail review and then remove the mini review I have there now.
  - Dublin Trails: There seem to be a lot of trails in Dublin. Not sure if they are just a bunch of neighborhood trails or if they are connected. Look into this.
  - Alum Creek Trail. Not the park but the Greenway trail.
  - Blacklick Trail. Not the park but the Greenway trail.
  - Three Creeks.
  - Walnut Woods
  - Glacier Ridge.
  - Pickerington Ponds
  - Rocky Fork doesn't have a lot now, but it looks like they have land and I bet they expand. Keep in mind for the future.
  - Chestnut Ridge: There are some hiking trails in addition to the mtb trails. Not a lot so not worth a special trip, but maybe check them out some time when I'm mountain biking there.
  - Slate Run
  - Not sure how real the Ohio To Erie Trail is. Check this out.
  - Others?
- Consider changing the breakpoint for the essential info section to be a bit wider. Many phones don't switch to the mobile view when horizontal and I'm not sure if I like how that looks.
- Add higher quality images. Keep the same cropping, just use higher quality compression.
- See about using Cloudflare as a way of using https on Github pages with my custom domain.
- Maybe make the caption font color a touch darker (this color might be being used elsewhere too and it should be changed everywhere).
- Add a note about how I've made responsive images work and how to use. Also that the site design assumes 16x9 proportions.
- I'm not using footer in includes. Probably kept around as reference, but remove?
- Improve site meta/consider having page specific meta.
- Add picture on about?
- I now have Lato 300. I've used it in a few places, but I think a lot of places could improve by using it.
- Add a favicon.
- Curious about the feed.xml.  It's for RSS syndication, but I'm not sure exactly how it's used/if it's already set up to work or if something needs to be done.  Not sure I even want it, but I'd like to understand it.
- I have my homepage background image url as /assets/imagename.  This is fine.  However, for all of my other links I have site.baseurl prepended to the link.  That way, if my site is ever served from a baseurl (think domainname/blog instead of just domainname/), I can just change the baseurl variable to /blog instead of "" and then all of my links will still work.  But I can't figure out a good way to do that in a sass file (liquid templates don't work there).  This is the only backgound image, so it's not a big deal, but keep it in mind.
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
