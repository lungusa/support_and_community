
https://www.lung.org/support-and-community/
SUPPORT AND COMMUNITY



START: CHANGES REGARDING THE "FIND LOCAL SUPPORT" section:::::::::::

 - https://www.lung.org/local-content/florida/fl-local-content.xml?state=FL was initially used as a hybrid ajax call. it as not used because not every state had the addresses laid out

 - the content type "LOCAL SUPPORT" using a list item did NOT work because it would list every single office nationwide. it was not selecting based off of the state. the Support And Community landing page was not built for that

 - https://www.lung.org/all-items.xml?related_state=NY did not work initially because there were two different types `<localassoc_item>` and `<localsupport_item>`
 - even though "lung.org / local content / content items / about us / local associations office" has EVERY SINGLE office, only the ones listed as MAIN were showing up in the "localassoc_item" list. this was because of a display template's `<t:if test="main_state != null">` statement. this was in the content type "LOCAL ASSOCIATION OFFICE" with display template "LIST OF LOCAL ASSOCIATIONS ITEMS NO FILTER - XML"
 - THUS A NEW DISPLAY TEMPLATE for the content type of "LOCAL ASSOCIATION OFFICE" was created called "ALL LOCAL ASSOCIATIONS" with no `<t:if>`
 - ADDITIONALLY a change was made to the content type "XML DOCUMENT" within the display template "ALL - items no filter - XML"
 - under the section `<localassoc_page_items>` I added `<t:include id="templatelist-916041975"/>` which employs the new template "ALL LOCAL ASSOCATIONS" that does not have the `<t:if test="main_state != null">` statement.

 - within the content type "Landing page - Support & Community", the display template "Support Community" was changed.
 - it contains an AJAX call where the `ALL-ITEMS.xml` file is called and sets up the formatting and "show more" feature based on how many offices there are.


 END: CHANGES REGARDING THE "FIND LOCAL SUPPORT" section:::::::::::
