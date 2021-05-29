import sys, random, time
from os import system

def c(): system('clear')

class Room():
  def __init__(self): pass
  def play(self):
    print('This room hasnt been initialized yet.')

class Game_Over(Room):
  def play(self):
    time.sleep(5)
    a = [
      'My dog could do better than you.',
      'Wow... That was amazing...',
      'Hah! Nice try.',
      'Your worse than your dad\'s jokes.',
      'You stink worse than something that stinks.'
    ]
    print(random.choice(a))
    time.sleep(3)
    print('Game Over!')
    sys.exit()

class Win(Room):
  def play(self):
    time.sleep(5)
    a = [
      'Absolutely amazing!',
      'Your friends will be so proud.',
      'Terrific!',
      'Congrats!'
    ]
    print(random.choice(a))
    time.sleep(3)
    print('Game Over!')
    sys.exit()

class Intro(Room):
  def play(self):
    c()
    print('Welcome To A Adventure Game!\nObjective: \n\tFind the Map to Find The Titanic Remains, \n\tFind all the rare items on the ship\n\tthen sell them for a price of a life time')
    if not input('Ready? [y/n]: ') == 'y': sys.exit()
    c()
    print('You are onboard an submarine. You have managed to reach the bottom of the Atlantic Ocean. You have reached 13,000 feet down, You hope to find the Ship before your 90 day food rations give out. Youve been looking for the ship for about 3 days now, deciding what to do when you find it.\nYour options are:\n\t1. Sleep\n\t2. Activate Radar \n\t3. Continue ahead')
    o = input('Move? [1, 2, 3]: ')
    c()
    if o == '1':
      print('You Went to Sleep.Then had a rude awaking your submarine crashed into a iceberg. you look around as  your sub fills with water losing your air you slowly drown looking for the exit')
      return 'game over'
    elif o == '2':
      print('You Enable your radar and soon get a ping, you contine as the ping gets closer and closer you then stop right above the ping. :\n\t You and your friends put on scuba gear and swim down finding 2 parts of ship cut in half \n\t you contine finding a Bunch of crates and then realize that this is the titanic \n\t you turn to your friend realizing what you have found\n\t.\n You guys go around looking for valubles in the Ship.')
      return 'corridor'
    elif o == '3':
      print('You quickly scan your surroundings, for the ship. But the Darksea makes it hard to see anything.You unknowingly enter a Squids Teratory, Out of nowhere a Massive Squid comes up and Crushes your sub in half you tragicly get picked up and get split and half and ate by two squids.')
      return 'game over'

class Corridor(Room):
  def play(self):
    print(' You reach the end and turn on your head light. You turn and see two doors in front of you. Which one will you choose?\nYou can choose between the left one or the right one.\n\t1. Left\n\t2. Right')
    o = input('Room? [1, 2]: ')
    c()
    if o == '1':
      print('You enter the left room. You contine you ahead You take as step forward and you instantly know this is a mistake. You lose vison of your friend and everything else, and the floor beneath you colapes, sending you to fall backwards cuting your airtank relaseing your air.. You die due to water filling you suba mask.')
      return 'game over'
    elif o == '2':
      return 'bomb hold'

class Bomb_Hold(Room):
  def play(self):
    print('You enter the right room. You see sign that says Storage compartment which probably holds the valubles. There is a rusted padlock with password on top. You approach the padloc. You have six tries to guess the 1 digit password. Thats easy!')
    password = random.randint(0, 9)
    for _ in range(6):
      if input('[keypad]: ') == str(password):
        c()
        print('Crack! The rusty Lock snaps opens and you hear a creaking sound has the door opens The crates are visible in the water. You and your friend pick up the crate and then exit back to the sub, and run across to the other end of the sub to get a tool to open it, you manage to get a crowbar and open the crate You notice the timer for the your airtanks are low, it reads [9:35]. 9 minutes, left.')
        return 'bridge'
      else:
        c()
        print('Crack! "The numbers on the lock break!" its now imposable to open the lock.')
    print('The lock cant be open with no numbers so your hopeless. So close, yet so far.')
    return 'game over'

class Bridge(Room):
  def play(self):
    print('You enter the sub. There are three crates waiting with broken locks. You glance at the timer again [6:12]. You need to act fast. \nYour options are to:\n\t1. Break the locks and take the crate to the sub\n\t2. Leave them\n\t3. Take the crates one by one')
    o = input('Move? [1, 2, 3]: ')
    if o == '1':
      c()
      print('You break the locks and take the creates the crate top comes off losing all the valuables with it.')
      return 'game over'
    elif o == '2':
      c()
      print('You go home with the one crate and split only $100.')
      return 'game over'
    elif o == '3':
      c()
      print('You Take all creates with just enough airleft to leave.')
      return 'escape room'

class EscapeRoom(Room):
  def play(self):
    print('You take all 5 creates to teh sub, you know the clock is ticking and do not have time to check if any are damaged. Which storage compartment do you choose.')
    p = input('Pod? [1, 2, 3, 4]: ')
    if int(p) == random.randint(1, 2) or int(p) == random.randint(3,4):
      c()
      print('You put the crates in ' + p + '. You close the door and get on the sub you here a loud vacum sound. You press the Dryer button and Go home. You sell all the stuff in the crates for 400 million. You have suceeded and will live to scuba dive another day.')
      return 'win'
    else:
      c()
      print('You put the crate in ' + p +'. You are thinking happy thoughts, when you get home, you go to take the crates out. You then see the sign that says dont use broken. The crates fell thru the floor and are now lost in the middle of the ocean. Sooooooooooooooooooooo close, yet sooooooooooooooooooooooooooooooooooooo far.')
      return 'game over'

engine = {
  'game over': Game_Over(),
  'intro': Intro(),
  'corridor': Corridor(),
  'bomb hold': Bomb_Hold(),
  'bridge': Bridge(),
  'escape room': EscapeRoom(),
  'win': Win()
}

room = engine['intro'].play()
while True:
  room = engine[room]
  room = room.play()
