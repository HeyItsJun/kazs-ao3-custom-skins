# AO3 Custom Skins


## Intro to AO3's Elements

> *Prompt to Gemini: get all the visible elements of the site.*

To customize an AO3 skin thoroughly, you need to target the high-level layout containers, the specific content blocks (blurbs), and the meta-data fields. Because AO3 is built on Ruby on Rails, the HTML is generated dynamically via `.erb` templates in the `app/views` directory of the [repo](https://github.com/otwcode/otwarchive).

Below is a comprehensive categorization of the primary HTML elements, IDs, and classes used across the site, derived from the `otwarchive` source code and common skinning practices.


## 1. Global Layout (High-Level Containers)

These wrap every page on the site. Customizing these changes the overall "frame" of the Archive.

* `#outer`: The outermost wrapper for the entire page.
* `#inner`: The container inside `#outer`, often used for setting site width/centering.
* `#header`: The top navigation area.
* `.menu`: The primary navigation links (Fandoms, Browse, etc.).
* `.search`: The header search bar.
* `.logo`: The AO3 logo element.

* `#main`: The primary content area between the header and footer.
* `#footer`: The bottom area containing site links and OTW information.
* `#dashboard`: The sidebar seen on user profiles and "My Works" pages.


## 2. Work Listings (The "Blurb")

When you browse works, each result is a `li` element with the class `.blurb`. This is one of the most common targets for skins.

* `.blurb`: The container for a single work or bookmark in a list.
* `.header.module`: The top part of the blurb (Title, Author, Fandoms).
* `.declaration`: Contains the rating, category, and warnings icons.
* `ul.required-tags`: The four square icons (Rating, Orientation, etc.).
* `h4.heading`: The Title and Author line.
* `h5.fandoms`: The fandom tags listed at the top.
* `blockquote.summary`: The work's summary text.
* `dl.stats`: The numbers at the bottom (Words, Kudos, Comments).


## 3. Reading a Work (The Work Page)

These elements appear when you are actually reading a story.

* `#workskin`: A specific ID added to the work content. Note: "Work Skins" only affect elements inside this ID.
* `.preface.group`: The top section of a work (Title, Summary, Notes).
* `.title`: The work title.
* `.byline`: The author's name.
* `dl.work.meta`: The list of tags (Warnings, Relationships, Characters) at the top.

* `#chapters`: The container for all chapter text.
* `.userstuff`: The actual story text (this is where standard HTML like `<p>`, `<b>`, `<i>` lives).

* `#feedback`: The section containing Kudos and Comments.
* `.kudos`: The "X and Y left kudos" list.
* `ol.thread`: The list of comments.


## 4. Metadata and Tags

AO3 uses specific classes for different types of tags in the `dl.meta` or `.blurb` sections:

* `.warnings`: Archive Warnings.
* `.relationships`: Relationship/Ship tags.
* `.characters`: Character tags.
* `.freeforms`: "Additional Tags."
* `.fandoms`: Fandom names.


## 5. UI Components & Forms

For a truly "thorough" skin, you may want to style these interactive elements:

* `button`, `.action`: Primary site buttons.
* `.dropdown`: The hoverable menu items in the header.
* `fieldset`: Grouped form elements (like in the Search or Filter sidebars).
* `.notice`, `.error`: The flash messages that appear at the top of the page (e.g., "Successfully logged in").
* `.pagination`: The page numbers at the bottom of lists.


## Pro-Tip for Customization:

If you want to find a specific element not listed here (like a specific button on the "Post New" page), use your browser's **Inspect Tool** (Right-click > Inspect).

Because the repo is open-source, you can also look directly into the **[app/views](https://www.google.com/search?q=https://github.com/otwcode/otwarchive/tree/master/app/views)** folder in the GitHub repo. For example:

* `app/views/layouts/_header.html.erb` shows the structure of the top navigation.
* `app/views/works/_work_blurb.html.erb` shows exactly how search results are built.

