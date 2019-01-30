---
layout: default
title: "Submit a Picture"
tags: submit,picture,contact,us
---
# Submit a Picture
* Want to submit a picture for a recipe already on the site?
* Go ahead and submit it below!

<html>
  <head>
  <script>
    UPLOADCARE_PUBLIC_KEY = 'a1ed3bccd2792a8f47e6';
    UPLOADCARE_IMAGES_ONLY = true;
  </script>
  <script src="https://ucarecdn.com/libs/widget/3.x/uploadcare.full.min.js"></script>
  </head>
  <body>
    <!--<h1>Submit an Issue</h1>-->
    <form id="submitPicture" action="https://formspree.io/craig.willett@gmail.com" method="POST">
      <!--<input type="hidden" name="_subject" id="_subject" value="TDC New Recipe">-->
      <b><h3>Name:</h3></b>
      <input type="text" name="Name" required><br/><br/>
      <b><h3>Email:</h3></b>
      <input type="email" name="_replyto" required><br/><br/>
      <b><h3>Recipe Name:</h3></b>
      <input type="text" name="_subject" required><br/><br/>
      <b><h3>Upload picture: </h3></b><input
        type="hidden"
        role="uploadcare-uploader"
        name="content"
        data-image-shrink="null"
        data-multiple="true"
        data-multiple-min="1"
        data-multiple-max="3" /><br/><br/>
      <input type="submit" value="Send">
  </form>
  </body>
</html>
