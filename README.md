# GAME_PROGRAM-EX--7
## To create an AI character in Unreal Engine that roams randomly within a NavMesh area and chases
the player when they come within a certain range, using Behavior Trees, Blackboard, and AI Perception.

## STEPS
1.Setup Navigation Add a NavMeshBoundsVolume to your level and scale it to cover the roamable area. Press P to confirm the green nav area is visible (indicating navigable space).
<BR>
2.Create AI Character Create a Blueprint character (e.g., BP_AIEnemy ) with a skeletal mesh and AIController class. Create an AI Controller Blueprint (e.g., BP_AIController ) and assign it to the character.
<BR>
3.Enable AI Perception In BP_AIController , add an AIPerception component. Configure a Sight sense (set detection range, lose sight range, peripheral vision angle). Bind OnPerceptionUpdated to update a blackboard value (e.g., CanSeePlayer and PlayerActor ).
<BR>
4.Set Up Blackboard Create a Blackboard with the following keys: TargetLocation (Vector) PlayerActor (Object) CanSeePlayer (Bool)
<BR>
5.Create Behavior Tree (BT_AI) Structure it like this: AI Random Roam with Chase - Unreal Engine 🎯 Aim
## Procedure
Root Selector
Sequence (Chase Player)

Blackboard Check: CanSeePlayer == truTask: Find Random Location → TargetLocation Move To: TargetLocation

6.Custom Task: Find Random Location Create a new BTTask_BlueprintBase to get a random reachable point using: Set the result to the TargetLocation blackboard key.

7.Test the AI Add a player character to the level. Place the AI enemy in the map and assign its controller and behavior tree. Press Play: the AI should roam when the player is far and chase the player when within sight. UNavigationSystemV1::GetRandomReachablePointInRadius()

## Output:
<img width="504" height="246" alt="image" src="https://github.com/user-attachments/assets/51eb1315-79b6-4a19-bb6d-40db7ef342e2" />
<img width="467" height="208" alt="image" src="https://github.com/user-attachments/assets/4b43219f-8d9e-49ae-80d1-3eed3a5d720f" />
<img width="493" height="196" alt="image" src="https://github.com/user-attachments/assets/64edae2a-b665-43d5-aa8c-f11377ed89c3" />

The AI character roams randomly within a defined area. When the player enters its sight range, the AI stops roaming and begins to chase the player until the player is out of sight, after which it resumes roaming.

## Result
The AI character roams randomly within a defined area. When the player enters its sight range, the AI stops roaming and begins to chase the player until the player is out of sight, after which it resumes roaming.


