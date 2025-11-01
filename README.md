# DIT3-1-DELEON-JASMINE-ROBELLE-ACT05

1. How did you implement CRUD using SQLite?
In the NoteKeeper app, I implemented CRUD operations using Room, which is a wrapper over SQLite. Creating notes was done with the @Insert annotation in NoteDao. Reading notes used @Query and was collected as a Flow in the ViewModel so the Compose UI updates automatically. Updating notes utilized @Update, and deleting notes used @Delete. All database operations were performed through the ViewModel to keep the UI and data layers separate.

2. What challenges did you face in maintaining data persistence?
One challenge was ensuring that notes remained stored after closing the app. Initially, using temporary lists or cache caused notes to disappear. Another challenge was synchronizing the Compose UI with database updates, which required mutable state lists and unique note IDs to track edits and deletions. Handling database versioning for future updates also needed attention to avoid crashes.

3. How could you improve performance or UI design in future versions?
For performance, I could implement Paging 3 for large note lists and optimize Room queries for filtering or searching. UI improvements could include swipe-to-delete with undo, adding categories or tags, persistent dark mode using SharedPreferences, and animations for adding or deleting notes. Using Material 3 theming would also make the interface more visually consistent and user-friendly.
