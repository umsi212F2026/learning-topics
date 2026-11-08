# Least privilege

### vs-authorization

Jun sets up a program on his laptop that sorts his family's photos into albums. When he installs
it, he lets it read the photo folder and add entries to the album list, but not delete photos.
Later, after an update, the program tries to delete a blurry photo. The laptop checks the
permissions the program was given, finds that deleting isn't among them, and refuses.

#### a

When the program tries to delete the photo, the laptop decides whether it may. Which term best
describes that?

1. Authorization
2. Least privilege
3. Neither

#### b

Did Jun's choice about what to let the program do follow the principle of least privilege?

1. Yes
2. No

### catch-pick

A family's photo workflow runs each night. A program copies new photos from everyone's phones into
a shared folder, and then an agent writes a caption file for each new photo. The agent has
permission to read the photos and to write caption files, and nothing else.

Which of these uses the term least privilege correctly?

1. Least privilege is broken here, since the agent can write caption files at all.
2. Limiting the agent to reading photos and writing captions follows least privilege.
3. Least privilege means each part may touch only one thing the workflow keeps.
4. Least privilege is the check that runs each time the agent opens a photo.

### catch-newsletter

A volunteer sets up a program that sends a hiking club's weekly newsletter by email. All it needs
is to read the members' email addresses. To save time, he gives it permission to read, change and
delete everything on the club's shared drive. He says:

"It's fine. The program is authorized, so we're following least privilege."

What is wrong with that? Answer in two or three sentences, in your own words.
