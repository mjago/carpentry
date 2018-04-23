---
title: Contact
layout: page
permalink: /contact_2/
---

## Cian Burfoot
Lincoln <br>
UK <br>
Tel: 07734 567890

## Enter your email address and I will reply as soon as possible:
<!--
     After implementing this contact form make sure
     1. you have defined "email: youremail@email.com" in _config.yml file.
     2. you verify your form on formspree.io.
-->

<form class="wj-contact" action="https://formspree.io/{{site.email}}" method="POST">
    <input type="text" name="email" placeholder="Email Address">
    <textarea type="text" name="content" rows="10" placeholder="Message"></textarea>
    <input type="hidden" name="_next" value="/">
    <input type="hidden" name="_subject" value="New Contact Form Submission">
    <input type="submit" value="Submit">
</form>

<script>
// this script will automatically fill text field
// depending on what's passed in the url
var fillForm = function () {
    var queryString = document.location.search.split("+").join(" ");
    var params = {}, tokens, re = /[?&]?([^=]+)=([^&]*)/g;
    while (tokens = re.exec(queryString)) {
        params[decodeURIComponent(tokens[1])] = decodeURIComponent(tokens[2]);
    }
    if (params.n == undefined || params.p == undefined){
        // no value in the query string
        // here you have to manage this use case : redirect or print a message to user
    }else{
        // filling form fields with query string values
        document.getElementsByName('content')[0].value = params.p + " (ref: " + params.n + ")\n\n";
    }
} ();
</script>

<style>
form.wj-contact input[type="text"], form.wj-contact textarea[type="text"] {
    width: 100%;
    vertical-align: middle;
    margin-top: 0.25em;
    margin-bottom: 0.5em;
    padding: 0.75em;
    font-family: monospace, sans-serif;
    font-weight: lighter;
    border-style: solid;
    border-color: #444;
    outline-color: #2e83e6;
    border-width: 1px;
    border-radius: 3px;
    transition: box-shadow .2s ease;
}

form.wj-contact input[type="submit"] {
    outline: none;
    color: white;
        background-color: #2e83e6;
    border-radius: 3px;
    padding: 0.5em;
    margin: 0.25em 0 0 0;
    border: 1px solid transparent;
    height: auto;
}
</style>
