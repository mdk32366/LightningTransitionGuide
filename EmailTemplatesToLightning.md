### [Use Classic Templates in Lightning](https://help.salesforce.com/articleView?id=classic_templates_in_lightning.htm&type=5)

Use Your Classic Email Templates in Lightning Experience
Leverage all the work and planning that went into your Salesforce Classic email templates by using the same templates in Lightning Experience. You can use your Text, Custom HTML, Letterhead, and Visualforce email templates in Lightning Experience.

REQUIRED EDITIONS
Available in: Lightning Experience
Available in: Personal, Group, Professional, Enterprise, Performance, Unlimited, and Developer Editions


#### When you insert an email template, change the filter to Classic Email Templates.


Issues:

It's true that it's possible to continue to use Classic email templates in Lightning. They're located in Setup > Email > Classic Email Templates. However, I think Patrinia is trying to convert their Classic templates to Lightning templates. I was just starting to do the same thing as I just discovered the Email Templates object and the ability to edit the source code.

The issue as you'll see in Patrinia's example is that the template begins with a <style> section. Lightning currently indicates that it doesn't support predefined styles and probably only permits in-line styles. This is a no-go for most of our templates, too, because we rely on the ability to custom design some elements of our emails, at least for the recipients whose email clients support it.

We may need to migrate this inquiry to an Idea to get more attention.

This sort of thing in the template:

<style type="text/css">   
    #outlook a{padding:0;} /* Force Outlook to provide a "view in browser" button. */
    /* Resets: see reset.css for details */
    .ReadMsgBody { width: 100%; background-color: #ebebeb;}
    .ExternalClass {width: 100%; background-color: #ebebeb;}
    .ExternalClass, .ExternalClass p, .ExternalClass span, .ExternalClass font, .ExternalClass td, .ExternalClass div {line-height:100%;}
    body {-webkit-text-size-adjust:none; -ms-text-size-adjust:none;}
    body {margin:0; padding:0;}
    table {border-spacing:0;}
    table td {border-collapse:separate;}
     /*table.container{border:1px solid #dddddd;}*/ /* Remove star and slash from either side to add border*/
    .yshortcuts a {border-bottom: none !important;}
 
 Is not allowed.  The new Lightning Templates do not allow the <Style> element.  It's currently a requested feature.
  
  See:  https://success.salesforce.com/answers?id=9063A000000pRUFQA2
  
  
