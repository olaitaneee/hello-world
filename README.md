# hello-world
just another repository(my first repository)
# -*- coding: utf-8 -*-
"""
Created on Sat Jul  4 12:06:49 2020

@author: kazeem
"""

import pygame
import game_function_r as gf_r
from setting_r import Setting
from ship_r import Ship

def run_game():
    """Initialize pygame settings"""
    #initialize pygame
    pygame.init()
    #set up settings class
    ai_setting = Setting()
    #set up display screen
    screen = pygame.display.set_mode(
            (ai_setting.screen_width, ai_setting.screen_height))
    #set up diaplay icon
    pygame.display.set_icon(ai_setting.icon)
    #makes a ship
    ai_ship = Ship(screen, ai_setting)
   
   #game main loop
    while True:
        #check for events
        gf_r.check_events(ai_ship)
        #update the ships position
        ai_ship.update()
        #updates the game display window
        gf_r.update_screen(screen, ai_setting, ai_ship)
        
run_game()
