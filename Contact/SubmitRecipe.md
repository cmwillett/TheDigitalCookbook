---
layout: default
title: "Submit a Recipe"
tags: submit,recipe,new
---
<html>
  <head>
  </head>
  <body>
    <h1>Submit a Recipe</h1>
    <form id="submitRecipe" action="https://formspree.io/craig.willett@gmail.com" method="POST">
      <input type="hidden" name="_subject" id="_subject" value="TDC New Recipe">
      <b>Name:</b><br/>
      <input type="text" name="Name" required><br/><br/>
      <b>Email:</b><br/>
      <input type="email" name="_replyto" required><br/><br/>
      <b>Recipe Name:</b><br/>
      <input type="text" name="RecipeName" required><br/><br/>
      <b>Video URL (Optional):</b><br/>
      <input type="text" name="VideoUrl"><br/><br/>
      <b>Ingredients:</b><br/>
      <textarea rows="15" cols="75" name="Ingredients" required></textarea><br/><br/>
      <b>Directions:</b><br/>
      <textarea rows="15" cols="75" name="Directions" required></textarea><br/><br/>
      <input type="submit" value="Send">
  </form>
  </body>
</html>
