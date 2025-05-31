import pygame
import random
from pygame.locals import *
import time

def changeBackground(img):
    background = pygame.image.load(img)
    bg = pygame.transform.scale(background, (screen_width,screen_height))
    screen.blit(bg,(0,0))

pygame.init()
pygame.display.set_caption('Recycle Marathon')
screen_width = 900
screen_height = 700
screen = pygame.display.set_mode([screen_width,screen_height])

class Bin(pygame.sprite.Sprite):
    def __init__(self):
        super(). __init__()
        self.image = pygame.image.load('').convert_alpha()
        self.image = pygame.transform.scale(self.image, (40,60))
        self.rect = self.image.get_rect()

class Recyclable(pygame.sprite.Sprite):
    def __init__ (self):
        super(). __init__()
        self.image = pygame.image.load('').convert_alpha()
        self.image = pygame.transform.scale(self.image, (40,40))
        self.rect = self.image.get_rect()

images = ["","",""]

item_list = pygame.sprite.Group()
allsprites = pygame.sprite.Group()
plastic_list = pygame.sprite.Group()

for i in range(50):
    item = Recyclable(random.choice(images))
    item.rect.x = random.randrange(screen_width)
    item.rect.y = random.randrange(screen_height)
    item_list.add(item)
    allsprites.add(item)
