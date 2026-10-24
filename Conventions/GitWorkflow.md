# Git Workflow

## Git Commits
Prefer one logical change per commit.
>Don't be afraid to commit your changes in multiple commits. This benefits cherry picking for other branches, resolving merge conflicts and undoing changes.

Do not commit changes that don't compile.
>This will cause issues with the benefits mentioned above.
>If you did it anyway, use amend if possible or squash.
>Consult a senior if you need help with this.

If someone else is actively working on the same branch, be sure to communicate with them when you rewrite history on the origin (Force Push).
>Failing to do so might cause issues for them when they try to push their changes.

## Git Commit Messages
Message subjects should never longer then 72 characters, everything beyond that will vanish into the message body.

At the front of a commit message should be a keyword from this list:
- **feat:** Introduces new functionality or gameplay logic.
- **refactor:** Changes internal structure without changing observable behaviour.
- **rework:** Substantially changes existing functionality or its behaviour.
- **tweak:** Adjusts existing values or minor behaviour without introducing a new feature.
- **fix:** Corrects unintended behaviour or a defect.
- **docs:** Adds or modifies documentation; comments, .md files, UML diagrams, etc...
- **assets:** Adds, removes or modifies assets made by artists.
- **test:** Adds, removes or modifies automated tests.
- **deps:** Adds, removes, or updates third-party dependencies.
- **settings:** Changes to project configuration such as game engine project settings, CMake, build scripts, etc...

When possible add a scope in parentheses, this adds context:
- feat(player): Add fireball ability
- fix(spawner): Prevent instant respawn
- docs(uml): Update activity diagram
- settings(Unity): Adjust viewport resolution

Use imperative descriptions.
>Write "Add fireball ability", not "Added fireball ability"

Keep the subject concise, avoid words that aren't needed.
>Add **another** fireball ability.
>Prevent instant **unit** respawn.
>Update **the** activity diagram.
>Adjust **the** viewport resolution.

If you want to add more detail, do so in the message body.

In the Github Desktop app you'll notice 2 textboxes, one for the subject and the other one for the body.

Elsewhere you can define this by adding a blank line between them:
```
fix(spawner): Prevent instant respawn

When a unit is destroyed it resets the spawn cooldown preventing an instant respawn.
```

When using a console you seperate them as follows:
```
git commit -m "This is the subject" -m "this is the body."
```
>"[If multiple -m options are given, their values are concatenated as separate paragraphs.](https://git-scm.com/docs/git-commit#Documentation/git-commit.txt---messagemsg)"