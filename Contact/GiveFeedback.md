---
layout: default
title: "Give Feedback"
tags: give,feedback,contact
---
# Give Feedback
<html>
  <head>
  </head>
  <body>
    <!--<h1>Give Feedback</h1>-->
    <form id="giveFeedback" action="https://formspree.io/craig.willett@gmail.com" method="POST">
      <!--<input type="hidden" name="_subject" id="_subject" value="TDC New Recipe">-->
      <b><h3>Name:</h3></b><br/>
      <input type="text" name="_subject" required><br/><br/>
      <b><h3>Email:</h3></b><br/>
      <input type="email" name="_replyto" required><br/><br/>
      <b><h3>Feedback:</h3></b><br/>
      <textarea rows="15" cols="75" name="Feedback" required></textarea><br/><br/>
      <input type="submit" value="Send">
  </form>
  </body>
</html>
