---
layout: default
title: "Give Feedback"
tags: give,feedback,contact,us
---
# Give Feedback
* Got some feedback for me?  Maybe a new "common search" you want added to the drop down?  Well tell me!

<html>
  <head>
    <script type="text/javascript">
     function concatenate(/*String*/string_one, /*String*/string_two, /*boolean*/with_space) {
      if (with_space===true) {
     return string_one+'-'+string_two;
      }
      else {
     return string_one+string_two;
      }
     }
     function join_names() {
      var input_topic = document.getElementsByName('topic')[0].value;
      var input_short_description = document.getElementsByName('short_description')[0].value;
      var var_input_subject = concatenate(input_topic, input_short_description, true);
      document.getElementsByName('_subject').value = var_input_subject;
     }
    </script>    
  </head>
  <body>
    <!--<h1>Give Feedback</h1>-->
    <form id="giveFeedback" action="https://formspree.io/craig.willett@gmail.com" method="POST">
      <input type="hidden" name="_subject" id="_subject" value="">
      <b><h3>Name:</h3></b>
      <input type="text" name="name" required><br/><br/>
      <b><h3>Email:</h3></b>
      <input type="email" name="_replyto" required><br/><br/>
      <b><h3>Topic:</h3></b>
      <select name="topic" required>
        <option value="">Choose a Topic</option>
        <option value="Complaint">Complaint</option>
        <option value="Idea">Idea</option>
        <option value="Kudos">Kudos</option>
        <option value="Question">Question</option>
        <option value="New Common Search">New Common Search Item</option>
      </select><br/><br/>
      <b><h3>Short Description:</h3></b>
      <input type="text" name="short_description" required><br/><br/>
      <b><h3>Description:</h3></b>
      <textarea rows="15" cols="75" name="Description" required></textarea><br/><br/>      
      <!--<b><h3>Feedback:</h3></b>
      <textarea rows="15" cols="75" name="Feedback" required></textarea><br/><br/>-->
      <input type="submit" onclick="join_names();" value="Send">
  </form>
  </body>
</html>
