# demorepo
tryna stuff-pt0 git repo
import random

def play_meme_forge():
    """
    Simple MemeForge mini-game: Dodge Skibidi Toilets to collect meme shards.
    Player chooses left/right/up/down to dodge obstacles and collect shards.
    Goal: Collect 5 shards to forge a meme weapon.
    """
    shards = 0
    max_shards = 5
    obstacles = [
        "Skibidi Toilet left!",
        "Skibidi Toilet right!", 
        "Skibidi Toilet above!",
        "Skibidi Toilet below!"
    ]
    
    print("🏃‍♂️ Welcome to MemeForge Mini-Game!")
    print("Dodge Skibidi Toilets to collect 5 meme shards!")
    print("Commands: left, right, up, down\n")
    
    while shards < max_shards:
        # Generate random obstacle
        obstacle = random.choice(obstacles)
        print(f"🚽 {obstacle} INCOMING!")
        
        # Player input
        move = input("Dodge (left/right/up/down): ").strip().lower()
        
        # Simple dodge logic - 70% success chance per correct directional match
        directions = ["left", "right", "up", "down"]
        if move in directions:
            obstacle_dir = obstacle.split()[-1]  # Extract direction from obstacle
            if move == obstacle_dir:
                if random.random() < 0.7:  # 70% dodge success
                    shards += 1
                    print("✅ Perfect dodge! +1 Meme Shard! (Shards:", shards, "/", max_shards, ")")
                else:
                    print("❌ Close call! Skibidi grazed you - no shard this time.")
            else:
                print("❌ Wrong direction! Skibidi hits you - try again!")
        else:
            print("❌ Invalid move! Skibidi Toilet hits you!")
    
    print("\n🎉 MEME SHARDS COLLECTED! You've forged the 'Distracted Boyfriend Trap'!")
    print("Ready for PvP battle in MemeForge arenas! 💥")

if __name__ == "__main__":
    play_meme_forge()
