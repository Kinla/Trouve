# TROUVÉ

### Overview

Have you ever wanted to know what something is? This web application helps you identify “anything” when you provide it with an image. It also comes with a brief description complete with audio playback. 

Link to Trouvé: https://kaiannfletcher.github.io/Team04-Project01/

##### Team Members
* Sharon Chien
* Kai-Ann Fletcher
* Peiji Song

- - -

### Technologies
- HTML5
- CSS / Bootstrap
- JavaScript / JQuery
- Google Cloud Vision API
- MediaWiki API
- responsiveVoice.JS

- - -

### Process

1. User chooses an image to upload.
   * There is no input validation. However, by using the `HTML5 <Input>`, we have specified `type="file"` and `accept="images/*"`. This then will hide all other file type while browsing for a file.

   * Automatically resize image to `max-width: 600px` / `max-height: 600p` and converts image data to `Base64` data URL through the use of `HTML5 <canvas>`.  

   * A `POST` request is sent to Google Cloud Vision API withThe `Base64` string without the data tag as part of the data. The request also specifics returning only one `Web Entities`.
      * Calls next API - MediaWiki API.

   * The MediaWiki API takes the `description` of the top scoring entity as the `title` of the query string and sends off the request by `GET` method. If there is a page found on Wikipedia, the page content would return as a response.
   
2. The UI is polulated with the `title` and a shortened Wikipedia page content as the `description`.
3. The user can opt to listen to the `description` using the `play` button just below the `description`. This functionality is enabled by responsiveVoice.JS.
   * `pause` and `stop` functions for audio is also available.

A Javascript audio library (responsiveVoice) was implemented to then handle the audio playback of the description. Your search history is then stored in local storage and pulled to the page for easy access in future.

Why is this project useful?

Our code is also mobile-responsive. This means it functions well in mobile and other small devices. It is accessibility-friendly with the audio playback to accommodate the visually-impaired.

How can users get started with the project?

Simply find an image you want to know more about and upload it :) Our application does the rest of the work for you :) Enjoy!!

Where can users get help?
Please contact any one of our contributors by emailing trouveteam@trouve.ca.
We are in the process of working on guides and documentation to improve user education on our product.

Who maintains and contributes to this project?

Here is a list of the individual developers of this project:
1) Sharon Chien
2) Peiji Song
3) Nick Buadwal
4) Kai-Ann Fletcher

Improvements to come (Roadmap):
Make audio buttons LARGER on mobile devices.
Better UI design for favorite/history page. Currently half finished.
User specific search history / favorites that is linked to firebase and allow for user deletion of these items.
Multi-language support.
Cleaner codes especially management of JS/CSS files
See if another text-audio API or JS library will allow for better audio UI design, namely toggle play/pause button instead of two seperate buttons.
Introduce a loader icon that indicates to the user that text is going to be returned to the DOM once the image is uploaded - improves user experience so they don’t wait indefinitely for text to appear.
Better understanding of what makes an app “lightweight” and apply it.
Develop this into a mobile app.










