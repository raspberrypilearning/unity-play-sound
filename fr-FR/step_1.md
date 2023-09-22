Les sons sont utilisés pour améliorer l'expérience du joueur. Pour ajouter un son, crée une variable publique pour stocker le son que tu veux jouer :

--- code ---
---
language: cs
---

public AudioClip collectSound;

--- /code ---

Ajoute une ligne de code à l'endroit où tu veux que le son soit joué :

--- code ---
---
language: cs
---

AudioSource.PlayClipAtPoint(collectSound, transform.position);

--- /code ---

Par exemple, ce code joue un son de collecte lorsque le GameObject est collecté par le joueur :

--- code ---
---
language: cs
---

public AudioClip collectSound;

void OnTriggerEnter(Collider other)
{
    // Check the tag of the colliding object
    if (other.gameObject.tag == "Player")
    {
        AudioSource.PlayClipAtPoint(collectSound, transform.position);
        Destroy(gameObject);
    }
}

--- /code ---

Dans l'éditeur Unity, trouve la propriété du son pour ton composant de script et clique sur le cercle pour attribuer le son que tu veux jouer :

![La fenêtre Inspector avec le son « Collect » dans la variable Collect Sound et le cercle à droite en surbrillance.](images/collect-sound-property.png)
