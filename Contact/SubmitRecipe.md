---
layout: default
title: "Submit a Recipe"
tags: submit,recipe,new
---
# Submit a Recipe
* If the recipe already exists and you just want to submit pictures for the recipe, just fill out the required fields (name, email, and recipe name); then upload the pictures.  

\*\* denotes required field...
<html>
  <head>
    <script>
      UPLOADCARE_PUBLIC_KEY = 'a1ed3bccd2792a8f47e6';
      UPLOADCARE_IMAGES_ONLY = true;
    </script>
    <script src="https://ucarecdn.com/libs/widget/3.x/uploadcare.full.min.js"></script>
  </head>
  <body>
    <!--<h1>Submit a Recipe</h1>-->
    <form id="submitRecipe" action="https://formspree.io/craig.willett@gmail.com" method="POST">
      <!--<input type="hidden" name="_subject" id="_subject" value="TDC New Recipe">-->
      <b><h3>**Name:</h3></b>
      <input type="text" name="Name" required><br/><br/>
      <b><h3>**Email:</h3></b>
      <input type="email" name="_replyto" required><br/><br/>
      <b><h3>**Recipe Name:</h3></b>
      <input type="text" name="_subject" required><br/><br/>
      <b><h3>Video URL (if applicable):</h3></b>
      <input type="text" name="VideoUrl"><br/><br/>
      <b><h3>Ingredients:</h3></b>
      <textarea rows="15" cols="75" name="Ingredients"></textarea><br/><br/>
      <b><h3>Directions:</h3></b>
      <textarea rows="15" cols="75" name="Directions"></textarea><br/><br/>
      <b><h3>Upload Pics: </h3></b><input
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
