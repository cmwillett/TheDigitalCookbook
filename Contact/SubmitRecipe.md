---
layout: default
title: "Submit a Recipe"
tags: submit,recipe,new
---
<html>
  <head>
    <script>
      UPLOADCARE_PUBLIC_KEY = '99b1fd0d4ef0f45752e3';
      UPLOADCARE_IMAGES_ONLY = true;
    </script>
    <script src="https://ucarecdn.com/libs/widget/3.x/uploadcare.full.min.js"></script>
  </head>
  <body>
    <h1>Submit a Recipe</h1>
    <form id="submitRecipe" action="https://formspree.io/craig.willett@gmail.com" method="POST">
      <!--<input type="hidden" name="_subject" id="_subject" value="TDC New Recipe">-->
      <b>Name:</b><br/>
      <input type="text" name="Name"><br/><br/>
      <b>Email:</b><br/>
      <input type="email" name="_replyto"><br/><br/>
      <b>Recipe Name:</b><br/>
      <input type="text" name="_subject"><br/><br/>
      <b>Video URL (Optional):</b><br/>
      <input type="text" name="VideoUrl"><br/><br/>
      <b>Ingredients:</b><br/>
      <textarea rows="15" cols="75" name="Ingredients"></textarea><br/><br/>
      <b>Directions:</b><br/>
      <textarea rows="15" cols="75" name="Directions"></textarea><br/><br/>
      <b>Upload Pics: </b><input
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


<!-- The best place for this one is your <HEAD> tag -->


<!-- This is where the widget will be. Don't forget the name attribute! -->
