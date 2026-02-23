Great project! Here's a clean breakdown into reviewable steps:

**Step 1 — Add the HTML structure (no functionality yet)**
Add the search bar input and the four filter buttons to the page. Just hardcode them in the right place above the menu. At this point nothing works, but you can confirm the elements exist in the DOM and style them however you want.

**Step 2 — Wire up the search bar to filter by name/description**
Write a JavaScript function that listens for `input` events on the search bar. It grabs all `.menu-item` divs, lowercases the search term, and checks it against each item's `h3` and `p` text. If there's no match, set `display: none` on the item; otherwise show it. Test by typing a word you know exists (like "pepperoni") and confirming only matching items show.

**Step 3 — Wire up the category buttons**
Write a second function that listens for `click` on each button. Each button needs a `data-category` attribute (e.g. `data-category="signature"`) and each section or item needs a corresponding `data-category` attribute to match against. Clicking a button hides items not in that category and shows ones that are. Test each button individually to confirm the right items appear. Also confirm "All" shows everything.

**Step 4 — Make search and category filter work together**
Right now Steps 2 and 3 are independent, which means they'll conflict — filtering by category then typing in search could bring back hidden items. Consolidate the logic into a single `applyFilters()` function that checks _both_ the active category and the current search term at the same time. Both have to match for an item to be visible. Test by selecting "Classic" and then typing a word — only matching Classics should appear.

**Step 5 — Handle the active button state**
This is purely visual: when a category button is clicked, add an `active` class to it and remove it from the others. Write a CSS rule for `.filter-btn.active` (e.g. a different background color). This makes it clear which filter is selected. Test by clicking through all four buttons.

**Step 6 — Add a "no results" message**
After `applyFilters()` runs, check if every `.menu-item` is hidden. If so, show a message like _"No items match your search."_ If at least one is visible, hide the message. Test by typing total gibberish and confirming the message appears, then clearing it and confirming it disappears.
