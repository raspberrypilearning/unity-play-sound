Sounds are used to enhance player experience. To add a sound, create a public variable to store the sound you want to play:

```
public AudioClip collectSound;
```

Add a line of code at the point you want the sound to play:

```
AudioSource.PlayClipAtPoint(collectSound, transform.position);
```
For example, this code plays a collect sound when the GameObject is collected by the Player:

```
public AudioClip collectSound;

void OnTriggerEnter(Collider other)
{
    // Check the tag of the colliding object
    if (other.gameObject.tag == "Player")
    {
        AudioSource.PlayClipAtPoint(collectSound, transform.position);
        Destroy(gameObject);
    }
```

In the Unity editor, find the sound property for your script component and click on the circle to assign the sound you want to play:

![The Inspector window with sound 'Collect' in the Collect Sound variable and the circle to the right highlighted.](images/collect-sound-property.png)
