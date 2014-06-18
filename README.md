###How to design an Email Template from Scratch

This is my attempt to follow a tutorial from scratch and design an email template

I am right now in the process of learning why designing an email template is important

####Why is coding HTML email a challenge?
   * Coding standards don’t exist
   * people continue to use Word fro creating e-mail messages because they believe it’s the best e-mail authoring experience around
   * There are way too many different type of email clients along with the fact that they could be using their email client on different type of browsers as well

####How to approach your work
   * Work Structurally first
      * building the structure first can help avoid many bugs and issues later down the track
   * Test often: every minor development milestone
      * Test using Litmus or Email on Acid
   * Validate Often
      * W3C validator
   * Sending your email
      * mailchimp
      * campaign monitor
   * Content, Development and Spam Scores
      * It is important to avoid typical spammy tactics
         * all caps
         * explanation points in subject
         * the words “free” “invest”
      * the cleaner the code the less likely your email will be marked as spam

###Diving into Development
   * Tools of the trade
      * Sublime text
      * litmus or email on acid
   * Starting with a good base
   * !DOCTYPE
      * A doctype
         * a line of code which informs the program reading it which HTML tags to expect and which set of rules the HTML and CSS adhere to
      * using an XHTML doctype
         * fewest quirks and inconstancies between documents
   ```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
    <html xmlns="http://www.w3.org/1999/xhtml">
    <head>
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
        <title>Demystifying Email Design</title>
        <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    </head>
</html>
   ```
   * Content tag
      * it is telling the destination rendering engine how to process text and special characters
      * you should still encode all the special characters  just to be safe
   * viewport tag
      * set the viewable area to the width of the device’s screen
      * also sets the initial scale to normal which is neither zoomed in or zoomed out
         * if you don’t do this, smartphones may scale your content down so that the content fits within the viewable area, and the text and images will be butting against the screen
   * MEANINGFUL TITLE

####Email is all about nesting tables
   * We can’t use divs, sections or articles…we can only use tables
   * Colspan or rowspan are not properly supported either

####Paragraphs or Cells?
   * we can’t really use standard tags like
      * h1, h2, h3
      * p
      * because they can be rendered very inconsistely across email clients
   * what can we do?
      * placed every block of text into its own cell and apply inline styling to that cell

####Inline style or stylesheets?
   * You can’t apply multiple classes to things in HTML email because it is not supported
   * Every element can have a maximum of one class
   * can not short hand
   * just do inline styles. It is much easier to troubleshoot

####Image Names and Spam Scores
   * Remember to make sure your images name are very meaningful so that the spam score will be higher

####Image Size
   * Use a compression app for your images to keep it below 250 kb
   * slow load time can make or break your email if the overall file size is too large

####Other Gotchas
   * Don’t leave anything up to the email clients
      * specify all widths
      * always set the size in pixels, then you can use percentages inside those containers if you want
