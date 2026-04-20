# Mobile-Arch
CS-360-10061-M01 Mobile Architect &amp; Programming 2026 C-2 (Mar - Apr)

Inventory App — Mobile2App Warehouse Tracker
CS-360 Mobile Architecture & Programming | Southern New Hampshire University
Developer: Kelly Reinersman

About This Project
This repository contains the completed Inventory App developed throughout CS-360. The app is a fully functional Android warehouse inventory tracking tool built in Android Studio using Java and SQLite. It was developed across three projects — planning and proposal (Project One), UI design (Project Two), and full code implementation (Project Three).
App Summary and User Needs
The Inventory App was built for the Mobile2App Company to give warehouse workers, store associates, and shift managers a fast and reliable way to track stock levels from their mobile device. The app was designed to address three core user needs: the need for quick on-demand inventory access, the need for secure multi-user login, and the need to be alerted immediately when an item runs out of stock.

Drawing on personal experience managing inventory at both Walmart and McDonald's, the design was grounded in real-world conditions — employees working quickly under time pressure, sometimes with gloves on, in environments where a miscounted item or missed restock can cause real problems during a shift. Every design and development decision was made with those users in mind.
Screens and UI Design
The app includes three primary screens:

Login Screen — secure username and password login with account creation for new users
Inventory Grid Screen — scrollable list of all items with quantity controls, add and delete functionality, and an out-of-stock alert banner
SMS Notification Screen — permission request screen allowing users to enable or disable SMS alerts

The UI was designed following Android Material Design 3 guidelines with a dark navy color scheme and gold accents chosen specifically for warehouse environments where screens are viewed repeatedly under harsh lighting. Large tap targets on the quantity buttons accommodate users working quickly or wearing gloves. The single-screen-per-task layout and bottom navigation bar keep the number of taps required to complete any action to a minimum. These design choices were successful because they were tied directly to the real needs of the three user types identified during planning — the warehouse associate, the shift manager, and the new or part-time employee.
Development Approach
The app was coded using a layered approach — starting with the database layer, then the activity logic, and finally connecting everything through the UI. A dedicated DatabaseHelper class was built to handle all SQLite operations including creating tables, inserting records, querying data, updating quantities, and deleting items. Keeping all database logic in one class made it easy to debug and reuse across multiple activities.

In-line comments were added throughout the code to explain the purpose of each major block, and consistent naming conventions were used across all files to make the codebase readable to anyone reviewing it. This approach of separating concerns — keeping database logic, UI logic, and navigation logic in their own layers — is a strategy that scales well and would apply directly to any future Android or software development project.
Testing
Testing was done continuously throughout development using the Android Emulator in Android Studio. After each major feature was added the app was run and tested for the specific functionality just implemented before moving on. Key test scenarios included creating a new user account and verifying it persisted after closing the app, logging in with correct and incorrect credentials, adding items and confirming they survived an app restart, long pressing to delete items, adding an item with zero quantity to trigger the out-of-stock alert, and testing both the allow and deny paths on the SMS permission screen.

This testing process is important because it catches bugs close to where they are introduced rather than discovering them all at once at the end. During testing it was discovered that inventory items were not persisting between sessions, which revealed that the original ArrayList-based approach needed to be replaced with a proper SQLite implementation — one of the most important improvements made during Project Three.
Innovations and Challenges
The biggest challenge throughout the project was the file structure and organization in Android Studio. Early on, new Java classes were accidentally created in the test folder instead of the main source folder, which caused the build to fail with "cannot find symbol" errors. Working through that problem built a much stronger understanding of how Android Studio organizes a project and how the manifest, layout files, and Java classes all have to reference each other correctly.

Another area of innovation was the UI color scheme. Rather than using the default Android theme, a custom dark navy and gold palette was designed from scratch using drawable XML files for gradients, rounded buttons, and card backgrounds. This gave the app a polished, professional look that stands out from a typical student project and reflects the kind of attention to design detail that real users notice.
Strongest Component
The database implementation is the component that best demonstrates the knowledge and skills developed throughout this course. The DatabaseHelper class handles a complete set of CRUD operations — Create, Read, Update, and Delete — across two separate tables (users and inventory items). The login system validates credentials against the database, account creation checks for duplicate usernames, and all inventory changes persist across sessions. Connecting that database layer to a functional UI with real-time updates, and then integrating it with the SMS notification system, brought together everything covered in the course — from UI design and user-centered thinking to Java programming and Android architecture — into one working application.
Technologies Used
Java
Android Studio
SQLite
Android SensorManager (Module Six assignment)
Material Design 3
