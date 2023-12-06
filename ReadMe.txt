
COMMIT CATEGORIES
    APPLICATION BREAKDOWN
    APPLICATION SETUP
    APPLICATION COMPONENT
    APPLICATION FEATURE
    APPLICATION BUG FIXES
    APPLICATION EXTRAS
    APPLICATION DOCUMENTATION








STEP 1: APPLICATION SETUP - META & LINKS
    META
        - charset
        - http-eqCOMPONENTv
        - viewport meta
        - author meta
        - revised meta
        - language meta
        - robot meta (index, nofollow)
        - title & description meta

    LINKS
        - Favicon & Font
        - External CSS file
        - External JS file (theme, global & page script)







STEP 2: APPLICATION SETUP - COLORS VARIABLES (LIGHT & DARK VERSION)
    BACKGROUND
        - page background color
        - text on background color
        - variant background color

    PRIMARY ELEMENT
        - color of primary element
        - hover color of primary element
        - container color of primary element

    BUTTON BADGES
        - background color of the badges
        - text color of the badges

    OUTLINE
        - general outline color
        - input outline color
        - input outline color on hover

    ALPHA COLORS
        - 10% opacity black color
        - 10% opacity white color
        - 20% opacity black color
        - 20% opacity white color
        - typical white color

    OVERLAY
        - background color of an ovelay element

    IMAGE BACKGROUND
        - fallback color of an image element

    ACTIVE INDICATOR
        - color associated with an active element

    ERROR
        - color associated with an error element







STEP 3: APPLICATION SETUP - TYPOGRAPHY VARIABLES
    DISPLAY FONT SIZE
        - small, large, medium font sizes for display elements

    TITLE FONT-SIZE
        - small, medium font sizes for title element

    LABEL FONT-SIZE
        - small, medium & large font sizes for label element

    BODY FONT-SIZE
        - medium & large font sizes for body element

    HEADLINE FONT-SIZE
        - small font size for headline element

    BASE FONT-SIZE
        - 62.5%

    FONT-WEIGHT
        - regular font weight
        - medium font weight

    PRIMARY FONT
        - dm serif display & serif as fallback

    SECONDARY FONT
        - dm sans & sans-serif as fallback








STEP 4: APPLICATION SETUP - BOX STYLING VARIABLES

    BORDER RADIUS
        - 4 pixel border radius
        - 8 pixel boder radius
        - border radius for pill element
        - border radius for circular element

    BOX SHADOW
        - 20% opacity black shadow with a blur level of 8 pixel in a y-direction of -1 pixel
        - 30% opacity black shadow with a blur level & spread level of 4pixel & 1 pixel respectively in a y-direction of 2 pixel.







STEP 5: APPLICATION SETUP - SIZE VARIABLES
    HEADER HEIGHT
    MOBILE NAVIGATION HEIGHT
    SECTION GAP







STEP 6: APPLICATION SETUP - TRANSITION VARIABLES

    NOTE: this variables are setup in the root pseudo-seletor UNDER MEDIA QUERY WHOSE 'PREFERS-REDUCED-MOTION' IS SET TO 'NO-PREFERENCE'
    TRANSITION TIMING FUNCTION
        - utilizing a cubic bezier function (accelaration of the transition is plotted with a Bezier curve {xaxis-progression & yaxis-time})
        - start bezier curve handle position of (.2, 0)
        - end bezier curve handle position of (0, 1)

    SHORT TRANSITION
        - duration of 200ms
        - timing function of our custom bezier curve

    LONG TRANSITION
        - duration of 500ms
        - timing function of our custom bezier curve







STEP 7: APPLICATION SETUP - THEME VARIABLES

    here, we aim to polymorphorsize our color variables
    such that the same css variable will reference two different properties depending on the context of the page. this context is determined by the value of an attribute.

    once this is done, color of elements on the page can connect to a variable & the property will change depending on the value of an attribute on the page. this value can simply be changed via javascript.

    in step 2, 
    we categorize the coloring of our page into background, primary, badge-btn, outline, alpha e.t.c 
    we then css variable for each category FOR EACH THEME (light & dark) such that we have --light-background, --dark-background, --light-primary, --dark-primary e.t.c

    in this step,
    we will create css variables for each category
    then via css attribute styling if any element has the attribute 'data-theme' set to 'light' the category css variables we just created will reference the light category css variables we created earlier.
    then also via css attribute styling if any element has the attribute 'data-theme 'set to 'dark', the same category css variables we just created
    such as '--background: --light-background' e.t.c
    actually, this attribute will be placed in the html element thus every descendant can utilize the variable 







STEP 8: APPLICATION SETUP - RESET STYLING
    ALL ELEMENTS
        - zero margin & padding
        - border-box box sizing

    INLINE ELEMENTS
        - set the block display of inline elements 'a', 'img', 'button', 'span'

    INPUT & BUTTON ELEMENT
        - set font property to inherit
        - none background & none border

    LIST & LINK ELEMENT
        - no list style for li element
        - no text decoration for anchor element
        - set color value to inherit for anchor element

    IMAGE, INPUT & BUTTON ELEMENT
        - auto height for img element
        - 100% width of input element
        - set color value to inherit for button element
        - set pointer cursor for button element

    HTML ELEMENT
        - setup font family & font-size
        - smooth scroll behaviour
        - set webkit tap highlight color to transparent

    BODY ELEMENT
        - display: flex, column-flex-direction, zero-opacity
        - size: minimum height of 100vh, top padding of header-height, bottom padding of mobile nav height
        - color: background color set to 'background variable', text color set to 'on-background variable'
        - font: set font-size, font-weight, letter-spacing, line-height
        - animation: setup fade animation such that in short transition time with the transition timing function variable the opacity changes from 0 to 1

    MAIN ELEMENT
        - flex grow of 1






STEP 9: APPLICATION SETUP - FONT SETTING UTILITY CLASSES
    we categorise element on pages in our web-app by there font setting into "display", "title", "label", "body" "headline".
    and each category can have a small, medium & large version such that we have "display-small", "display-medium", "display-large" e.t.c

    therefore we would create utility class which specify the font setting for each category.
    font-settings such as font-size, font-weight, font-family, letter-spacing, line-height.

    the classes are
    "display-{large/small/medium}", "headline-small", "title-{small/medium}", "body-{medium/large}" 






STEP 10: APPLICATION FEATURE - HEADER COMPONENT
    THE LAYOUT
        - the header component is a flexbox with 4 items
        - the logo, the navigation-links, the theme-switch button, the saved-recipes button
        - the navigation links to not show in mobile view
        - the saved-recipies button is actually a link to the saved recipes page
        - the logo & theme switch button container encapsulates two version 'the light theme version' & 'the dark theme version'. but only one displays depending on the theme of the page
        - CHECK STEP-1 IN documentation.txt

    THE STYLING
        - the hover interaction of the navigation-links & theme-switch button will be encapsulated in a class
        - the styling of the theme-switch button will be encapsulated in a reusable class "icon-btn"
        - the styling of the saved recipes button will be encapsulated in a reusable class "btn" & "btn-primary"
        - CHECK STEP-2 IN documentation.txt

    THE BASIC INTERACTION
        - when the the theme-switch button is clicked, the theme of the page changes.
        - CHECK STEP-3 IN documentation.txt






STEP 11: APPLICATION FEATURE - MOBILE NAVIGATION COMPONENT
    THE CONCEPT
        - this application features 4 pages 'home page', 'recipes page', 'saved recipes page' & recipe detail page
        - this application has a mobile navigation component situatd at the bottom of the page
        - the mobile navigation encapsulate 3 link, 'link to the homepage', 'link to the Recipes page' & 'link to the Saved recipes page'
        - two items describe the link. an icon & a text(label)

    THE LAYOUT
        - this component is implement with an unordered list.
        - 1 ul element & 3 li element
        - the li element encapsulate the anchor element so it becomes a link.
        - the anchor element encapsulates a material icon & a text.
        - CHECK STEP-4 IN documentation.txt

    THE STYLES
        - the mobile navigation is positioned at the bottom of the screen, at a certain height and with viewport width
        - we want the navigation link icon container to have a grayish background color when the navigation link is hovered upon
        - we want the active navigation icon container to have a different background color
        - we want the active navigation icon container material icon to have a 100 percent FILL
        - CHECK STEP-5 IN documentation.txt






STEP 12: APPLICATION FEATURE - THE BANNER COMPONENT

    THE CONCEPT
        - basically, each page is divided into 3 parts Header, Main, Footer.
        - the Main part of the hompage has different sections.
        - the first section is the banner compnent which basically has 4 items
        - a background image, an heading text, a search-box, a label text 
        - the banner content is vertically center and horizontally centered
        - the search box constitute a dummy icon, a search field & a search button.
        - the heading text font-settings is of the category "DISPLAY-LARGE"
        - the label text font-settings is of the category "LABEL-SMALL"
        - CHECK STEP-6 & STEP-7 IN documentation.txt

