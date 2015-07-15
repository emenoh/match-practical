#List of changes as requested in instructions.txt
###Author: James Hatfield


##Basic code typos corrected
1. in index.html I saw an error in the console, so went and saw that the argument being passed to the requestJSON function was spelled incorrectly. After fixing this I was able to see the GitHub API JSON response data coming back.

    |- requestJSON(requri, function(Json) {
    
    |+ requestJSON(requri, function(json) {

2. In styles.css there was an extra left bracket: '{' that I found by running a CSS Lint on the file (http://csslint.net/).

    |- html, body, div, span, applet, object, iframe, h1, h2, h3, h4, h5, h6, p, blockquote, pre, a, abbr, acronym, address, big, cite, code, del, dfn, em, img, ins, kbd, q, s, samp, small, strike, strong, sub, sup, tt, var, b, u, i, center, dl, dt, dd, ol, ul, li, fieldset, form, label, legend, table, caption, tbody, tfoot, thead, tr, th, td, article, aside, canvas, details, embed, figure, figcaption, footer, header, hgroup, menu, nav, output, ruby, section, summary, time, mark, audio, video {
{

    |+ html, body, div, span, applet, object, iframe, h1, h2, h3, h4, h5, h6, p, blockquote, pre, a, abbr, acronym, address, big, cite, code, del, dfn, em, img, ins, kbd, q, s, samp, small, strike, strong, sub, sup, tt, var, b, u, i, center, dl, dt, dd, ol, ul, li, fieldset, form, label, legend, table, caption, tbody, tfoot, thead, tr, th, td, article, aside, canvas, details, embed, figure, figcaption, footer, header, hgroup, menu, nav, output, ruby, section, summary, time, mark, audio, video {

That fixed the breaking bugs.



##New Features plus Refactoring
User Stories 1, 2
"can you make the enter key trigger a search (but, only
when entering text in the search box)."

1. Changed the event handler from a click to a submit to capture both submit button clicks as well as enter key form submits. This required changing the html to use an actual form with a button element rather than just an orphaned input elment and an anchor tag.

2. I did go ahead and refactor the code to have the contents of the event handler call a function rather than putting all the code inside the event callback.

User Story 3
"Optional extra credit: don't search for
the same username twice."

3. I added a conditional check to the entire main code block and added a 'currentUserName' cache variable outside of it. After the main code block runs for the first time the currentUserName variable is populated. On the next run of the main code block it now checks to see if the value from the form input elment 'username' is the same as the cached value before running again (I added a console message for this exercise to show you that they match and let you know that "you just searched for that user...").

Use Stories 4, 5
"we need to add the user's email address as a clickable link to the page,
as well as a link to their blog, if available.""

4. Added the email key from the JSON API response to the list of variables available to thesimple html template function. Added a conditional block to append the email address as an anchor tag/string to 'outhtml'.

5.  Added the blog key from the JSON API response to the list of variables available to thesimple html template function. Added a conditional block to append the blog address as an anchor tag/string to 'outhtml'.


