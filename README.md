cs56-games-simple-rpg
(W15) TBD: It looks like a promising game; the code base looks navigatable but trying to run it produces a really strange window that seems to randomly place blue colored squares on the main green square regardless of what key is pressed and can only be escaped from. It looks fairly extensible but has a bad bug currently and Im having difficulties running it(Paz Zait-Givon)

Running the Game
=====================
* If running at CSIL, run `ant build` and then `ant runcli` (for the CLI version of the game) or `ant run` for the GUI version.
* If running through an SSH instance of CSIL, make sure an xserver instance is running for the GUI version and run the above commands.
* If running on a local instance after cloning, the classpath for JUnit must be fixed in the `build.xml` file.
  + Go to [this link]( https://github.com/junit-team/junit/wiki/Download-and-Install) and download the JAR files (junit and hamcrest).
  + Create a `java` directory in your home folder (`cd && mkdir java`)
  + Run cp ~/Downloads/{junit-X.Y.jar,hamcrest-core-XX.YY.jar} where X, Y, XX and YY are corresponding versions of the JAR files you downloaded.
  + Add the following lines to your `.bash_profile` (or to your `.zshrc` if you use zsh):
    ```
    export JUNIT_HOME="$HOME/java"
    export PATH="$PATH:$JUNIT_HOME"
    export CLASSPATH="$CLASSPATH:$JUNIT_HOME/junit-X.Y.jar:$JUNIT_HOME/hamcrest-core-XX.YY.jar"
    ```
  + Now replace all instances of `/cs/faculty/pconrad/public_html/cs56/lib/junit-4.8.2.jar` in the `build.xml` with `${env.JUNIT_HOME}/junit-X.Y.jar` .
  + Now you should be able to build and run locally!
---------------------------------------------------

The first version of the game is a CLI version, with a non-functional GUI implementation.

![](http://i.imgur.com/rll8hnf.png)

Project History
===============
```

YES | bronhuston | barasuishou | A simple rpg game
— Edit
 W14 | bronhuston 5pm | barasuishou | A simple rpg game
```

Features for the CLI version:
- Ability to move
- Basic turn-based battle
- Random encounters

A sample playthrough might look like this:

Output:
Main Character HP: 100/100 MP: 100/100 XP: 0/100
Current Location: (0,0)

Options:
1. Move Left
2. Move Right
3. Move Up
4. Move Down
5. Quit

Input:
2

Output:
You have encountered an enemy.
Main Character LV: 1 HP: 100/100 MP: 100/100 XP: 0/100
Current Location: (1,0)
Enemy LV: 1 HP: 20/20 MP 15/15

Options:
1. Attack
2. Run Away
