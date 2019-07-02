# TROUVÉ

### Overview

Have you ever wanted to know what something is? This web application helps you identify “anything” when you provide it with an image. It also comes with a brief description complete with audio playback.

This is an easy to use mobile responsive application that allows for travellers to learn more about items that they may not know the name of on the fly. The audio playback feature is really important as it is just bad use of time to stare at a screen when you can be exploring the world. The audio functionality also serves the visually impaired.

Link to Trouvé: https://kinla.github.io/Trouve/.

##### Developers
* Nick Buadwal
* Sharon Chien
* Kai-Ann Fletcher
* Peiji Song

##### Contact Us
Please contact any one of our contributors by emailing trouveteam@trouve.ca.
We are in the process of working on guides and documentation to improve user education on our product.

- - -

### Demo
![demo](Trouvé.webm)
[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg)](http://www.youtube.com/watch?v=YOUTUBE_VIDEO_ID_HERE)

### Technologies
- HTML5
- CSS / Bootstrap
- JavaScript / JQuery
- Google Cloud Vision API
- MediaWiki API
- responsiveVoice.JS

- - -

### Technical Description

1. User chooses an image to upload.
   * There is no input validation. However, by using the `HTML5 <Input>`, we have specified `type="file"` and `accept="images/*"`. This then will hide all other file type while browsing for a file.

   * Automatically resize image to `max-width: 600px` / `max-height: 600p` and converts image data to `Base64` data URL through the use of `HTML5 <canvas>`.  

   * A `POST` request is sent to Google Cloud Vision API withThe `Base64` string without the data tag as part of the data. The request also specifics returning only one `Web Entities`.
      * Calls next API - MediaWiki API.

   * The MediaWiki API takes the `description` of the top scoring entity as the `title` of the query string and sends off the request by `GET` method. If there is a page found on Wikipedia, the page content would return as a response.
   
2. The UI is polulated with the `title` and a shortened Wikipedia page content as the `description`.
3. The user can opt to listen to the `description` using the `play` button just below the `description`. This functionality is enabled through the use of responsiveVoice.JS.
   * `pause` and `stop` functions are also available.
4. User history can be accessed via the `history` page.
   * Currently, only the `title` and `description` of each search has been saved in localStorage.
   * The user can click on a button which is named after the `title` of an historical search. This will then populate the display area with the `title` and the `description`. 
   * Audio playback works on this page.

- - -

### Improvements
1. Make audio buttons LARGER on mobile devices.
2. Better UI design for favorite/history page. Currently half finished.
3. User specific search history / favorites that is linked to personal accounts on a server database and allow for user deletion of these items.
4. Multi-language support.
5. Cleaner codes especially management of JS/CSS files
6. See if another text-audio API or JS library will allow for better audio UI design, namely toggle play/pause button instead of two seperate buttons.
7. See if another audio API / JS libaray will allow for smoother voice playback.
8.Introduce a loader icon that indicates to the user that text is going to be returned to the DOM once the image is uploaded - improves user experience so they don’t wait indefinitely for text to appear.
9. Shorten the response time of Google Cloud Vision API if possible.
10. Develop this into a mobile app.










