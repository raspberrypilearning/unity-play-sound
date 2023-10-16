Les sons sont utilisés pour améliorer l'expérience du joueur. Pour ajouter un son, crée une variable publique pour stocker le son que tu veux jouer :

--- code ---
---
language: cs
---

public AudioClip sonCollecte;

--- /code ---

Ajoute une ligne de code à l'endroit où tu veux que le son soit joué :

--- code ---
---
language: cs
---

AudioSource.PlayClipAtPoint(sonCollecte, transform.position);

--- /code ---

Par exemple, ce code joue un son de collecte lorsque le GameObject est collecté par le joueur :

--- code ---
---
language: cs
---

public AudioClip sonCollecte;

void OnTriggerEnter(Collider other)
{
    // Vérifier le tag de l'objet de collision
    if (other.gameObject.tag == "Joueur")
    {
        AudioSource.PlayClipAtPoint(sonCollecte, transform.position);
        Destroy(gameObject);
    }
}

--- /code ---

Dans l'éditeur Unity, trouve la propriété du son pour ton composant de script et clique sur le cercle pour attribuer le son que tu veux jouer :

![La fenêtre Inspector avec le son « Collect » dans la variable Collect Sound et le cercle à droite en surbrillance.](images/collect-sound-property.png)
