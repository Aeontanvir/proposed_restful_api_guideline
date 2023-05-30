# Restful API Best Practices

RESTful API best practices include: meaningful resource endpoints, proper HTTP verbs, clear error handling, pagination and filtering, content negotiation, secure authentication and authorization, versioning, comprehensive documentation, performance optimization, and adherence to naming conventions and REST constraints.

## Table of Content

1. Preface
2. Overview
    1. Brief Overview
    2. Where the State comes from
3. Characteristics and Constraints of RESTful Server
4. Key Points to Remember
5. Understanding RESTful API verbs
6. Planning a RESTful API
7. Uniform Interface
8. Design Pattern of Uniform Interfaces (aka Endpoints)
    1. Overview
    2. Basic Design Patterns
9. Request and Response Format
10. Exception Handling and Error Response Format



## How to use this Document

1. HEADING NUMBERINGS: This document uses the following Google Docs Add-on (see the Add-ons menu in the menu bar) to generate the heading numberings automatically. After you have added a new heading, please use this Add-on to re-update the heading numbers. The Add-on appears as a right-side sidebar.
2. BOOKMARKS: In order to refer to specific places in this document from other tools like JIRA/Wrike/Trello, please use the bookmark feature. To create, place cursor at the place (except any heading since heading bookmarks get replaced by the TOC add-on) for which you want to create a bookmark and from Insert menu, select Bookmark. If any bookmark  link doesn't work any more, re-create the bookmark and use the new link.
3. TABLE OF CONTENT REFRESH: If you have added any heading/subheading, please remember to update the heading numbers first (follow the instructions above in item #1) and then refresh the Table of Content above, too.
4. CODE SNIPPETS FORMATTING: To format code snippets, please use the Add-on "Code Pretty" from Add-ons menu (install it if you don't have it). First, to remove source application formattings,  copy-paste your text to any plain text editor. Then from the plain text editor, copy paste to this document. Then select the text and select the Add-ons > Code Pretty > Format Selection menu option.
5. CHAT OR EMAIL SNIPPETS FORMATTING: To format chat or email snippets, just use the Consolas font. First, to remove source application formattings,  copy-paste your text to any plain text editor. Then from the plain text editor, copy paste to this document. Then select the text and then select the Consolas font from the Font drop-down menu in the toolbar. You should use font size 8 for such snippets.
6. PAGE NUMBERS: Page numbers appear at the top-right corner of each page.
7. TABLES: For tables, please use the color scheme for heading given in the sample table. You should use font size 8 for all of the table's content, except the header, which will be in regular font size 10.
8. STAND-OUT TEXT: Please use the color "cornflower blue" from the font colors menu for any stand-out text.
9. ANY COPY-PASTE: In order to not disrupt the formattings of this document, please don't do any copy-paste directly to this document. First paste the content to any plain text editor so that any source formatting is removed and then copy it again from the editor and paste to this document.
10. COMMENTING: To comment and discuss on any part of text of the document, please select the text and use the Ctrl-Alt-M commenting feature.



# Preface

In this document I am writing a very basic RESTful API and  common patterns and best practices followed by industry for designing a RESTful API. Best practices are  dictated by use cases, problem spaces, preferences and way of solving problems. I am welcoming everybody for feedback and suggestions. I am all ears.




