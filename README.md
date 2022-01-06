
| User should be able to . . .                                                         |             |
| :----------------------------------------------------------------------------------- | ----------: |
| Visit the deployed pages on GitHub pages, with link in the About section of the Github repo |    1 |
| See bought items styled differently from unbought items                                   |        1 |

| Events                                                                                |             |
| :----------------------------------------------------------------------------------- | ----------: |
| On the home page (`'/'`), Login and Signup using the login and signup form. On success, redirect to the `/list` page   |        1 |
| Logout by clicking the logout button                                                       |       1 |
| If a non-logged-in user tries to visit the list page, redirect them to the login page     |       1 |
| On the list page load event, fetch the list itemss from supabase and render them to the page. Note that list items should have a quantity and an item name. Call your `displayShoppingListItems()` function to do this work.        |        2 |
| Add a list item to supabase by using the input and button.                                     |        2 |
| When a list item is added, clear out the shopping list and render the updated list of shopping items.       |        2 |
| When a user clicks a list item, it becomes bought. Update this state in supabase, clear out the shopping list, and re-fetch and redisplay the updated items. Call your `displayShoppingListItems()` function to do this work.                |        2 |
| When a user clicks delete all shopping list items, delete them. Update this state in supabase, clear out the shopping list, and re-fetch and redisplay the updated items. Call your `displayShoppingListItems()` function to do this work.               |        1 |


| Functions                                                                                |             |
| :----------------------------------------------------------------------------------- | ----------: |
| ASYNC: `createItem(item)` : create a item in supabase for the logged-in user |1|
| ASYNC: `deleteAllItems()` : delete all items  in supabasefor the logged-in user |1|
| ASYNC: `getItems()` : get all items in supabase for the logged-in user |1|
| ASYNC: `buyItem(id)` : complete this items in supabase for the logged-in user |1|
| PURE: `renderItem(item)` : takes in an item object and returns a DOM element |1|
| IMPURE: `displayShoppingListItems()` : fetchest the items, clears out the list, and redisplays them |1|


## HTML setup

- form with a number input, a text input, and an add new item button
- delete list button
- "destination div" to inject our list items into

## Events
1) on load
  - fetch and display user's existing list items
    - call supabase to fetch all shopping items for this user
    - loop through those items, create DOM elements, and append -- render items differently if "bought: true"
2) submit 'add item' form
  - add the new item and quantity to the list
    - send the new item to supabase and create a new row
    - clear out the old list
    - fetch the list again
    - loop through those items, create DOM elements, and append -- render items differently if "bought: true"
3) user clicks "2 pounds of flour"
  - "2 pounds of flour" counts as "bought" and is crossed out from the list
    - update 'bought' to true in the database
    - clear out the old list
    - fetch the list again
    - loop through those items, create DOM elements, and append -- render items differently if "bought: true"
4) on click delete list button
  - redisplay all items (which should ne an empty list now)
