---
layout: default
title: "Submit Recipe"
tags: submit,recipe,new
---
### Got a recipe you'd like us to try/add?



<html>
<head>
	<title>Contact us</title>
<!-- define some style elements-->
<!-- a helper script for vaidating the form-->

</head>

<body>
<h1>Submit Recipe</h1>
<form id="submitRecipe" action="https://formspree.io/craig.willett@gmail.com" method="POST">
  Name:<br/>
  <input type="text" name="name"><br/><br/>
  Email:<br/>
  <input type="email" name="_replyto"><br/><br/>
  Recipe Name:<br/>
  <input type="text" name="recipeName"><br/><br/>
  Ingredients:<br/>
  <textarea name="ingredients"><br/><br/>
  Directions:<br/>
  <textarea name="directions"><br/><br/>
  <input type="submit" value="Send">
</form>

</body>
</html>
