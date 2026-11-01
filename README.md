# TaskMate
Offline-first task allocation application for nurses, midwives and ward superisors.

# TaskMate Shift Management Application for Akobo Teaching Hospital

## Project Overview

TaskMate is an Android application developed for midwives and ward supervisors at Akobo Teaching Hospital to organize, track, and review clinical duties during shifts. In maternity wards, handovers traditionally rely on verbal communication or paper notes, leading to disorganization, delayed medication, missed rounds, and poor shift visibility. TaskMate addresses these challenges by offering a digital companion tailored for hospital wards, enabling staff to create tasks, monitor active duties, transition progress states, and review completed activities before shift closure.

## Video Demo

Video Demo Link:[Watch TaskMate App Demonstration](https://youtu.be/XKJu3q-md3s?si=YaH8rp4FB53Sgqzn)

## CS50x 2026 AI Disclosure

In accordance with CS50x 2026 Academic Honesty policies, AI assistance was utilized. AI tools assisted with architectural guidance, UI styling, SharedPreferences JSON persistence, code refactoring, lint warning resolution, and documentation drafting. All generated code was thoroughly reviewed, tested, and validated by the student, who assumes full ownership of the final project.

## Implemented Features

### Shift Task Creation
Midwives and supervisors can add new ward duties during active shifts by clicking the add task button. A custom dialog prompts for a description, automatically requesting focus and displaying the keyboard for entry.

### Persistent Local Task Storage
To provide local data persistence, TaskMate incorporates automatic storage using Android SharedPreferences and native JSON serialization. Tasks are retained across ordinary application restarts and device reboots, though uninstalling the app or clearing its data removes stored data.

### Real Time Shift Dashboard
The home screen displays a healthcare dashboard featuring status counter cards. These cards automatically reflect the total number of pending, in progress, and completed shift tasks.

### Interactive Task Management
Tapping any active task card opens an action menu allowing staff to update progress. Tasks can be transitioned between Pending, In Progress, and Completed states, or deleted when no longer required.

### Filtered Navigation Views
TaskMate includes an interactive navigation header supporting four views. Home displays the complete shift dashboard and all duties. Tasks filters the list to display active duties. History displays an organized log of completed tasks. Settings provides application information and verification.

## Key Project Files and Architectural Role

MainActivity.java serves as the primary activity controller, managing user interactions, navigation tabs, UI updates, and JSON storage.

Task.java defines the task data model encapsulating titles, status enums, and native JSON serialization methods.

activity main.xml provides the interface layout housing branding headers, navigation tabs, overview cards, and dynamic task containers.

colors.xml defines the healthcare palette including dark navy headings, teal green buttons, slate text, and status card colors.

strings.xml contains localized string resources for headers, tab titles, dialog hints, counter formatting, and state messages.

bg card rounded.xml defines rounded corners, subtle borders, and background shading for cards.

AndroidManifest.xml configures application metadata, theme definitions, keyboard resize behavior, and main launcher activity settings.

build.gradle.kts specifies build parameters, targeting Android SDK 37 with minimum SDK 24, Java 11 compatibility, and dependencies.

## Technical and Design Decisions

TaskMate utilizes a lightweight architecture prioritizing performance on entry level ward devices. Persistent storage uses native SharedPreferences paired with org.json rather than heavy database libraries, eliminating external dependencies, minimizing file size, and guaranteeing instant execution. Enums enforce strict state management, while programmatic view creation in MainActivity renders task cards efficiently and reliably.

## Technologies Used

Programming Language: Java 11
Target Platform: Android SDK 37 Minimum SDK 24
UI Frameworks: AndroidX, Material Design 3, AppCompat, ConstraintLayout
Data Storage: Android SharedPreferences and org.json
Build Automation: Gradle with Kotlin DSL

## Installation and Setup Guide

Clone the TaskMate repository, open the project in Android Studio, and allow Gradle to synchronize dependencies automatically. Connect an Android device with USB Debugging enabled, or launch an Android Virtual Device, then click Run in Android Studio to compile and install the application.

## How to Use TaskMate

To add a new task, tap Add New Task, enter a clinical duty description, and click Save Task. To update task status, tap any task card and select Mark as In Progress or Mark as Completed. To review shift history, tap the History tab at the top of the dashboard.

## Limitations and Future Improvements

### Current Limitations
Storage is local to the individual physical device without user accounts.

### Planned Future Improvements
Cloud Database Sync: Integrating Firebase or Room DB for real time synchronization between midwives and supervisors. Staff Assignment: Delegating tasks to specific midwife staff IDs. PDF Export: Generating shift reports for hospital records.

## Conclusion

TaskMate delivers a practical, robust digital shift management companion for healthcare professionals at Akobo Teaching Hospital. By combining persistent local storage with an accessible healthcare UI design, TaskMate streamlines daily ward workflows and enhances patient care organization.
