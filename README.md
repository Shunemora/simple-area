%%shunem_preloaded --background Loop -O

# Program to stay inside a bounded area

# Start to drive forwards
tank_drive.on(SpeedPercent(50), SpeedPercent(50))

# Set up a loop to run the set commands
# over and over again
while True:
    # Save the light sensor reading
    light_level = colorLeft.reflected_light_intensity_pc
    
    # Display the light sensor value
    # in the simulator Output display window
    print('Light_left: ' + str(light_level))

    if light_level < 40:
        # Drive backwards a set distance 
        tank_drive.on_for_rotations(SpeedPercent(-50),
                                    SpeedPercent(-50),
                                    2)

        # Drive in a turn for 2 rotations
        # of the outer motor
        tank_turn.on_for_rotations(-100,
                                   SpeedPercent(75),
                                   2)

        # Drive forwards again
        tank_drive.on(SpeedPercent(50),
                      SpeedPercent(50))
        
        # Last line of if conditional block
        
    # Last line of while loop block

# Program ends
