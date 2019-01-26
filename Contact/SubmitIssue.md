---
layout: default
title: "Submit an Issue"
tags: submit,issue,new,defect
---
# Submit an Issue
* Find an issue on the site?  A broken link?  Misspelled word?

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
    <form id="submitIssue" action="https://formspree.io/craig.willett@gmail.com" method="POST">
      <!--<input type="hidden" name="_subject" id="_subject" value="TDC New Recipe">-->
      <b><h3>Name:</h3></b>
      <input type="text" name="Name" required><br/><br/>
      <b><h3>Email:</h3></b>
      <input type="email" name="_replyto" required><br/><br/>
      <b><h3>Short Description:</h3></b>
      <input type="text" name="_subject" required><br/><br/>
      <b><h3>Description:</h3></b>
      <textarea rows="15" cols="75" name="Description" required></textarea><br/><br/>
      <b><h3>Upload any images: </h3></b><input
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
