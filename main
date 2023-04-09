import random

# Player class to keep track of player's attributes
class Player:
    def __init__(self, name):
        self.name = name
        self.max_health = 100
        self.health = 100
        self.attack = 10
        self.defense = 5
        self.gold = 0
        self.health_potion = 3
        self.xp = 0

# Function to simulate a battle with a monster
def battle(player):
    monster_health = random.randint(50, 100)
    monster_attack = random.randint(5, 10)
    print(f"A wild monster appears with {monster_health} health and {monster_attack} attack!")
    while True:
        print(f"Player: {player.name} | Health: {player.health} | Attack: {player.attack} | Defense: {player.defense} | Gold: {player.gold}")
        action = input("Enter your action (attack/run): ").lower()
        if action == "attack":
            damage_to_monster = max(player.attack, player.attack - monster_health)
            damage_to_player = max(monster_attack, monster_attack - player.defense)
            monster_health -= damage_to_monster
            player.health -= damage_to_player
            print(f"You attack the monster and deal {damage_to_monster} damage!")
            print(f"Monster Health: {monster_health}")
            if monster_health <= 0:
                print("You defeated the monster!")
                player.gold += 10
                player.xp += 5
                player.health_potion += 1
                break
            print(f"The monster attacks you and deals {damage_to_player} damage!")
            if player.health <= 0:
                print("You were defeated by the monster!")
                break
        elif action == "run":
            print("You successfully escaped from the battle!")
            break
        else:
            print("Invalid action. Please enter 'attack' or 'run'.")

# Function to start the game
def start_game():
    print("Welcome to the Word-Driven RPG Game!")
    player_name = input("Enter your name: ")
    player = Player(player_name)
    print(f"Hello, {player.name}! Your journey begins now.")
    while True:
        print("==========")
        print("Options:")
        print("1. Battle a monster")
        print("2. Check player status")
        print("3. Use Health Potion")
        print("4. Level Health: 10G")
        print("5. Level Attack: 10G")
        print("6. Quit")
        choice = input("Enter your choice (1/2/3/4): ")
        if choice == "1":
            battle(player)
        elif choice == "2":
            print(f"Player: {player.name} | Health: {player.health} | Health Potions: {player.health_potion} | Attack: {player.attack} | Defense: {player.defense} | Gold: {player.gold} | XP: {player.xp}")
        elif choice == "3":
            player.health_potion -= 1
            player.health = player.max_health
            if player.health_potion == 0:
                print("Out of health potions")
            else:
                print("You used 1 health potion")
                print(f"Player: {player.name} | Health: {player.health} | Health Potions: {player.health_potion}")
        elif choice == "4":
            if player.gold < 10:
                print("Invalid amount of gold")
            else:
                player.max_health += 5
                player.gold -= 10
        elif choice == "5":
            if player.gold < 10:
                print("Invalid amount of gold")
            else:
                player.attack += 2
                player.gold -= 10
        elif choice == "6":
            print("Thank you for playing!")
            break
        else:
            print("Invalid choice. Please enter 1, 2, 3, 4, or 5.")

# Start the game
start_game()
