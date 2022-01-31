Braindump (I'll probably come up with more notes later on):

- Not using a CSS preprocessor atm, so styles are split in between the inline definitions in components, and the globals outside of the component structure.  Implemented classes are kind of sloppy and not as modular as would be ideal.  Preprocessor would help with clean up.

- Hero section would ideally see the logo get fixed to the nav bar in some way when the page is scrolled.

- I was initially thinking of a more expanded Studios section that would lead more fluidly into the games accordion below, but didn't want to spend too much time exploring on that since I didn't really come up with a good idea to implement in a timely enough fashion.

- Games section is probably not ideal layout, wouldn't work with more than 5 games per studio, so a grid style layout would likely be the better solution in that scenario.  For screen width constraints (mobile / tablets), the accordion would need to transition to a vertical layout.

- There's pretty bad perf issues because of the placeholder images being loaded in the Games section; I spent a little time debugging but couldn't figure out a good solution so just let it as is.  Would obviously need to be addressed, but I think part of the problem is it's just loading large images.  It also seems to be re-fetching the image each time the hover event triggers, but not quite sure why that is yet.  Tried breaking the Game card out into its own component to avoid the re-trigger, but that didn't seem to solve the issue.  Fixed URLs / cached / preloaded images may resolve most of the issue.

- Positioning of title / about text on the game cards is entirely subjective, and would need to be evaluated based on the need to support localized text.  Likewise the CTA buttons / close button may need to be repositioned in more useable places.

- Nav Bar could be set up to scroll to individual section on the home page, or to separate pages entirely.

- Weird alignment bug with the Nav Bar where it's not centering at the same position with the rest of the content of the page - something to do with the positioning and the parallax wrappers probably.

- Didn't get around to doing a dedicated News page, but would have had to do a modal that just popped to full screen and listed off all of the news articles since I didn't have time to set up any sort of routing solution.

- All the white blocks behind the text is just to ensure readibility because the placeholder images are dynamic.  Real world graphics would be taken into account and the text made a legible color / positioned accordingly the compliment the graphics used.