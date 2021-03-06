meteor-todo
===========

A simple-to-use but highly expandable to-do list with support for `#tags`, `@people`, due-dates, and archiving. Touch- and mobile-friendly. Now with API!

**This todo list currently *does not* support collaboration or multi-users.** This was an intentional design decision, as I never like having my todo list accessible by others. However, this is Meteor, folks. Adding user accounts is *maybe* a five-line ordeal. Feel free to Pull-Request if you feel strongly about it! 2015 roadmap includes a default-CSS redesign and optional multi-user functionality. Collaboration welcome.

# New Features
- **Mar 14**
 - API endpoints for [your consideration](https://github.com/j6k4m8/todosh)
- **Feb 24**
 - **Touch Events**: Swipe a task right to mark it as complete. Swipe left to procrastinate and push its deadline off to tomorrow.
 - **Smart Titlebar**: Your titlebar now shows more information about your day: `todo [4 | 6] 40%` means that you have completed 4 tasks and have 6 remaining for the day. You're 40% done with your day!
 - **"Hard" Deadlines**: I get into the habit of setting deadlines before the actual due-date of the project, so **prefixing your task with a `!` makes it a hard deadline**: The task shows up with a vivid red left-border to indicate that you should think twice before swiping left!

# Usage
## Notifications
After you enter your Pushbullet API key in the `settings.json` file, you will receive an update every six hours with a list of the next six hours' worth of tasks.

## Creating a new TODO 
Type a new todo in the left input (focus it by typing <kbd>n</kbd>). Mark tags with `#`. Indicate people with `@`. Nest due-dates in `` ` `` tick marks. Due dates are handled intelligently by the [chrono.js](https://github.com/wanasit/chrono) library, so typing something like "Next friday at 5pm" just *works*.
![screenshot 2014-12-26 at 2 05 49 pm](https://cloud.githubusercontent.com/assets/693511/5558955/60b94214-8d08-11e4-8104-f367b351d96c.png)

`#tags` and `@people` will autocomplete with <kbd>TAB</kbd>. Potential options are shown in a small dropdown which is poorly styled right now. **[EDIT]** Now it's prettier. Screenshots forthcoming later on.
![screenshot 2014-12-26 at 2 10 20 pm](https://cloud.githubusercontent.com/assets/693511/5558987/0b2b200a-8d09-11e4-9f89-f0b20d4b1015.png)

## Editing a TODO
Click an item in the list to open its control panel. Alternatively, use <kbd>j</kbd> and <kbd>k</kbd>, vim-style, to navigate through the rows. Use <kbd>v</kbd> (for **v**isibility) to open or close the currently selected item.
![screenshot 2014-12-26 at 2 13 37 pm](https://cloud.githubusercontent.com/assets/693511/5558994/6a6b8492-8d09-11e4-9d71-4be3ffa81ea2.png)

Click on a duedate button to set the due-date. The list auto-sorts by duedate, soonest (most urgent) at the top.

Items with tagged People will show the individuals' contact information in their dropdown panels. If no information is available, they will appear as input boxes. Type an email or phone number to set the information for that user: All tasks with that tagged user will auto-update to show their information.
![screenshot 2014-12-26 at 2 17 00 pm](https://cloud.githubusercontent.com/assets/693511/5559003/e096278a-8d09-11e4-8485-508674b368a4.png)

After submitting an email, the email can be clicked to autopopulate the email client in a new tab.

Use <kbd>?</kbd> to open the keyboard-shortcuts cheatsheet:
![screenshot 2014-12-26 at 2 19 18 pm](https://cloud.githubusercontent.com/assets/693511/5559016/31275084-8d0a-11e4-9a31-8e841f384529.png)

## Searching for a Task
The query-bar (focus with <kbd>/</kbd>) searches via fuzzy-string-matching: For instance, to find the task with a title of `Go to the store`, you can type `go to store`, `store`, `gttst`, or any variation thereof. Hitting enter from the searchbar auto-selects the first task that matches the query. Clearing the query-bar resets the list to include all tasks again.

## Complete a task
Complete a task by hitting its checkbox, or by typing <kbd>ctrl</kbd>+<kbd>return</kbd> when it's selected. It will become greyed-out and italic, and move to the end of the list. To toggle visibility of completed tasks, use <kbd>*</kbd>. To archive all completed tasks, use <kbd>|</kbd>. As of now, there is no way to unarchive an item. They are kept with the expectation that this feature will be developed in the future.

# Delete a Task
Delete a task with <kbd>shift</kbd>+<kbd>3</kbd> (<kbd>#</kbd>, same as Gmail). This cannot be undone.
