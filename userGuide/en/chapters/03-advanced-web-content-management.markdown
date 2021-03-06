
# Advanced Web Content Management   

In the previous chapter we looked at some basic ways you can use Liferay to
handle your web content. In this chapter we'll delve deeper into slightly more
complex web content management techniques. But don't be alarmed, it's not too
intense. We'll cover the following topics:

- Web content structures and templates
- Leveraging Liferay's multi-site capabilities
- Using page templates and site templates
- Allowing users to customize site pages
- Staging
- Creating teams to allow for flexible management of site permissions
- Mobile device rules

We'll examine how web content structures and templates provide additional power
and flexibility to the web content management system we saw in chapter 2. You'll
also learn how easy it is to set up and administer multiple sites in Liferay.
Next, we'll learn how you can empower your users to create personal
customizations of site pages. We'll also examine how you can use staging to
manage the publication of pages and content on your site. Well conclude with
sections on creating teams and rules for presenting site pages to mobile
devices. Once finished with this chapter, you'll be the envy of your peers as
they'll think you really know what you're doing.

## Advanced content with structures and templates  

If you've ever launched a web site, you know that as it grows, you can
experience growing pains. This is the case especially if you've given lots of
people access to the site to make whatever changes they need to make. Without
preset limitations, users can display content in any order and in any manner
they desire (think huge, flashing letters in a font nobody can read). Content
can get stale, especially if those responsible for it don't maintain it like
they should. And sometimes, content is published that should never have seen the
light of day.

Thankfully, Liferay WCM helps you handle all of those situations. You can use
*Structures* to define which fields are available to users when they create
content. These can be coupled with *Templates* that define how to display that
content. Content won't get stale, because you can take advantage of the
*Scheduling* feature to determine when content is displayed and when it's
removed. Additionally, you can configure Liferay's built-in *Workflow* system to
set up a review and publishing process so only what you want winds up on the
live site. Liferay Portal gives you the management tools you need to run
everything from a simple, one-page web site to an enormous, content-rich site.

All of this starts with structures.

### Using structures  

Structures are the foundation for web content. They determine which fields are
available to users as they create new items for display. Structures not only
improve manageability for the administrator, they also make it much easier for
users to quickly add content.

For example, say you're managing an online news magazine. All your articles need
to contain the same types of information: a title, a subtitle, an author and one
or more pages of text and images that comprise the body of the article. If
Liferay only supported simple content as has been described above, you'd have no
way to make sure your users entered a title, subtitle, and author. You might
also get articles that don't match the look and feel of your site. If titles are
supposed to be navy blue but they come in from your writers manually set to
light blue, you need to spend time reformatting them before they are published.

Structures give you the ability to provide a format for your content so your
users know what needs to be entered to have a complete article. Using
structures, you can provide a form for your users which spells out exactly what
is required and can be formatted automatically using a template.

You create a structure by adding form controls such as text fields, text boxes,
text areas (HTML), check boxes, select boxes and multi-selection lists. Also you
can add specialized, Liferay-specific application fields such as an Image
Uploader and Documents and Media right onto the structure. Furthermore, you can
move the elements around by dragging them where you want them. This makes it
easy for you to prototype different orders for your input fields. Additionally,
elements can be grouped together into blocks which can then be repeatable.
Template writers can then write a template which loops through these blocks and
presents your content in innovative ways, such as in sliding navigation bars,
content which scrolls with the user and more.

Let's look at how we can create and edit structures through the Manage
Structures interface.

#### Editing structures

Go back to the Control Panel and select *Web Content* from the content section.
The first way to access the Manage Structures interface is simply by clicking
*Manage* &rarr; *Structures*. This opens a popup showing all the web content
structures that exist in your currently selected scope. Here, you can add new
web content structures, edit existing ones, manage the templates associated with
a structure, edit the permissions of a structure, and copy or delete structures.

Copying web content structures can be useful if you'd like to create a new web
content structure that's similar to an existing one, but you don't want to start
from scratch. Liferay generates a unique portal ID for the copied structure, but
every other attribute of the copied structure, including the name, is the same
as that of the original. Once you've copied a web content structure, you should
enter a new name for it to avoid confusing it with the original. When you copy a
web content structure, you'll be prompted to choose whether to copy any detail
templates or list templates associated with the structure. For information on
detail templates and list templates, please refer to chapter 9 on [Dynamic Data
Lists](https://www.liferay.com/documentation/liferay-portal/6.1/user-guide/-/ai/dynamic-data-lists-in-liferay).

![Figure 3.1: You can access the Manage Structures interface by clicking *Manage* &rarr; *Structures* from the Web Content page of the Control Panel.](../../images/manage-structures.png)

The second way to access the Manage Structures interface is directly from the
web content article WYSIWYG editor. Click *Add* &rarr; *Basic Web Content* from
the Web Content page to add another piece of content to your portal. Instead of
going right for the content, this time we'll first create a structure. To access
the Manage Structures interface, simply click on *Select* next to the
*Structure* heading near the top of the page. To create a new structure in your
chosen scope, simply click on the *Add* button in the Manage Structures popup.

It's very easy to create and edit structures: all you have to do is drag
elements into the structure and then give them names. For instance, select the
*Text* element and drag it onto the structure. You can do the same with any of
the elements. To remove it from the structure, simply select the *Delete* icon
(red X) in the upper right corner of the element. You also have the ability to
duplicate the element, which can be done by selecting the *Duplicate* button.
We'll explain the *Edit* button later.

Web content structures also have the capability of inheriting characteristics
from other structures. When a parent structure is configured, the child
structure inherits the parent's fields and settings. Using this feature is
helpful when you want to make a similar structure to one that already exists.
For example, if you'd like to create an in-depth Nose-ster sports article in
addition to a regular Nose-ster sports article, you can simply inherit the
characteristics of the regular article and only add additional fields to the
more in-depth article. When the in-depth article is configured, it will display
its parent's fields in addition to its own fields.

Another method to edit your structure is switching to *Source* mode and manually
customizing your structure by editing its XML file. You'll notice by default the
*View* mode is selected. Click the *Source* tab to switch to Source mode. This
method is for the more experienced developers.

Take a moment to add, delete, and rearrange different elements.

![Figure 3.2: The structure editor gives you many options to customize your Web Content.](../../images/04-web-content-structure-editor.png)

Liferay supports the following fields in structures:

**Boolean:** Adds a checkbox onto your structure, which stores either `true`
(checked) or `false` (unchecked). Template developers can use this as a display
rule.

**Date:** Adds a preformatted text field that displays a convenient date picker
to assist in selecting the desired data. The format for the date is governed by
the current locale.

**Decimal:** Similar to *Number*, except that it required a decimal point (.) be
present.

**Documents and Media:** Adds the Documents and Media folder hierarchy to your
structure.

**File Upload:** Uploads a document to attach. Uploads are stored in Documents
and Media, in an existing folder or in the user's default upload action.

**HTML:** An area that uses a WYSIWYG editor to enhance the content.

**Image:** Adds the browse image application into your structure.

**Integer:** Similar to *Number*, except that it constrains user input to
non-fractional numbers.

**Link to Page:** Inserts a link to another page in the same site.

**Number:** Presents a text box that only accepts numbers as inputs, but puts no
constraints on the kind of number entered.

**Radio:** Presents the user with a list of options to choose from using radio
button inputs.

**Select:** Presents a selection of options for the user to choose from using a
combo box. Can be configured to allow multiple selections, unlike *Radio*.

**Text:** Used for items such as titles and headings.

**Text Box:** Used for the body of your content or long descriptions.

These fields provide all you need to model any information type you would
want to use as web content. Liferay customers have used structures to model
everything from articles, to video metadata, to databases of wildlife. You're
limited only by your imagination. To fire that imagination, let's look more
closely at field settings.

#### Editing field settings  

When creating a new structure, it is essential that you set variable names.
Template writers can use these variables to refer to elements on your form. If
you don't set variable names, Liferay generates random variable names and these
can be difficult for a template writer to follow. For example, consider a field
called *Author*. You might create this field in your form but the underlying
variable name in the structure might look something like `TextField4882`. The
template writer needs to create markup for your structure and place the Author
field in a certain spot in the markup. How will he or she know which field is
Author when they're all named randomly?

To solve this problem, all you need to do is set a variable name for each field
as you add it to your structure. Let's do this now. In your structure, add an
element *HTML*. To change its field label and variable name, you'll need to
access the field's settings. Click on the field and select the gear icon that
appears in the upper right corner. Change the *Field Label* value to
*Instructions* and the *Name* value (variable name) to `Steps`. Now your
template writer has a variable by which he or she can refer to this field.

Here's a list of all the configurable settings available for a structure's
fields:

**Type:** Lists the type of field placed in the definition. This is not editable
but is available to reference from a template.

**Field Label:** Sets the text that can be displayed with the field. This is the
human-readable text that the user sees.

**Show Label:** Select *Yes* to display the Field Label.

**Required:** Select *Yes* to mark the field required. If a field is required,
users must enter a value for it in order to submit content using this structure.

**Name:** The name of the field internally, automatically generated. Since this
is the variable name that you can read the data from in a template, you should
give a more memorable name here.

**Predefined Value:** Specifying predefined values for structure forms is a way
to specify defaults. When a user creates a new web content article based on a
structure that has predefined values for various fields, the predefined values
appear in the form as defaults for those fields.

**Tip:** Each field can have a small help icon, with a tooltip attached that
displays helpful information. If you would like to provide text for the tooltip
you may enter it here.

**Indexable:** Select *Yes* to enable Liferay to index your field for search.

**Repeatable:** Select *Yes* to make your field repeatable. Your users can then
add as many copies of this field as they like. For example, if you're creating a
structure for articles, you might want a repeatable Author field in case you
have multiple authors for a particular article.

**Width:** Changes the width of the field. The field width can be *small*,
*medium*, or *large* (not available for Boolean, Documents and Media, Image,
Radio, and Select.

**Allowed File Extensions:** Specifies the file types allowed for upload (e.g.
*pdf*, *html*, *txt*, etc.). Set this value to a comma-delimited list of
extensions, including the character ., and Liferay checks the extension before
the file can be uploaded. To allow all file types, input an asterisk: "\*" (only
available for File Upload).

**Multiple:** Select *Yes* to enable a multi-selection list (only available for
Select).

**Options:** Changes the options available for selection. You're able to add and
remove options as well as edit each individual option's display name and value
(only available for Radio and Select).

**Read Only:** Select *Yes* to disable the ability to modify or delete uploaded
files (only available for File Upload).

For the Nose-ster structure, type something in the *Tip* field that helps users
know what to put into the Body element (example: *This is an HTML text area for
the body of your content*). Now, when users hover over the Help icon near your
title, your tip is displayed.

##### Structure Default Values

Structure Default Values allow you to create one structure that uses common data
from multiple articles. Returning to our newspaper scenario again, let's say you
want all sports articles to have the same display page (sports page), the same
categories, or the same set of tags. Instead of adding them for each article or
wondering if your users are adding them to each article, you can add these
characteristics once for every sports article by creating default values for the
structure. There are two ways to edit structure default values: creating a new
structure or editing an existing structure.

For a new structure, you must first create the structure before editing its
default values. Navigate to *Web Content* in the Control Panel and click the
*Structures* tab, then select the *Add Structure* button. Under the *XML Schema
Definition* section of the new structure form, use the *Add Row* button to
create different types of fields for the structure. Or you can use the editor to
create the structure manually: the Launch Editor button allows you to edit the
XML for the structure if you wish to do it via code. When you are done, click
*Save and Continue* to go to the Structure Default Values form.

![Figure 3.3: You can create fields for structure default values via the XML Schema Definition section of the new structure form.](../../images/xml-schema-definitions-new.png)

To edit an existing structure, go to *Web Content* in the Control Panel and
click the *Structures* tab to see the structures list. Find the *Actions* button
for the desired structure and select *Edit Default Values* from the menu to view
a window like the one below. This form allows you to manage the structure
settings.

![Figure 3.4: You can edit default values via the Actions button of the structure form.](../../images/structure-default-values.png)

Every new web content you create with this structure is preloaded with the
data you inserted.

#### Assigning permissions  

Setting permissions on structures is done using the same procedure as
permissions everywhere else in Liferay. Most users should not have the ability
to edit structures. Structures are coupled with templates, which require some
web development knowledge to create. This is why only trusted developers should
be able to create structures and templates. Users, of course, should be able to
view structures. The *View* permission enables them to make use of the
structures to create content.

![Figure 3.5: View Permissions for a Structure](../../images/04-web-content-structure-permissions.png)

You can grant or deny permissions based on Roles and this is the recommended way
to handle permissions for structures.

Now that you understand what structures are used for, you need to understand the
other half of Liferay's web content management system: templates.

### Using templates  

Developers create templates to display the elements of the structure in the
markup they want. Content can then be styled properly using CSS, because markup
is generated consistently by the template when structured content is displayed.
In essence, templates are scripts that tell Liferay how to display content in
the structure. Any changes to the structure require corresponding changes to the
template, because new or deleted fields produce errors on the page. If users
enter content into a structure, it *must* have a matching template. Without a
template, the portal has no idea how to display content which has been created
using a custom structure.

Let's look more closely at the types of templates Liferay supports.

#### Template Types (FTL, VM, XSL, and CSS)  

Liferay supports templates written in four different templating languages, to
support the skill sets of the largest number of developers. This increases the
chances you can jump right in and use whichever one you've already used before.
If you haven't yet been exposed to any of them, your best bet is FreeMarker or
Velocity, as they are less "chatty" than XSL and extremely simple to
understand.

**FTL** (FreeMarker Template Language): Freemarker is a templating language
which could be considered a successor to Velocity. It has some advantages over
Velocity for which it sacrifices some simplicity, yet it is still easy to use. If
you haven't used any of the template languages before, we recommend using
FreeMarker: you'll get up to speed the fastest.

**VM** (Velocity Macro): Velocity is a scripting language that lets you mix
logic with HTML. This is similar to other scripting languages, such as PHP,
though Velocity is much simpler.

**XSL** (Extensible Style Sheet Language): XSL is used in Liferay templates to
transform the underlying XML of a structure into markup suitable for the
browser. While it may not be as clean and compact as Velocity or FTL, it's
widely used for transforming XML into other formats and it's very likely your
developers have already been exposed to it.

**CSS** (Cascading Style Sheets): You can use CSS if your structure is very
straightforward and modifications are simple (colors, fonts, layouts, etc.). If
your structure is more complex, however, you'll need to use one of the other
options.

<!-- CSS was not available during testing of 6.2 feature. Need to find out if
this is planned or if CSS category is still being developed. -->

#### Adding templates

Liferay WCM makes it easy to create structures, templates, and content from the
same interface. Let's go through the entire flow of how you'd create a
structure, link it to a template and then create content using them both. We'll
use FreeMarker for our template and we'll lay out the structure fields
systematically to go along with the format we've defined for our content.

![Figure 3.6: You can create a new Web Content template by browsing a pre-made template or creating one in the script editor.](../../images/04-web-content-templates-create.png)

1. Go back to the Web Content section of the Control Panel and click *Add*
&rarr; *Basic Web Content*.
2. Click *Select* next to the Structures heading to access the Manage Structures
interface.
3. Click on the *Add* button.
4. Name the structure *News Article* and add the following fields:

| Field Type | &nbsp;Field Label | &nbsp;Name |
--------- | ---------- | ---------- |
 Text  | &nbsp;Title | &nbsp;`title` |
 Text Box | &nbsp;Abstract | &nbsp;`abstract` |
 Documents and Media | &nbsp;Image | &nbsp;`image` |
 HTML | &nbsp;Body | &nbsp;`body` |

5. Click *Save*.
6. In the Manage Structures interface, click *Choose* next to the News Article
structure that you created.
7. In the New Web Content form, click *Select* next to the Template heading to
access the Manage Templates interface.
8. Click *Add*, enter the name *News Article*, and add a description.
9. Make sure FreeMarker is selected as the script language (it's the default).
10. If you've written the script beforehand, you can select *Browse* to upload
it from your machine. Otherwise, you can type the script directly into the
script editor window.
11. Click *Save*.
12. Exit the Manage Templates interface and click *Select* next to the Template
heading again.
13. Click *Choose* next to the News Article template you created.
14. On the New Web Content form, you'll see the Title, Abstract, Image, and Body
fields that you defined for the News Article structure. The News Article
template should also be selected.
15. Populate the fields and click *Publish* to publish your News Article.

Below is the template script for this structure. It is written in FreeMarker:

    <#assign renderUrlMax = request["render-url-maximized"]>
    <#assign namespace = request["portlet-namespace"]>
    <#assign readmore = request.parameters.read_more?exists>
    <h1>${title.getData()}</h1>
    <#if readmore>
    <p>${abstract.getData()}</p>
    <p>${body.getData()}</p>
    <#else>
    <p>
    <img src="${image.getData()}" border="0" align="right">
    ${abstract.getData()}</p>
    <a href="${renderUrlMax}&${namespace}read_more=true">Read More</a>
    </#if>

This template is pretty small but it actually does quite a bit. First, a portlet
URL which maximizes the portlet is created. Once this is done, the template gets
the namespace of the portlet. This is important to avoid URL collisions with
other URLs that might be on the page.

After this, the template attempts to get a request parameter called `read_more`.
Whether or not this was successful is the key to the rest of the script:

- If the template got the `read_more` parameter, it displays the abstract and
the body below the title (which is always displayed).

- If the template didn't get the `read_more` parameter, it displays the image,
the abstract and the link created above, which sets the `read_more` parameter.

When this template is rendered, it looks something like this:

![Figure 3.7: The initial view for the Nose-ster News Article.](../../images/04-web-content-adv-example1.png)

![Figure 3.8: After Clicking *Read More*, you're able to read the full text body.](../../images/04-web-content-adv-example2.png)

Now that you've created a handsome template, it's time to decide who the lucky
people are that get to use it.

### Assigning template permissions  

Permissions for templates are similar to permissions for structures. As with
structures, you only want specific developers editing and creating templates.
You may, however, want to make the templates viewable to some content creators
who understand the template scripting language but are not directly writing the
scripts. You can determine who views and interacts with the template by
navigating to *Manage* &rarr; *Templates* and selecting *Permissions* from the
*Actions* button.

You can grant or deny permissions based on Roles. For instance, you may create a
role with the ability to update the template and create a second role that can
both update and delete. Liferay Portal makes it possible to assign permissions
based on the roles and responsibilities within your organization.

Now that you understand the role structures and templates play in creating web
content, let's look at how you can use Liferay to manage multiple sites.

## Leveraging Liferay's multi-site capabilities  

As stated in chapter 1, a site is a set of pages that can be used to publish
content or applications. Sites can be independent or they can be associated with
an organization and serve as the website for that organization. With Liferay,
you can create as many different sites as you like within the context of a
single portal.

You can use sites in Liferay to build many different kinds of websites. Whether
you're building a large corporate website, a company intranet, or a small site
designed to facilitate collaboration among team members, Liferay's framework
provides all the tools you need. To support different kinds of collaboration and
social scenarios, Liferay's sites provide three membership types:

- Open: Users can become members of the site at any time. Users can join sites
from the *My Sites* portlet.

- Restricted: Users can request site membership but site administrators must
approve requests in order for users to become members. Requests can be made from
the *My Sites* portlet.

- Private: Users are not allowed to join the site or request site membership.
Private sites don't appear in the *My Sites* portlet. Site administrators can
still manually select users and assign them as site members.

In addition to these memberships, when a site is associated with an
organization, all the users of that organization are automatically considered
members of the site.

Members of a site can be given additional privileges within the site by using
Liferay's permission settings. It is also possible to assign different roles
within the site to different members. This can be done through *site roles*
which are defined equally for all sites or *teams* which are unique for each
site.

Liferay's sites have two categories of pages called page sets. There are two
kinds of page sets: public pages and private pages. A site can have only public
pages, only private pages or both. Private pages can only be accessed by site
members. Public pages can be accessed by anyone, including users who haven't
logged in. It's possible to restrict access to pages at the page set level or at
the level of individual pages through the permission system. Public pages and
private pages have different URLs and can have different content, applications,
themes, and layouts.

Building a corporate Intranet provides a typical use case for Liferay sites. A
corporate Intranet could have sites for all the organizations in the company:
Sales, Marketing, Information Technology, Human Resources and so on. But what
about the corporate health and fitness center? That's something everybody in the
company, regardless of organization, may want to join. This makes it a good
candidate for an open and independent site. Similarly, the home page for a
corporate intranet should probably be placed in an open independent site so any
member of the portal can access it.

For other kinds of web sites, you may want to use independent sites to bring
people together who share a common interest. If you were building a photo
sharing web site, you might have independent sites based on the types of photos
people want to share. For example, those who enjoy taking pictures of landscapes
could join a Landscapes site and those who enjoy taking pictures of sunsets
could join a Sunsets site.

Liferay always provides one default site, which is also known as the main site
of the portal. This site does not have its own name but rather takes the name of
the portal. By default the portal name is *liferay.com* but this value can be
changed through the simple configuration of the setup wizard. The portal name
can also be changed at any time through the Control Panel within *Portal
Settings*.

---

![tip](../../images/01-tip.png) **Tip:** Prior to Liferay 6.1, there were two
ways of creating sites: organizations and communities. This has been simplified
to provide more ease of use and allow for more flexibility. The main role of
organizations is still to organize the users of the portal in a hierarchy but
they can also have associated sites. Communities can still be created through
independent sites but the new name reflects the fact that sites can be used for
many different purposes besides communities.

---

Sites can be created through the Control Panel by a portal administrator. To add
a site, click on *Sites* under the Portal section of the Control Panel and then
click *Add*. If there is at least one site template available, a dropdown menu
appears. Site templates provide a preconfigured set of pages, portlet
applications, and content that can be used as the basis of a site's public or
private page set. To create a site from scratch, select *Blank Site*. Otherwise,
select the name of the site template you'd like to use. If you opt to create a
site from a site template, you have to choose whether to copy the site
template's pages as your new site's public or private page set. If other site
templates are created, they will appear in the Add menu as they become
available. The following figure shows the form that needs to be filled when
creating a *Blank Site*.

![Figure 3.9: Adding a Site](../../images/01-add-site-screen.png)

**Name:** is the name of the site you wish to create.

**Description:** describes the site's intended function.

**Membership Type:** can be open, restricted or private. An open site appears in
the My Sites portlet and users can join and leave the site whenever they want. A
restricted site is the same except users must request membership. A site
administrator must then explicitly grant or deny users' requests to join. A
private site does not appear in the My Sites portlet and users must be added to
it manually by a site administrator.

**Active:** determines whether a site is active or inactive. Inactive sites are
inaccessible but can be activated whenever a site administrator wishes.

Once you've created a site, it appears in the Sites page of the Control Panel.
Once the site has been created you can specify more details about the site using
three categories: Basic Information, Search Engine Optimization, and Advanced.

![Figure 3.10: Editing a Site](../../images/01-site-editor.png)

**Details:** lets you edit the information you entered when you created the site
and allows you to choose a site template for the public or private pages of your
site. If you select a site template, leave the *Enable propagation of changes
from the site template* box checked to automatically update your site if the
associated site template changes. The update will only be done to pages which
have not been changed within the specific site. If you uncheck this box but
recheck it later, the template pages are then reapplied to your site,
overwriting any changes that may have been made. Only users who have the
permission "Unlink Site Template" will be able to disable the propagation of
changes. When the propagation is enabled, the site template might prevent
modification of some or all pages to ensure the propagation occurs.

**Categorization:** allows you to apply categories and tags to the site.

**Site URL:** lets you set friendly URLs and virtual hosts for your web site.

**Site Template:** provides additional information about the site template
associated to the pages of the site (if any).

**Sitemap:** lets you use the sitemap protocol to notify search engines your web
site is available for crawling.

**Robots:** lets you use a `robots.txt` file to specify certain pages and links
you don't want to be indexed by search engines. You need to set a virtual host
before you set a `robots.txt` file.

**Staging:** lets you turn on either Local Live staging or Remote Live staging.
To enable staging, the *Enable propagation of changes from the site template*
box on the Details tab must be unchecked. With staging enabled, changes to the
site template are automatically propagated to the staged site, not to the live
site. The changes still must be approved before the site is published to live.

**Analytics:** lets you set a Google Analytics ID that is used for your site.

When creating a site from a site template, the initial form provides a new
option that lets you decide if you want to copy the pages from the template as
public pages or as private pages. By default, the site is linked to the site
template and changes to the site template propagate to any site based on it. A
checkbox appears that allows users to unlink the site template if the user has
permission to do so.

![Figure 3.11: When creating a site from a site template, you need to choose whether the site template should be copied into the site's public pages or private pages.](../../images/creating-site-from-site-template.png)

Site templates are a powerful tool for managing many similar sites. Let's
examine how they work.

## Using site templates  

Site Templates can be administered from the Control Panel. They allow portal
administrators to create multiple sites with the same default set of pages and
content. Site templates can contain multiple pages, each with its own theme,
layout template, portlets, and portlet configurations. Site templates can also
contain content just like actual sites. This allows administrators to use site
templates to create new sites that are each created with the same default pages,
portlets, and content. After they've been created, these sites and their pages
can be modified by site administrators. Using site templates can save site
administrators a lot of work even if each site that was created from a given
site template ends up being very different.

To get started, click on *Site Templates* in the Portal section of the Control
Panel. Here, you can add, manage, or delete site templates. You can also
configure the permissions of site templates. As long as a site is linked to the
site template it was created from, changes to the site template's pages,
portlets, and portlet configurations are propagated to the site. Changes to a
site template's content, however, are not propagated to existing sites that are
linked to the site template. We discuss the propagation of changes between site
templates and sites in more detail in the section on site templates use cases
below.

To manage the pages of a site template, click on *Site Templates* in the Control
Panel and then click *Actions* &rarr; *Manage Pages*. From here, you can add or
remove pages from a site template or select themes and layout templates to apply
to the site template. Click on a specific page if you'd like to select a
different theme or layout template for that page. To edit the pages themselves,
click *Actions* &rarr; *View Pages*. You can add specific portlets to each page
of a site template and configure the preferences of each portlet. Each page can
have any theme, any layout template, and any number of portlet applications,
just like a page of a regular site. As with site pages, you can organize the
pages of a site template into hierarchies. When you create a site using a site
template, the configuration of pages and portlets is copied from the template to
the site.  By default, all changes made to the site template are automatically
copied to sites based on that template.

---

![tip](../../images/01-tip.png) **Tip:** If you want to publish a piece of web
content to many sites and ensure modifications are applied to all, don't use
site template content for that purpose. Instead, place the content in the global
scope and then reference it from a *Web Content Display* application in each
site.

---

By default, the following site templates are provided:

- **Community Site:** Provides a preconfigured site for building online
  communities. The Home page of a *community site* provides message boards,
  search, a display of a poll and statistics of the activity of community
  members. The site will also be created with a page for a community calendar
  and a page for a wiki.

- **Intranet Site:** Provides a preconfigured site for an intranet. The Home
  page displays the activities of the members of the site, search, a language
  chooser and a list of the recent content created in the intranet. It also
  provides 3 additional pages for *Documents and Media*, *Calendar* and external
  *News* obtained through public feeds.

The following figure displays the form shown when editing the *Community Site*
template:

![Figure 3.12: Site Templates](../../images/01-site-templates.png)

To view and manage the pages of a site template, click the *Open site template*
link. This opens the template in a new browser window (or tab) and it can be
navigated or managed like a regular site.

### Site templates example

Suppose we need to create the following three sites for Nose-ster's internal
use: Engineering, Marketing, and Legal. These should be private sites that are
only accessible to members of these respective departments. We could design each
site separately but can save ourselves some work if we create a site template to
use instead.

To create a site template, navigate to the Control Panel and click *Site
Templates*. Then click *Add* and enter a name for your template: we'll use
*Department* for our example. Leave the *Active* and *Allow Site Administrators
to Modify the Pages Associated with This Site Template* boxes checked. The
*Active* box must be checked for your template to be usable. If your template is
still a work in progress, you can uncheck it to ensure that no one uses it until
it's ready. Checking *Allow Site Administrators to Modify the Pages Associated
with This Site Template* allows site administrators to modify or remove the
pages and portlets that the template introduces to their sites--if you want the
templates to be completely static, you should uncheck this.

From the list of site templates, click on the *Department* site template that
you created. Then click on the *Open site template* link to begin adding pages
and portlets and configuring the layouts. When you click this link, the site
template opens in a new browser tab or window. For our example, we would like
our site template to include four pages. First, we'd like a Home page with the
Activities, Announcements, and Calendar portlets. Next, we'd like a Documents
and Media page with the Documents and Media portlet. Finally, we should create a
Wiki page with the Wiki and Tag Cloud portlets and a Message Boards page with
the Message Boards and Tag Cloud portlets. When you're done creating and
configuring the pages of your site template, just close the browser tab or
window that opened when you clicked *Open site template*. Changes to site
templates are automatically saved as you make them, so you don't need to return
to the Site Templates page of the Control Panel and select *Save*.

![Figure 3.13: You can see the name of the site template you're currently editing](../../images/editing-site-template.png)

Next, let's use our site template to create our Engineering, Marketing and Legal
sites. Go to the Control Panel and click on *Sites*. Then click *Add* &rarr;
*Department*. Enter *Engineering* for the site name and set the Membership Type
to *Private*. Recall that private sites don't appear in the My Sites portlet so
that regular portal users won't even know that the Engineering site exists.
Also, the only way users can be added to a private site is via an invitation
from a site administrator. Leave the *Active* box checked so that your site can
be used immediately. Select the *Copy as Private Pages* option since our
Engineering site is intended for internal use only. Leave the *Enable
propagation of changes from the site template* box checked so that the
Engineering site receives updates if the Department site template is modified.
Finally, click *Save* to create your the Engineering site.

Repeat these steps to create the Marketing and Legal sites. The new sites have
all the pages and portlets you created in the site template. To view the pages
of the new sites, click on *Sites* in the Control Panel and then click on
*Actions* &rarr; *Go to Private Pages* next to one of your new sites. Using site
templates streamlines the site creation process for administrators, making it
easy to create sites quickly. Now each Nose-ster department has its own
calendar, documents and media library, wiki, and message boards application.
Although the pages and portlets of each department's site are the same, each
site will quickly be filled with department-specific information as users add
and share content within the sites. Also, site administrators can add new pages,
portlets, and content to their sites, further differentiating each department's
site from the others.

### Propagating changes from site templates to sites

It's possible for site template administrators to add, update, or delete site
template pages. Changes made to a site template can be propagated to sites whose
pages sets are linked to the site template. Such a link is created when you
create a site based on a site template and leave the *Enable propagation of
changes from the site template* box checked. To disable or re-enable this link
for a site, select the site in the Control Panel's context menu selector. Then
click on *Site Settings* and uncheck or recheck the *Enable propagation of
changes from the site template* checkbox. You can can also access the Site
Settings interface via the Dockbar by clicking *Manage* &rarr; *Site Settings*.
In this section, we explain the propagation of changes from site templates to
sites and discuss the options available to site administrators and site template
administrators.

If a site's page set has been created from a site template and the propagation
of changes from the site template is enabled, site administrators can add new
pages but cannot remove or reorder the pages imported from the site template.
If a site has both pages imported from a site template and custom site pages,
the site template pages always appear first; custom pages added by site
administrators appear after the site template pages. Only site template
administrators can remove, reorder, or add site template pages. Site
administrators can add or remove custom site pages. They can also reorder custom
site pages as long as they're all positioned after the site template pages. Site
template administrators cannot add, remove, or reorder custom site pages.

If a site administrator changes a page that was imported from a site template
and refreshes the page, the following message appears:

	This page has been changed since the last update from the site template. No
	further updates from the site template will be applied. Click *Reset* to
	overwrite the changes and receive updates from the site template.

If the site administrator clicks the *Reset* button, changes are propagated from
the site template to all the pages of the site that were imported from the site
template. Clicking the *Reset* button makes two kinds of updates. First, changes
made by site administrators to pages that were imported from the site template
are undone. Second, changes made by site template administrators to site
template pages are applied to the site pages.

Site template administrators can set preferences for portlets on site template
pages. When a portal administrator creates a site from a site template, the
portlet preferences are copied from the site template's portlets, overriding any
default portlet preferences. When merging site template and site changes, e.g.,
when resetting, portlet preferences are copied from site template portlets to
site portlets. Only global portlet preferences or local portlet preferences
which don't refer to IDs are overwritten.

Site administrators can also add data to site template portlets. For example,
site template administrators can add the Wiki portlet to a site template page
and use the Wiki to create lots of articles. When a portal administrator creates
a site from a site template, data is copied from the site template's portlets to
the site's portlets. The preferences of the site's portlets are updated with the
IDs of the copied data. For example, if a site is created from a site template
that has a Wiki portlet with lots of wiki articles, the wiki articles are copied
from the site template's scope to the site's scope and site's Wiki portlet is
updated with the IDs of the copied wiki articles. Portlet data is only copied
from a site template to a site when the site is first created; data is not
copied copied during a site reset.

Now that we've learned how site templates work, let's discuss how to use page
templates. 

## Using page templates  

Click on *Page Templates* in the Control Panel to see a list of page templates.
Page templates function similarly to site templates but at the page level. Each
page template provides a pre-configured page to reuse. Within a page template,
it's possible to select a theme, a layout template, to add portlets to the page
and to configure portlet preferences. Both sites and site templates can utilize
page templates for creating new pages.

![Figure 3.14: Page Templates](../../images/server-configuration-page-templates.png)

You can edit or delete existing page templates, configure their permissions, or
add new page templates. By default three sample page templates are provided:

- **Blog:** provides a page with three applications related to blogging. It has
  two columns, the main left column contains the blogs portlet and the small
  right column provides two side portlets, Tag Cloud and Recent Bloggers. The
  tag cloud application will show the tags used within the site and will allow
  navigating through the blog entries shown in the main blogs portlet.

- **Content Display Page:** provides a page preconfigured to display content. It
  has three auxiliary applications (Tags Navigation, Categories Navigation, and
  Search) and an Asset Publisher. The most significant aspect of this page is
  that the Asset Publisher is preconfigured to be display any web content
  associated with this page. This means that you can select any page created
  from this page template as a *Display Page* for a web content article. You can
  choose a display page for a web content article when creating a new web
  content article or when editing an existing one. When you create a new web
  content article, a unique (canonical) URL for the web content pointing to this
  page will be assigned to it.

- **Wiki:** provides a page with three applications related to authoring a wiki.
  It also has two columns, the main left column with the wiki application and
  two right side portlets to allow navigating through pages by tags and
  categories.

To add a new page template, click the *Add* button. Then enter a name and
description for your template. Leave the *Active* button checked. Click *Save*
and then identify your page template in the list. Click its name or use the
Actions button to edit the page template. The *Open Page Template* link opens a
new browser window which you can use to configure your new page. Any changes you
make are automatically saved so you can close the new browser window once you're
done.

Note that after a new page template has been created the default permissions are
to only allow the creator to use the page template. To give other users access
to it, use the actions menu in the list of templates and choose *Permissions*.
Once you see the matrix of roles and permissions, check the *View* permission
for the role or roles needed to see the page template in the list of available
page templates when creating a new page. If you want any user who can create a
page to be able to use the page template, just check the *View* permission for
the *User* role.

![Figure 3.15: Selecting a Page Template](../../images/control-panel-selecting-page-template.png)

To use your template to create a new page, just navigate to a page over which
you have site administrator privileges and select *Add* &rarr; *Page* from the
Dockbar. You'll be able to select a page template and type a name for the new
page. Alternatively, you can use the Control Panel. First, in the context
selector menu, select the site to which you'd like to add a page and then click
on the *Site Pages* link. Then click the *Add Page* button, type a name, select
your template from the drop down menu and click *Add Page* to finish.

![Figure 3.16: Choosing whether or not to automatically apply page template changes to live pages](../../images/automatic-application-page-template-changes.png)

Note that by default, when a site administrator creates pages based on a page
template, any future changes to the template are automatically propagated to
those pages. Site administrators can disable this behavior by unchecking the
*Automatically apply changes done to the page template* box.

<!-- | COMMENT FOR AUTHOR: IMHO, the following paragraph does not fit here
because it is of interest in the context of managing a site, not in the context
of managing a site template | -->

If staging has been enabled, changes to the page template are automatically
propagated to the staged page. These changes still need to be approved before
the page is published to live. For this reason, the automatic propagation of
page template changes to the staged page cannot be turned off and the
*Automatically apply changes done to the page template* checkbox does not
appear.

We'll discuss staging in more detail later in this chapter. For now let's look
at importing and exporting templates.

### Exporting and importing site templates and page templates  

If you want to export a site that uses site or page Templates to a different
environment (through a LAR file or remote publication), the Templates must be
exported and imported manually in advance or the import will fail.

To export a Site using a Site Template, use the following process:
1. Go to Control Panel &rarr; Site Templates and click Actions &rarr; Manage
Pages for the Site Template your site is using.
2. Click *Export* to obtain a LAR file with the content of the Site Template. Be
sure to choose the applications and data you want exported.
3. In your target environment, go to Control Panel &rarr; Site Templates and
create a new Site Template.
4. Click Actions &rarr; Manage Pages for that Site Template and then click
*Import*.
5.  Upload the LAR file containing your site template's content.

Now the site can be exported and imported normally to this new environment.

For page templates, the process very similar:
1.  Go to Control Panel &rarr; Page Templates.
2. Next to the page template you would like to export, click Actions &rarr;
Export. This produces a LAR file you can import later.
3. On the target environment, go to Control Panel &rarr; Page Templates and
create a new Page Template.
4.  Next to the new template, click Actions &rarr; Import.
5.  Upload the LAR file containing the exported page template from step 3.

The page template can now be imported normally to this new environment.

Next, let's examine the tools Liferay provides for handling translations.

## Localization  

Previous versions of Liferay had the ability to create and manage different
translations of your web content but with Liferay 6.1 we've added several
improvements.

When you create a new piece of Web Content, you have the ability to choose a
default language. If you click *Change*, you can select your default language
from a large number of languages Liferay supports. Before you can create a
translation, you must finish creating the content in your default language and
save it. Once you've done that, editing the content provides you with the option
to *Add Translation*.

![Figure 3.17: Adding a translation](../../images/04-web-content-content-translation.png)

After you click *Add Translation*, you can select a language by scrolling
through the list or by entering the language you want to use in the search box.
When you select a language, a lightbox opens within your browser window enabling
you to easily compare the original with the new translation. Once you are done
with the translation, click *Save* and the translation is added to the list of
*Available Translations*.

![Figure 3.18: Adding a translation](../../images/04-web-content-content-translation-2.png)

The ability to completely delete a translation in one step has also been added.
Instead of simply disabling a translation or having to go through a multistep
process to remove it, you can now simply open the translation you don't want and
click *Remove Translation*.

When you create a new web content structure, each field you create has a
*Localizable* checkbox displayed next to it. This enables you to control what
can and can't be changed in the translation process. For example, if you don't
want images or content titles to be changed when the content is translated, you
can make sure those fields aren't listed as localizable. When you follow the
steps above to localize content, only fields within the structure that had the
*Localizable* box checked appear within the translation window. Next, we'll
discuss how to let users customize their site pages.

## Allowing users to customize site pages  

As we discussed before, as your site becomes larger and more complex, management
of the content becomes more challenging. We've gone over Liferay management
tools that help you create content quickly and in an orderly fashion. You
created a simple announcement with Liferay's structure editor that allows you to
quickly design a structure and prepare it for the template designers. Then you
applied a template to the structure. You know how to display content using the
Web Content Display portlet. Now, you're ready to take advantage of Liferay's
advanced publishing options.

If a web site isn't properly managed, it can quickly become stale and that
drives viewers away. If people are finding your site because of search engines,
you don't want them presented with outdated (and possibly inaccurate) web
content.

You also want your content to be found easily by your users. This is done
through tags and categories.

Additionally, you may want to create content and send it through an approval and
reviewal process weeks before you want it displayed on the web site. Liferay
gives you this flexibility with the *Schedule* and *Workflow* features.

## Scheduling web content  

Liferay's WCM lets you define when your content goes live. You can determine
when the content is displayed, expired and/or reviewed. This is an excellent way
to keep your site current and free from outdated (and perhaps incorrect)
information. The scheduler is built right into the form your users access to add
web content, in the same column as the structure and template selectors.

![Figure 3.19: Schedule for Publishing Content](../../images/04-web-content-schedule.png)

**Display Date:** Sets (within a minute) when content will be displayed.

**Expiration Date:** Sets a date to expire the content. The default is one year.

**Never Auto Expire:** Sets your content to never expire.

**Review Date:** Sets a content review date.

**Never Review:** Sets the content to never be reviewed.

As you can see, the scheduling feature in Liferay Portal gives you great control
in managing when, and for how long, your web content is displayed on your web
site. Additionally, you have the ability to determine when your content should
be reviewed for accuracy and/or relevance. This makes it possible to manage your
growing inventory of content.

Similar to scheduling, Liferay's staging feature also allows you to manipulate
time, in a manner of speaking.

## Staging page publication  

Staging is an important feature of Liferay WCM. The concept of staging is a
simple one: you can modify your site behind the scenes and then publish all your
updates in one shot. You don't want users seeing your web site change before
their eyes as you're modifying it, do you? Liferay's staging environment allows
you to make changes to your site in a specialized *staging area*. When you're
finished, you can publish all your site changes at once.

Liferay provides site administrators with two different ways to set up staging:
Local Live and Remote Live. With Local Live staging, both your staging
environment and your live environment are hosted on the same server. When Local
Live staging is enabled for a site, a clone of the site is created containing
copies of all of the site's existing pages. Portlet data is also copied,
depending on which portlets are selected when staging is enabled. The cloned
site becomes the staging environment and the original site becomes the live
environment.

When Remote Live staging is enabled for a site, a connection is established
between the current site and another site on a remote Liferay server. The remote
site becomes the live environment and the current site becomes the staging
environment--an instance of Liferay Portal used solely for staging. Content
creators can use the staging server to make their changes while the live server
handles the incoming user traffic. When changes to the site are ready to be
published, they are pushed over the network to the remote live server. Whether
you enable Local Live or Remote Live staging, the interface for managing and
publishing staged pages is the same. 

So when should you use Local Live staging and when should you use Remote Live
Staging? Local Live staging allows you to publish site changes very quickly,
since the staged and live environments are on the same server. It's also easier
to switch between the staged and live environments using Local Live staging.
However, since the staged content is stored in the same database as the
production content, the content isn't as well protected or backed up as with
Remote Live staging. Also, you can't install new versions of portlets for
testing purposes in a Local Live staging environment since only one version of a
portlet can be installed at any given time on a single Liferay server.

With Remote Live staging, your staging and live environments are hosted on
separate servers. This allows you to deploy new versions of portlets and
content to your staging environment without worrying about interfering with your
live environment. With Remote Live staging, you can also use one Liferay
instance as the staging server for multiple production servers. However,
publishing is slower with Remote Live than with Local Live since data needs to
be transferred over a network. And, of course, you need more hardware to run a
separate staging server.

Liferay 6.1 added a feature to staging called Page Versioning. This feature
works with both Local Live and Remote Live staging and allows site
administrators to create multiple variations of staged pages. This allows to
several different versions of sites and pages to be developed at the same time.
Variations can be created, merged, and published using a Git-like versioning
system. Let's jump in to see how to use staging.

### Enabling Local Live staging

Site administrators can enable Staging for a site via the Site Settings UI. To
reach this interface via the Control Panel, select a site in the context menu
selector, click on *Site Settings* in the Control Panel menu, then click on
*Staging* at the left. Under Staging Type, select either *Local Live* or *Remote
Live* and additional options appear. Staging allows changes to be made in a
staging environment so that work can be reviewed, possibly using a workflow,
before it's published to a live site. Enabling Local Live staging is easy. Just
select *Local Live* and decide whether you'd like to enable page versioning. You
can enable page versioning on a site's public pages, private pages, both, or
neither. Page versioning allows you to work in parallel on different versions of
pages and maintains a history of all page modifications. We discuss page
versioning in more detail below.

### Enabling Remote Live staging

When you enable Remote Live staging, the remote site becomes the live
environment and the current site becomes the staging environment. The remote
(live) Liferay server and the local (staging) Liferay server should be
completely separate systems. They should not, for example, share the same the
database. When Remote Live staging is enabled, all the necessary information is
transferred over the network connecting the two servers. Before a site
administrator can enable Remote Live staging for a site, the remote Liferay
server must first be added to the current Liferay server's list of allowed
servers. The current Liferay server must also be added to the remote Liferay
server's list of allowed servers. You can make these configurations in your
Liferay servers' `portal-ext.properties` files. Your first step should be to add
the following lines to your current Liferay server's `portal-ext.properties`
file:

    tunnel.servlet.hosts.allowed=127.0.0.1,SERVER_IP,[Remote server IP address]
    axis.servlet.hosts.allowed=127.0.0.1,SERVER_IP,192.168.0.16,[Remote server IP address]

Then add the following lines to your remote Liferay server's
`portal-ext.properties` file:

    tunnel.servlet.hosts.allowed=127.0.0.1,SERVER_IP,[Local server IP address]
    axis.servlet.hosts.allowed=127.0.0.1,SERVER_IP,192.168.0.16,[Local server IP address]

Remember to restart both Liferay servers after making these portal properties
updates. After restarting, log back in to your local Liferay portal instance as
a site administrator. Then navigate to the Control Panel and choose a site in
the context menu selector. Then click on *Site Settings* in the Control Panel
menu and then on *Staging* in the menu at the left. Select *Remote Live* under
Staging Type and additional options appear.

![Figure 3.20: After your remote Liferay server and local Liferay server have been configured to communicate with each other, you have to specify a few Remote Live connection settings.](../../images/remote-live-staging-settings.png)

First, enter your remote Liferay server's IP address into the Remote Host/IP
field. If the remote Liferay server is a cluster, you can set the Remote Host/IP
to the load balanced IP address of the cluster in order to increase the
availability of the publishing process. Next, enter the port on which the remote
Liferay instance is running into the Remote Port field. You only need to enter a
Remote Path Context if a non-root portal servlet context is being used on the
remote Liferay server. Finally, enter the site ID of the site on the remote
Liferay server that will be used for the Live environment. If a site hasn't
already been prepared for you on the remote Liferay server, you can log in to
the remote Liferay server and create a new blank site. After the site has been
created, note the site ID so you can enter it into the Remote Site ID field on
your local Liferay server. You can find any site's ID by selecting *Actions
&rarr; Edit* next to the site's name on the Sites page of the Control Panel.
Finally, check the *Use a Secure Network Connection* field to secure the
publication of pages from your local (staging) Liferay server to your remote
(live) Liferay server.

That's all you need to do to enable Remote Live Staging! However, when a user
attempts to publish changes from the local (staging) server to the remote (live)
server, Liferay passes the user's credentials to the remote server to perform a
permission check. In order for a publishing operation to succeed, the operation
must be performed by a user that has identical credentials and permissions on
both the local (staging) and the remote (live) server. This is true regardless
of whether the user attempts to publish the changes immediately or attempts to
schedule the publication for later. If only a few users should have permission
to publish changes from staging to production, it's easy enough to create a few
user accounts on the remote server that match a selected few on the local
server. However, the more user accounts that you have to create, the more
tedious this job becomes and the more likely you are to make a mistake. And you
not only have to create identical user accounts, you also have to ensure that
these users have identical permissions. For this reason, we recommend that you
use LDAP to copy selected user accounts from your local (staging) Liferay server
to your remote (live) Liferay server. Liferay's Virtual LDAP Server application
(EE-only), available on Liferay Marketplace, makes this easy.

### Example: Enabling Local Live staging

Let's create a Local Live staging environment for Nose-ster's home page. Before
we begin, let's add a new page. Click *Add &rarr; Page* from the toolbar in the
default site and name the new page *News and Events*. Next, click the *View
Pages* button to navigate to the pages. Then add the Alerts and Announcements
portlets to the News and Events page.

When you activate staging Local Live staging, Liferay creates a clone of your
site. This clone became the staging environment. Because of this, we recommend
only activating staging on new, clean sites. Having a few pages and some
portlets (like those of the example site we've created) is no big deal. However,
if you have already created a large amount of content you might not be able to
enable staging on that site. Also, if you intend to use page versioning to track
the history of updates to your site, we recommend that you enable it as early as
possible, *before* your site has many pages and lots of content. Your site's
update history won't be saved until you enable page versioning. Page versioning
requires staging (either Local Live or Remote Live) to be enabled.

Now we're ready to activate staging for this site. Go to the Control Panel then
to *Site Settings* and select *Staging* from under the *Advanced* heading. We'll
assume we don't have a separate staging server so we'll select the *Local Live*
staging type. If you do have a separate server to use for staging, follow the
instructions in the previous section for configuring it and your local server
for remote staging. Either way, once you make a selection (either *Local Live*
or *Remote Live*), more options become available for page versioning and staged
portlets.

### Enabling page versioning and staged portlets

Enabling page versioning for a site allows site administrators to work in
parallel on multiple versions of the site's pages. Page versioning also
maintains a history of all updates to the site from the time page versioning was
enabled. Site administrators can revert to a previous version of the site at any
time. This flexibility is very important in cases where a mistake is found and
it's important to quickly publish a fix. If you're following the Nose-ster
example, check *Enabled On Public Pages* to enable page versioning for the
Nose-ste site and then click *Save*.

![Figure 3.21: You can decide to use versioning and choose what content should be staged.](../../images/04-web-content-staging.png)

Before you activate staging, you can choose which portlets' data should be
copied to staging. We'll cover many of the collaboration portlets listed under
the Staged Portlets heading when we come to chapter 8. For now, you just need to
be aware that you can enable or disable staging for any of these portlets. Why
might you want to enable staging for some portlet types but not others? In the
case of collaborative portlets, you probably *don't* want to enable staging
since such portlets are designed for user interaction. If their content were
staged, you'd have to manually publish your site whenever somebody posted a
message on the message boards to make that message appear on the live site.
Generally, you'll want web content to be staged because end users aren't
creating that kind of content--web content is the stuff you publish to your
site. But portlets like the Message Boards or Wiki would likely benefit from
*not* being staged. Notice which portlets are marked for staging by default: if
you enable staging and accept the defaults, staging is *not* enabled for the
collaborative portlets.

### Using the staging environment  

After enabling staging (either Local Live or Remote Live) for a site, you'll
notice a colored bar with some new menus just below the Dockbar when you
navigate to the site. These new menus help us manage staged pages. You'll also
notice that most of your page management options have been removed, because now
you can't directly edit live pages. You now must use the staging environment to
make changes. Click on *Staging* to view the staged area. Your management
options are restored and you can access some new options related to staging. If
you're following along with the Nose-ster example, navigate back to the News and
Events page and click on *Staging* to get your page editing capabilities back.

![Figure 3.22: You can see the new bar staging adds to the top of your screen.](../../images/04-web-content-staging-live-page.png)

Add the Calendar portlet and then click on *Live* from the Dockbar. Notice that
the Calendar portlet isn't there. That's because you've staged a change to the
page but haven't published that change yet to the live site. Go back to the
staged page and look at the options you have available. From here you can *Undo*
changes, view a *History* of changes, *Mark as Ready for Publication* and
*Manage Page Variations*.

**Undo/Redo:** allows you to step back/forward through recent changes to a page,
which can save you the time of manually adding or removing portlets if you make
a mistake.

**History:** shows you the list of revisions of the page, based on publication
dates. You can go to any change in the revision history and see how the pages
looked at that point.

**Manage Page Variations:** allows you to work in parallel on multiple versions
of a staged page. We will explain this later.

After you're done making changes to the staged page, click the *Mark as Ready
for Publication* button. The status of the page changes from *Draft* to *Ready
for Publication* and any changes you've made can be published to the Live Site.
When you publish a page to live, only the version which was *Marked as Ready for
Publication* is published.

The dropdown next to the Staging link at the top gives you the option to
*Publish to Live Now* or *Schedule Publication to Live*.

**Publish to Live Now:** immediately pushes any changes to the Live Site.

**Schedule Publication to Live:** lets you set a specific date to publish or to
set up recurring publishing. You could use this, for example, to publish all
changes made during the week every Monday morning without any further
intervention.

Click on *Mark as Ready for Publication* and then *Publish to Live Now* to
publish your Calendar portlet to the live site.

Content publication can be also controlled using staging. Calendar events are
staged by default (this can be changed in Staging Configuration). If you create
an event in the staged site, it isn't visible in the live site until you publish
it to the live site following the same steps you just performed (you can select
which types of content are published when you publish to the live site). If
workflow is enabled for Calendar Events, the event needs to go through the
workflow process before it can be published to the live site.

![Figure 3.23: Ready to publish to the live site.](../../images/04-web-content-staging-publish.png)

Web content tends to be frequently updated, often more so than other kinds of
content. For some web content articles, this can result in very high numbers of
versions, sometimes hundreds. Such high version numbers can make it very slow to
publish web content articles. Liferay 6.2 addresses this issue by allowing site
administrators to choose whether or not to publish a web content article's
version history when a staged article is ready to be published. To use this
feature, staging must be enabled. Edit a web content article that's being
displayed in a Web Content Display portlet on one of your pages and then click
*Staging* &rarr; *Publish to Live Now* from just below the Dockbar. In the
popup, expand the Applications heading and scroll down until you see the section
for Web Content.

![Figure 3.24: Uncheck the version history box to only publish the latest approved version of web content articles that have multiple versions.](../../images/web-content-version-history-box.png)

Liferay 6.2 also added a portal property,
`journal.publish.version.history.by.default`, that sets the default behavior. By
default, this property is set to `true` so site administrators have to manually
manually uncheck the *Version History* box mentioned above if they only want to
publish the latest approved version of web content articles. If you'd like to
change the default behavior, add the following line to your
`portal-ext.properties` file:
`journal.publish.version.history.by.default=false`.

One of the most powerful features of staging is page variations. Let's see how
to use them to create multiple different variations of your site's pages for
different purposes.

### Using site pages variations  

Let's say you're working on a product-oriented site where you'll have several
major changes to a page or a set of pages over a short period of time. Also you
need to be working on multiple versions of the site at the same time to ensure
everything has been properly reviewed before it goes live. With staging in
Liferay 6.1 you can do this using **Page Variations**.

For example, you can create several page variations, enabling the marketing team
to give your site a completely different look and feel for Christmas. At the
same time, the product management team can work on a different version that will
be published the day after Christmas for the launching of a new product.
Additionally, the product management team is considering two different ideas for
the home page of the site, so they can create several page variations of the
home page inside their product launch site.

Variations only affect pages and not the content, which means all the existing
content in your staging site is shared by all your variations. In different site
page variations you can have different logos, different look and feel for your
pages, different applications on these pages, different configuration of these
applications and even different pages. One page can exist in just one site page
variation or in several of them.

By default, we only have one site page variation which is called **Main
Variation**. To create a new one, use the dropdown next to the *Staging* link
and click on *Manage Site Pages Variations*. This brings you to a list of the
existing site page variations for your site. Click *Add Site Pages Variation* to
create a new one. From the *Add Site Pages Variation* screen, you can set a
Name, Description and also set your new variation to copy the content from an
existing variation. There are several options to choose in this selector.

**Any existing Site Pages Variation:** creates a new site page variation that
contains only the last version of all the pages that exist in this variation.
The current variation must be marked as ready for publication.

**All Site Pages Variation:** creates a new variation that contains the last
version marked as ready for publication from any single page existing in any
other variation.

**None:** creates a new, empty variation.

You are also able to rename any variation. For example, edit the Main Variation
and change its name to something that makes more sense in your site, such as
*Basic*, *Master*, *Regular* and create a variation for Christmas.

You can switch between different variations by clicking on them from the staging
menu bar. It's also possible to set permissions on each variation, so certain
users have access to manage some, but not all variations.

You can now go to the home page of your Christmas variation and change the logo,
apply a new theme, move portlets around, change the order of the pages and
configure different portlets. The other variations won't be affected. You can
even delete existing pages or add new ones (remember to *Mark as Ready for
Publication* when you are finished with your changes).

When you delete a page, it is deleted only in the current variation. The same
happens when you add a new page. If you try to access a page which was deleted
in the current variation, Liferay informs you this page is not *enabled* in this
variation and you must enable it. To enable it, navigate to the *Manage* &rarr;
*Site Pages* screen. Here all the existing pages for all the variations are
shown in a tree. Pages not enabled for the current variation are shown in a
lighter color.

To publish a variation to the live site, click on *Publish to Live now* in the
dropdown next to the variation name. Publications can also be scheduled
independently for different variations. For example, you could have a variation
called *Mondays* which is published to the live site every Monday and another
one called *Day 1* which is published to the live site every first day of each
month.

You can also have variations for a single page inside a site page variation,
which allows you to work in parallel in different versions of a page. For
example, you might work on two different proposals for the design of the home
page for the Christmas variation. These page variations only exist inside a site
Page variation.

To create a new page variation, click *Manage Page Variations* on the staging
toolbar. This brings you to a list of existing page variations for the current
page (by default, there is only one called *Main Variation*). You can create
more or rename the existing one. You can switch between different page
variations using the toolbar containing the page variations below the site pages
variations toolbar. When you decide which page variation should be published,
mark it as *Ready for Publication*. Only one page variation can be marked as
ready for publication and that is the one that gets published to the live site.

![Figure 3.25: Creating a new Page Variation](../../images/04-web-content-add-site-pages-variation.png)

For example, we could create a page variation called Thanksgiving for the News
and Events page inside of the Christmas variation and another one called
Christmas Day to display different content on those particular days.

![Figure 3.26: The Thanksgiving Page Variation.](../../images/04-web-content-branch-thanksgiving.png)

Another powerful feature is the possibility of *merging* Site Pages Variations.
To merge two Site Pages Variations, you need to go to the Manage Site Variations
screen. From there, click on *Merge* on the Site Pages Variation you want to use
as the base. You will be asked to choose the Site Pages Variation to merge on
top of it. Merging works in the following way:

* New pages that don't exist in the base Variation, will be added.
* If a page exists in both Site Pages variations, and at least one version of
the page was marked as ready for publication, then the latest version marked as
ready will be added as a new Page Variation in the target page of the base
Variation. (Note that older versions or page variations not marked as ready for
publication won't be copied. However, merge can be executed as many times as
needed and will create the needed pages variations in the appropriate page of
the base Site Pages Variation).
* Merging does not affect content nor will overwrite anything in the base
Variation, it will just add more versions, pages and page variations as needed.

Let's finish our discussion of staging by outlining a few more features.

### Wrapping up staging  

You can enable staging on an individual site basis, depending on your needs.
This makes it easy to put strict controls in place for your public web site,
while opening things up for individual sites that don't need such strict
controls. Liferay's staging environment is extremely easy to use and makes
maintaining a content-rich web site a snap.

Liferay 6.0 introduced a new feature to the permissions system called teams.
Let's examine teams next.

## Creating teams for advanced site membership management  

Teams don't appear as a link in the Control Panel because they exist *within*
sites. Teams allow site administrators a greater degree of flexibility than was
possible using just user groups and roles. They allow site administrators to
create various sets of users and permissions for site-specific functions. Teams
are the preferred method for collecting permissions within a single site.

If you create a team for one site, the permissions defined for it are not
available to any other sites. In contrast, if you assigned a custom role to a
user group, the role would be available portal-wide even though the specific
permissions defined by it would only apply within the scope of a designated
site. Furthermore, team members, unlike user group members, are guaranteed to be
members of the desired site.

To create a team within a site, first navigate to the *Control Panel &rarr;
Sites* page then and then select *Actions &rarr; Manage Memberships* for the
site within which you want to create a team. Finally, click *View &rarr; Teams*
and click the Add Team button.

![Figure 3.27: Creating a Team within a Site](../../images/01-creating-a-team.png)

After you've clicked the *Add Team* button and entered a name and a description,
click *Save*. Your new team will appear in the list. To add members, simply
click on *Actions &rarr; Assign Members*.

Permission management for teams is handled at the individual portlet level,
using the *Options &rarr; Configuration &rarr; Permissions* tab of the portlet
itself. Remember the portlet options link is the wrench symbol at the top of a
portlet. This enables users who wouldn't have access to all of the necessary
options in the Control Panel to manage permissions through teams.

![Figure 3.28: Assigning Portlet Permissions to a Team](../../images/01-assigning-portlet-permissions-to-teams.png)

To give a team access to a particular portlet function, access the *Permissions*
tab of a portlet residing on a page, check the boxes corresponding to
permissions you want to assign to the teams, then click *Save*. That's it! Now
your team is ready to perform their functions. Next, let's look at how to
configure Liferay for mobile devices.

## Displaying site pages to mobile devices  

Mobile device rules allow you to configure sets of rules to alter the behavior
of the portal based on the device being used to access Liferay. The proportion
of mobile device users browsing the web has been steadily increasing, so it's
important to be able to handle different kinds of devices appropriately. For
instance, you can configure the look and feel of Liferay pages accessed by
smartphone or tablet users differently from those accessed by PC users.

Both sites and individual pages can be configured with any number of rule
groups. A rule group is designed to describe a group of devices; think of a rule
group as a mobile device family. It can contain one or more rules that describe
a category of devices, such as all Android devices or all iOS tablets. You can
define as many rules in a rule group as you need to classify all the devices for
which you'd like to define actions. Rule groups can be prioritized to determine
which one applies to a given page request. 

In order to configure mobile device rules, you need a way to find out the
characteristics of the device. While some of the characteristics are provided by
the device, most are not. For this reason, there are databases that contain
information about thousands of devices. These databases make it possible to
learn every detail about a device from the device type, which is included in
each request sent to the portal. Liferay's Mobile Device Rules can connect to
device databases so that you can use their device characteristics in your rules. 

Among the plugins available on Liferay Marketplace, you can find the Device
Recognition Provider plugin. This plugin provides out of the box integration
with WURFL, an open source database licensed with the AGPLv3 license. Commercial
licenses are also available. It's also possible to develop plugins that
integrate with other device databases. Even if you don't have a device database,
you can still set up mobile device rules. They won't, however, be effective until
a database is deployed, because the portal won't have enough information about
the devices being used to make page requests. 

To configure mobile device rules, you must install the Device Recognition Provider
plugin. This plugin uses the WURFL database to enable Liferay to detect which
mobile device or operating system is being used for any given request. To
install the plugin, navigate to the Store section of the Control Panel, located
under the Marketplace heading. Click on the *Utility* section and then on *See
All*. Search for the appropriate Device Recognition Provider plugin (CE or EE)
and click on it. Finally, click on *Free* to acquire the plugin. Once you've
acquired the plugin, you need to download and install it. To do so, navigate to
the Purchased section of the Control Panel, find your Device Recognition
Provider plugin, and click on *Download* and then *Install*.

**Installation Note:** If your server doesn't have access to the outside
Internet, an error appears in your log: `SLF4J: Failed to load class
"org.slf4j.impl.StaticLoggerBinder`. This occurs because WURFL by default
downloads device information from the web. You can provide the same information
to WURFL manually by downloading the SLF4J distribution from
[http://www.slf4j.org/download.html](http://www.slf4j.org/download.html),
unzipping the resulting file, copying `slf4j-log4j12.jar` to
`[WEB_APP_HOME]/wurfl-web/WEB-INF/lib` folder, and restarting your Liferay
instance. On some application servers, you'll need to add this .jar file to the
`wurfl-web.war` file first (in the directory noted above) before deploying the
file to your server. 

You can access the Mobile Device Rules administrative page from the Content
section of the Control Panel. Select the appropriate scope using the context
menu selector so your rule groups are available where you expect them to be. The
Mobile Device Rules administrative page displays a list of defined rule groups
and lets you add more. To add rules to a rule group, select *Actions*
&rarr; *Manage Rules*, or click on a rule group to edit it, and then click
the *Manage Rules* link.

![Figure 3.29: You can manage device rules from the Mobile Device Rules administrative page.](../../images/mobile-device-rules.png)

The rules defined for a rule group, along with the priorities of the rule groups
selected for a particular site or page, determine which rule group's actions are
applied to a given request. From the Manage Rules page for a specific rule set,
you can add a rule by specifying a rule type. Remember that you can add as many
rules to a rule group as you need in order to classify the devices on which
you'd like to take actions. Note that, by default, only the Simple Rule type is
available.  The rules are designed, however, to be extensible, and additional
rule types can be added by your developers. Once added, you can edit the rule to
specify a device type and operating system.

![Figure 3.30: You need to install the Device Recognition Provider plugin to populate the OS list.](../../images/mobile-device-editing-rule.png)

Once you've created some mobile device rule groups and added some rules to them,
you'll be ready to set up some actions. The actions defined for a rule group
determine what happens to a particular request when the device is detected
and the rule group has been found to apply.

You can add actions to a rule group from the Site Pages page of the Control
Panel. Select either the public or private pages and then look for the *Mobile
Rule Groups* link in the right-hand menu. Use the *Select Rule Group* button to
select rule groups to be applied either to a site or to a single page. If you
select the page group itself from the left-hand menu, the selected rule group
applies to all the pages of the site by default. If, however, you select an
individual page and then click the *Select Rule Group* button, the rule groups
apply only to that page. You can select multiple rule groups for a particular
site or page and order them by priority. The rule groups are checked in
decreasing order of priority: the actions defined by the first rule group that
applies are executed.

![Figure 3.31: You can select a mobile device rule group to apply for a site or page from the Site Pages section of the Control Panel.](../../images/mobile-device-selection.png)

To add actions to a selected rule group, use the *Actions* &rarr; *Manage
Actions* button and then click *Add Action*. By default, there are four kinds of
actions that can be configured for mobile rule groups: layout template
modifications, theme modifications, simple redirects, and site redirects. Layout
template modifications let you change the way portlets are arranged on pages
delivered to mobile devices, and themes modifications let you select a specific
look and feel. If it makes more sense for you to create separate mobile versions
of certain sites or pages, you can use a redirect to make sure mobile device
users get to the right page. To define a simple redirect, you need to specify a
URL. To define a site redirect, you need only specify the site name and page
name of the page to which you're redirecting. Like mobile device rules, mobile
device actions are designed to be extensible. Your developers can define custom
actions in addition to the four actions provided by default.

To review, if you'd like to configure an action or actions that take place when
mobile device requests are received, take the following steps:

1. Create a mobile device rule group to represent the family of devices for
   which to define an action or actions.

2. Define one or more rules for your rule group that describe the family of
   devices represented by your rule group.

3. Apply your rule group to an entire page set of a site (all the public pages
   of a site or all the private pages) or to a single page.

4. Define one or more actions for your rule group that describe how requests
   should be handled.

To see how this might work in practice, let's discuss a few examples of how you
can use mobile device rules. First, suppose you have a separate version of a
site on your portal that's specifically designed for mobile phones running
Android or Bada. For our example, we'll make a site called Android/Bada Liferay
and we'll configure the default Liferay site to redirect incoming requests from
Android or Bada mobile phones to the Android/Bada Liferay site. Our first step
is to create the Android/Bada Liferay site: go to the Sites page of the Control
Panel and click *Add* &rarr; *Blank Site*. Enter the name *Android/Bada Liferay*
and click *Save*. Then, with Android/Bada selected in the context menu selector,
click on *Site Pages*. By default, the newly created site doesn't have any
pages, so click on *Add Page*, enter the name *Welcome*, and click the *Add
Page* button.  Now our Android/Bada Liferay site has a public Welcome page just
like our default Liferay site.

Next, select *Liferay* in the context menu selector and go to the Mobile Device
Rules page of the Control Panel. Click on *Add Rule Group*, enter the name
*Android and Bada Mobile Phones*, and click *Save*. You'll see the message, *No
rules are configured for this rule group.*

![Figure 3.32: After adding a new rule, you'll see a message indicating that no rules have been configured for the rule group.](../../images/no-rule-groups-configured.png)

Click the *Manage Rules* link and we'll configure our rule group to apply only
to mobile phones running Android or Bada. Click *Add Rule*, enter *Rule 1* for
the name and select *Simple Rule* for the type, then click *Save*. Then click on
the rule to edit it or click *Actions* &rarr; *Edit*. Under OS, select *Android*
and *Bada OS* (hold down Control to make multiple selections), select *False*
under Tablet since we want our rule group to apply only to mobile phones, and
click *Save*. Now we just need to define the redirect action for our rule group.
Make sure Liferay is still selected in the context menu selector and click on
*Site Pages*. Click on *Mobile Rule Groups* in the navigation menu to the right.

![Figure 3.33: To apply a mobile device rule group to a page set of a site, select the site in the context menu selector, click on *Mobile Rule Groups*, click *Select Rule Group*, and select the desired rule group.](../../images/site-pages-mobile-device-rules.png)

Click *Select Rule Group* and then click the *Android and Bada Mobile Phones*
rule group that you configured. Once you've selected your rule group, click 
*Mobile Rule Groups* again and click either on your rule group or *Actions*
&rarr; *Manage Actions* next to it. Then click *Add Action*, enter the name
*Android/Bada Liferay Redirect*, and select *Site Redirect* under Type.  Under
the Site dropdown menu that appears, select *Android/Bada Liferay* and under the
Page dropdown menu that appears, select the *Welcome* page that you created
earlier. Lastly, click *Save*. That's it! Now Android and Bada mobile phone
users are redirected to the Android/Bada Liferay site from the Liferay site. 

Let's look at one more example of using mobile device rules before we move on.
Suppose you'd like to create another rule so that when a site is accessed by an
Android or iOS tablet, a different layout is used. To set this up, we need to
follow the same four steps described above. First, make sure that the Liferay
site is selected in the Control Panel's context menu selector and navigate to
the Mobile Device Rules page of the Control Panel. Add a new rule group called
*Android and iOS Tablets*. Add a simple rule called *Rule 1* to this rule group.
As with the previous example, we only need one rule to describe our device
family. Edit *Rule 1* and select *Android and iPhone OS* under the OS heading
and *True* under the Tablet heading, then click *Save*.

Next, click on *Site Pages* in the Control Panel, select *Mobile Rule Groups*,
and select the *Android and iOS Tablets* rule group. Notice that you've now
selected two rule groups for the Liferay site's public pages and they've been
assigned priorities. If a device making a request belongs to both of the device
families represented by the rule groups, the priority of the rule groups
determines which rule group's actions are executed. Note that in our example,
the first rule group contains only mobile phones and the second rule group
contains only tablets, so no devices can belong to both rule groups. Now we just
need to define an action for our Android and iOS Tablets rule group to use a
different layout: On the Site Pages page of the Control Panel, click on *Mobile
Rule Groups*, and then on *Actions* &rarr; *Manage Actions* next to Android and
iOS Tablets. Click on *Add Action*, enter the name *Layout Template
Modification*, and select the *Layout Template Modification* action type.
Lastly, select the *1 Column* layout template (or whichever one you like) and
click *Save*. Good job!  Now the Liferay site's pages are presented to Android
and iOS tablet users with the 1 Column layout template.

## Summary  

This chapter has been your guide to Liferay site management and advanced Web
Content Management. We've seen how you can use Liferay to manage both simple
content and advanced content with structures and templates. We've learned how
you can use Liferay to create multiple sites with different membership types.
We've also learned how to use page and site templates to simplify the site
creation process.

Liferay WCM also includes a powerful staging environment, allowing you to stage
content locally on the same server or remotely to another server. You can
publish your site when you want it, on the schedule you choose. You can even
create different variations of your site that can be worked on simultaneously.

You saw how to allow users to create personal customizations of site pages. We
discussed how site administrators can create teams as a flexible means of
delegating site permissions. We also saw how to configure mobile device rules so
that site pages are presented differently depending on the device making a page
request.

Whether your site is small and static or large and dynamic, Liferay's WCM
enables you to plan and manage it. With tools such as the WYSIWYG editor,
structures and templates, you can quickly add and edit content. With the Web
Content Display and Asset Publisher, you can rapidly select and configure what
content to display and how to display it. By using Liferay's integrated
workflow, you can set up custom publishing rules to fit your organization. And
by using Liferay's staging and scheduling mechanisms, you can manage various
branches of pages and content and control when they are published to your live
portal instance. You will find that managing your site becomes far easier when
using Liferay's Web Content Management system.
