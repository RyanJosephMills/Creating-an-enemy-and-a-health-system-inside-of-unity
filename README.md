# Creating-an-enemy-and-a-health-system-inside-of-unity

The first thing you will need to do to create an enemy character is go to the hierarchy section right, click get an empty game object and call it an enemy player. 

![image](https://github.com/RyanJosephMills/Creating-an-enemy-and-a-health-system-inside-of-unity/assets/146854317/714cc496-40a7-4a75-b28e-60e99df70c78)


Once you have done that, you can then drag and drop your enemy sprite onto the empty game object to make it a child of the empty game object. Then you will want to click on the sprite and create a component inside the hierarchy, and that component will need to be a capsule collider; once you have that, you will need to resize it to make it fit your character perfectly once you have done all of that you will now be ok to start creating a script.

![image](https://github.com/RyanJosephMills/Creating-an-enemy-and-a-health-system-inside-of-unity/assets/146854317/6c2309a1-8ac9-4736-a8db-79eafc8a86e8)


Once you have created your script, you will need to call it player health; this way, you will clearly understand where your player health is.

![image](https://github.com/RyanJosephMills/Creating-an-enemy-and-a-health-system-inside-of-unity/assets/146854317/81e954bb-f90c-4bed-ba1b-108c511f80dc)


Once inside the script, you will need first to create some variable that will keep track of your health, so the first one you will need to make is a public int maxHealth and equal that to 10. When you boot up the game, this will be your starting health; the following variable you will need to create is public int health, allowing you to see your health in the inspector later. Then you will need to go to the start, and inside there, you will need to put health = maxHealth; that way, when the game starts, you will always begin on max health.

![image](https://github.com/RyanJosephMills/Creating-an-enemy-and-a-health-system-inside-of-unity/assets/146854317/6662a923-8ca9-4a92-a30d-a4b92932f5d0)


The next thing you will need to do is go to the bottom of the code and create a new function called public void TakeDamage () {} and what this will do is this function will be called by the enemy when the player makes contact so that the player will be able to take damage, so you will now need to go inside of the brackets and create a variable which will be a integer and call it damage then inside of the curly brackets type health -= damage; so with this code we can now take damage however it won’t kill the player if we get beyond zero, so to do this you will need to create an if statement health <= 0 now before we put anything inside the curly brackets we will need to go back up to the top and create a new variable which is a public int and call it Respawn; now you can go back to the curly brackets put SceneManager.loadscene(Respawn) once you have done that you can then go back to unity and click on your player and drag the new script onto it, one thing you will need to do before you continue is inside the inspector you will find the public variable that we just created now what you will need to do is set the number to the current scene that you would like the player to restart in because if you don’t put it to the correct number it won’t work.

![image](https://github.com/RyanJosephMills/Creating-an-enemy-and-a-health-system-inside-of-unity/assets/146854317/9ecf83fa-0db5-410a-92b2-283acb706173)

![image](https://github.com/RyanJosephMills/Creating-an-enemy-and-a-health-system-inside-of-unity/assets/146854317/98495de3-9312-48ad-a71a-57a029ad6038)


Now, the next thing we need to do is make the enemy deal the damage to the player, so to do this, you will need to create a new script once again, call it enemy damage and open it up once you are inside, we will need to create a new variable called public int damage, the reason that we don’t set the value inside of the code is that when we place the enemy in the game each enemy will be able to deal different amounts of damage.

![image](https://github.com/RyanJosephMills/Creating-an-enemy-and-a-health-system-inside-of-unity/assets/146854317/2cb41143-2203-49c9-b0e9-e5adead17a1d)


Now that you have done that, we need to make it so that this script can talk to the other one we just made. To do this, we create a public PlayerHealth (which is the name of the script) playerHealth. Next, you can delete the start and the update sections as we won’t need them, so instead, we need to create a private void OnCollisionEnter2D(Collision2D collision). So now we need to make sure that when something collides with this enemy, it is the player, so we will need to create an if statement and inside the brackets put collision.gameObject.tag == “Player” then inside the curly brackets, put playerHealth.TakeDamage, which is the bit of code we made inside the other script, then make some brackets and put the word damage inside.

![image](https://github.com/RyanJosephMills/Creating-an-enemy-and-a-health-system-inside-of-unity/assets/146854317/613f1229-3086-47f9-b13a-9a17a59f9bc1)


The next thing you must do is return to unity and put the enemy damage script onto the actual enemy. Then, you must pick a value of the damage you want this enemy to do to the player. Then, you will need to drag the player from the hierarchy section and drag it into the player health in the inspector to get a reference to where the player health code is.

![image](https://github.com/RyanJosephMills/Creating-an-enemy-and-a-health-system-inside-of-unity/assets/146854317/adb3dc9c-112a-491d-bbcd-03e105311168)


https://github.com/RyanJosephMills/Creating-an-enemy-and-a-health-system-inside-of-unity/assets/146854317/b5d8d316-a7a4-4e4c-9f50-59b183150dea
