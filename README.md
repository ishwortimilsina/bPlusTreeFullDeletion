Overall Status
We have written all the required code in the single allocated method i.e. _Delete. We have not created or implemented any self-made methods. We have created a global constant MIN_OCCUPANCY and set it to 0.5 ; to multiply to the space calculated later.

_Delete Code Flow
1. Create global constant MIN_OCCUPANCY and set to 0.5
2. Find if the current page is index or leaf
3. If Index, do following
i. Initiate the current index page
ii. Check if the index page has more than the allowed minimum space
iii. If yes, create sibling page
iv. Try redistributing
v. If failed, try merging as follows
a. Take the first entry of the current page
b. Add the entry in the sibling page
c. Delete the entry from the current page
d. Repeat until no entry left in the current page
e. To maintain the linked list, do the following
? If the sibling is on right side of the current page, set the previous page of current page as the left page of the sibling page and vice versa. If there is no previous page, just set the id -1 as the previous page of the sibling page
? If the sibling is on the left side of the current page, set the next page of current page as the right page of the sibling page and vice versa. If there is no next page, just set the id -1 as the next page of the sibling page
f. Get the last entry of the sibling page, tally it with the keys in the parent page to find out the key pointing to the current page. Pull it down to the sibling page. Delete the key from the parent page.
vi. If the parent page as no entry, set the root pointer to the current sibling page.
4. If the current page in LEAF, do the following
i. Initiate the current leaf page
ii. Check if the leaf page has more than the allowed minimum space
iii. If yes, Create sibling page
iv. Try redistributing
v. If failed, try merging as follows
a. Take the first entry of the current page
b. Add the entry in the sibling page
c. Delete the entry from the current page
d. Repeat until no entry left in the current page
e. To maintain the linked list, do the following
* If the sibling is on right side of the current page, set the previous page of current page as the left page of the sibling page and vice versa. If there is no previous page, just set the id -1 as the previous page of the sibling page
* If the sibling is on the left side of the current page, set the next page of current page as the right page of the sibling page and vice versa. If there is no next page, just set the id -1 as the next page of the sibling page
f. Get the last entry of the sibling page, tally it with the keys in the parent page to find out the key pointing to the current page. Delete the key from the parent page.
vi. If the parent page as no entry, set the root pointer to the current sibling page.