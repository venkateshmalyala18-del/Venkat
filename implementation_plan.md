# Implementation Plan - Company Selection for SEO Rankings

Add a company selection screen to the Search Engine Optimization skill. Clicking the skill will display the company names, and clicking a company will show its specific ranking images.

## User Review Required

> [!IMPORTANT]
> The navigation has been updated so that when you are inside a company's rankings view, the main "Back" button at the top left of the overlay goes back to the company list view instead of closing the overlay. Clicking "Back" from the company list view will close the overlay.

## Proposed Changes

### Portfolio Page

We will update [index.html](file:///c:/Users/Admin/Downloads/Venkat/index.html) to incorporate the selection screen, update the CSS, and add Javascript handlers.

#### [MODIFY] [index.html](file:///c:/Users/Admin/Downloads/Venkat/index.html)

##### 1. CSS Styles
Add custom styles for the company cards:
- `.company-grid`: Grid layout for the company cards.
- `.company-card`: Hoverable and animated card containers.
- `.company-logo`: Visual icon wrapper.
- `.company-name`: Typography for company titles.
- `.company-desc`: Summary text styling.
- `.company-btn`: Action button highlighting when hovering the card.

##### 2. HTML Markup
Reorganize `#seoOverlay`'s structure inside `.ov-inner`:
- Add `#seoCompanySelect` container for the company cards grid.
- Add `#seoRankingsDetails` container containing the separate GeekOnDemand and MIRAJ IT Consultancy ranking grids.
- Set up an ID for the header title (`#seoOvTitle`) and update the back button to call `handleSeoBack()`.

##### 3. JavaScript Logic
- Add state variables to track the current view (`currentSeoView`) and selected company.
- Update `openOverlay('seoOverlay')` to reset to the company list view on open.
- Implement `selectSeoCompany(companyId)` to display the selected grid, update the header title, and scroll the view to the top.
- Implement `handleSeoBack()` to navigate back to the company list or close the overlay.
- Uncomment `var carouselData = [];` to fix a JavaScript error on the Creative Designs overlay.

## Verification Plan

### Manual Verification
1. Open `index.html` in a web browser.
2. Click the "Search Engine Optimization" skill block.
3. Verify that the company selection screen displays "GeekOnDemand" and "MIRAJ IT Consultancy" cards.
4. Click on "GeekOnDemand" and verify that only GeekOnDemand rankings are shown, and the header title updates.
5. Click the "Back" button and verify it returns to the company selection screen.
6. Click on "MIRAJ IT Consultancy" and verify its rankings are shown.
7. Click the "Back" button to return to the selection screen, then click "Back" again to close the overlay.
8. Click on "Content & Creative Design" skill and verify the overlay opens without any JavaScript crashes.
