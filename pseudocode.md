Team Members: Peyton, Nicole

# Initalize Game

 Initalize Resolution (Full Screen to Monitor)
 Intialize Score
 Intialize Connected Devices
 Initalize Menu
 Initalize Buttons

# Start game

    While game is running:
    Open Menu Screen
    Play Music
    if start pressed:
        go to stage select
        play stage select music
    if right pressed:
            go to right
    if left pressed:
            go to left
    if confirm button pressed:
        select gamemode
    if Training:
        go into training match
    if 1P VS. CPU:
        select difficulty
        go into regular match
    if 1P vs 2P:
        select playing style
        go into regular match

# Round

    if in match:
    randomize first hitter
    if hitter is player1:
        ball on left side
    if hitter is player2:
        ball on right side
    if ball hit:
        send to right side
    if ball hit and holding left:
        curve ball left
    if ball hit and holding up
        increase speed
    if ball hit and holding right
        curve ball right
    if ball hit and holding down:
        lower speed give ball control
    if ball in zone 1:
        score for player 1
    if ball in zone 2:
        score for player 2

# training

    while training is on:
    add rules to pause
    if rules pressed:
        show optionMenu
        take gamespeedinput
        take points input
    if back pressed:
        exit option menu.
    
# pause

    if start pressed in round:
        open pause menu
        pause game
    if ok button pressed:
        unpause game
    if main menu pressed:
        go back to main menu

# Power up

    spawn powerup randomly
    poweruptype freezing, invisible, and charging
    if powerup collected:
        use random poweruptype
    if freezing:
        freeze oppnent
    if inivisble:
        hide opponent bar
    if charging:
        initalize meter image
        wait for button presse
        if button press:
            add meter progress by 1
            add color to meter
        if meter progress is 7:
            release ball at 2x speed.
