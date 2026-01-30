# NoteKeeperApp

## 📝 Project Overview

**NoteKeeperApp** is an Android application that demonstrates local data persistence using a SQLite-based database. The app allows users to create, read, update, and delete notes, ensuring that data remains available even after the app is closed and reopened. This project focuses on CRUD operations, RecyclerView usage, and clean separation between UI and data layers.

---

## 🛠 Project Setup

* **Project Name:** NoteKeeperApp
* **IDE:** Android Studio
* **Template Used:** Empty Activity
* **Language:** Kotlin
* **Database:** SQLite (implemented using Room)

---

## 🎨 UI Design (activity_main.xml)

The main layout is designed to clearly display saved notes and provide easy note creation.

### UI Components:

* **RecyclerView** – Displays the list of saved notes
* **Floating Action Button (FAB)** – Opens a screen/dialog to add a new note

Each note item displays:

* Title
* Content preview
* Timestamp

---

## 🗄 Database Implementation

Although the task specifies SQLite, the app uses **Room**, which is an official Android persistence library built on top of SQLite.

### Database Structure:

**Table Name:** `notes`

**Columns:**

* `id` (Primary Key)
* `title`
* `content`
* `timestamp`

### Components Used:

* `@Entity` – Defines the notes table
* `@Dao` – Declares database operations
* `RoomDatabase` – Provides the database instance

---

## 🔄 CRUD Operations Implementation

### Create

* New notes are added using the `@Insert` annotation in `NoteDao`.
* Triggered by clicking the Floating Action Button (FAB).

### Read

* Notes are fetched using `@Query`.
* Data is exposed as a **Flow**, allowing the UI to update automatically when the database changes.
* Displayed using RecyclerView.

### Update

* Existing notes are edited using the `@Update` annotation.
* Updates are reflected immediately in the UI.

### Delete

* Notes are removed using the `@Delete` annotation.
* The RecyclerView updates automatically after deletion.

All database operations are handled through a **ViewModel**, ensuring separation of concerns between the UI and data layers.

---

## 💾 Data Persistence

* Notes are stored in the local Room database.
* Data persists even after the app is closed or restarted.
* This confirms proper SQLite-based persistence implementation.

---

## 📝 Reflection

### 1. How did you implement CRUD using SQLite?

In the NoteKeeperApp, CRUD operations were implemented using **Room**, which is a wrapper over SQLite. Creating notes was handled with the `@Insert` annotation in `NoteDao`. Reading notes was done using `@Query`, and the results were collected as a **Flow** in the ViewModel so the UI updates automatically. Updating notes used `@Update`, while deleting notes used `@Delete`. All database operations were performed through the ViewModel to maintain a clean separation between the UI and data layers.

---

### 2. What challenges did you face in maintaining data persistence?

One challenge was ensuring that notes remained stored after closing the app. Initially, using temporary in-memory lists caused notes to disappear. Another challenge was synchronizing the UI with database updates, which required proper state handling and unique note IDs to track edits and deletions. Database versioning also needed attention to avoid crashes when making future schema changes.

---

### 3. How could you improve performance or UI design in future versions?

For performance improvements, I could implement **Paging 3** to efficiently handle large note lists and optimize Room queries for searching or filtering. UI enhancements could include swipe-to-delete with undo, categories or tags for notes, persistent dark mode using SharedPreferences, and animations for adding or deleting notes. Adopting **Material 3 theming** would also improve visual consistency and user experience.

---

## 🎯 Learning Outcomes

* Implemented local data persistence using SQLite (Room)
* Performed full CRUD operations
* Used RecyclerView to display dynamic data
* Applied MVVM architecture principles
* Ensured data persistence across app restarts

