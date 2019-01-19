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
      <b>Name:</b><br/>
      <input type="text" name="name"><br/><br/>
      <b>Email:</b><br/>
      <input type="email" name="_replyto"><br/><br/>
      <b>Recipe Name:</b><br/>
      <input type="text" name="recipeName"><br/><br/>
      <b>Ingredients:</b><br/>
      <textarea rows="15" cols="75" name="ingredients">
      Ingredients:
      <ul>
        <li></li>
        <li></li>
        <li></li>
      </ul>
      </textarea><br/><br/>
      <b>Directions:</b><br/>
      <textarea rows="15" cols="75" name="directions"></textarea><br/><br/>
      <input type="submit" value="Send">
  </form>
  </body>
</html>
