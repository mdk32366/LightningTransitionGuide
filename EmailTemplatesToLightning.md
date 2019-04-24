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
  
 [Considerations for Using Classic Templates in Lightning](https://help.salesforce.com/articleView?id=classic_templates_in_lightning_considerations.htm&type=5)
 
#### When using Classic email templates in Lightning Experience, keep these considerations in mind.

REQUIRED EDITIONS
Available in: Lightning Experience
Available in: Personal, Group, Professional, Enterprise, Performance, Unlimited, and Developer Editions

The Lightning Email action layout must include the EmailTemplate field to display Classic email templates. The field is added by default to all Lightning Email action layouts.
To edit Classic email templates, use Classic Email Templates in Setup.

Externally linked CSS files are not supported. Although the CSS resource is displayed in the preview section in a Classic email template, most email clients don’t support externally linked CSS files.

##### Attachments
When sending an email that includes an email template, attachments from Classic email templates are read-only. Download an attachment to verify the content.
To change the attachments that are part of a Salesforce Classic email template, use Setup.
You can add an attachment to text, custom HTML, and letterhead email templates.
Note
NOTE The attachment must be in Salesforce Files.
You can't forward an attachment if:
The email is sent or received in Salesforce Classic
The email attachment is part of a Classic email template and the email is sent using Lightning email actions

##### Merge Fields
Merge fields in the email template are resolved when the template is inserted, based on the values in the Recipient and Related To fields. If you change the Recipient and Related To values after you insert the template, the email content doesn’t update.
Note
NOTE You don’t need to preview the template to see how it looks after the fields have merged.
You can’t add, edit, or remove merge fields using the merge field modal picklist.
Unresolved merge fields are blanked out when the template is inserted.
Text Email Templates
You can edit both the subject and the body.

##### Custom HTML Email Templates
The behavior is the same as it is in Salesforce Classic.

You can’t edit the subject or body.
You can’t pop out the email composer. The email must remain in docked mode.

##### Letterhead Email Templates
The behavior is the same as it is in Salesforce Classic.

You can edit the subject.
You can’t edit the header and footer.
Locked template sections remain locked and can’t be edited.

##### Visualforce Email Templates
The template is read-only.
Templates are sent with their dynamic and static attachments.
As with other email template attachments, dynamic attachments are in read-only mode and can’t be removed.
