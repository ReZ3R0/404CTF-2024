En cours de Redac ...

![01](https://github.com/ReZ3R0/404CTF-2024/blob/main/Images/That_Escalated_Quickly/TEQ000.png?raw=true)

![02](https://github.com/ReZ3R0/404CTF-2024/blob/main/Images/That_Escalated_Quickly/TEQ001.png?raw=true)

Nous avons cette photo déchirée:

![03](https://github.com/ReZ3R0/404CTF-2024/blob/main/Images/That_Escalated_Quickly/PhotoD.png?raw=true)

On peut trouver la correspondance avec google rechercher par image:
https://alpinemag.fr/patrick-edlinger-legende-escalade/
![04](https://github.com/ReZ3R0/404CTF-2024/blob/main/Images/That_Escalated_Quickly/PhotoPasD.png?raw=true)

$\textcolor{orange}{\text{C'est Patrick Edlinger.}}$

Impressionnant ! :scream: :heart_eyes: 🤩

![Impr](https://github.com/ReZ3R0/404CTF-2024/blob/main/Images/That_Escalated_Quickly/Imp.png?raw=true)

Je suis perdu dans mes lectures. Je découvre le grimpeur... J'adore Hallucinant !

Bon revenons à notre mission

le flag prend forme: **404CTF{patrick-edlinger_ _ _ }**

## La seconde question Q2:
```
2. Mais oui c'était donc cette  personne !  
Lors de la plus zammechat de ses ascensions, 
elle était pas  loin d'un joli lieu touristique naturel... 
Mais lequel ?  Trouvez ce lieu.
```

Je ne connais pas ce terme "zammechat" 

On fait quelques recherches Google "Patrick Edlinger zammechat" :arrow_right: Rien

Google "zammechat" nous donne un lien vers:

https://en.wiktionary.org/wiki/Appendix:A_Clockwork_Orange

Qui parle de Anthony_Burgess:

https://en.wikipedia.org/wiki/Anthony_Burgess

Qui a notamment écrit:

![AB-OM](https://github.com/ReZ3R0/404CTF-2024/blob/main/Images/That_Escalated_Quickly/L-orange-mecanique.jpg?raw=true)

Ok ok dans l'article sur lui plus haut on dit que ``En 1989, il réalisait Orange Mécanique, 8a, au Cimaï, en solo intégral``.

Proche du Cimaï nous avons Le [mont Caume](https://fr.wikipedia.org/wiki/Mont_Caume) qui est le point culminant des Monts toulonnais, avec une altitude de 801 mètres.
je vais retenir ce lieu pour la Q2.

ce qui nous donne à présent dans le flag: **404CTF{patrick-edlinger_mont-caume_  _  }**

```
La troisième question Q3:

3. Ce lieu trouvé, vous vous souvenez  d'un autre lieu touristique homonyme ! 
Il est possible d'y accéder à  moins d'une heure de train depuis une certaine grande ville. 
Trouvez cette ville. 
```

Petites recherches sur Maps:
```
homonyme de Caume:
Caumme /rien
Caume --> La Caume n'est pas la bonne piste
Caum /rien
Comme /rien
Come --> Donne Côme en Italie
com /rien
ect...
```

Caume ne me donne rien, mais [Côme](https://www.google.fr/maps/place/22100+C%C3%B4me,+Italie/@45.8005881,9.0442288,13z/data=!3m1!4b1!4m6!3m5!1s0x47869c481027ed63:0xb99b96af785ff524!8m2!3d45.8063817!4d9.0851867!16zL20vMGdneXI?entry=ttu) en Italie est à 1h en train de Milan:

https://www.sncf-connect.com/train/horaires/milan/come

![Milan-Come](https://github.com/ReZ3R0/404CTF-2024/blob/main/Images/That_Escalated_Quickly/Milan-Come-Train.png?raw=true)

Je poursuit avec le Flag: **404CTF{patrick-edlinger_mont-caume_milan_  }**

```
La quatrième question Q4:

4. Fort de vos découvertes, vous vous sentez en plein élan sportif !
Vous voulez donc effectuer une longue marche entre cette ville et celle juste en dessous dans le classement des villes par taille de population.
Dans quel pays seriez-vous à mi-chemin de votre trajet ? Trouvez ce pays.
```
Ici nous avons la Liste des villes et agglomérations les plus peuplées:

https://fr.wikipedia.org/wiki/Liste_des_villes_et_agglom%C3%A9rations_les_plus_peupl%C3%A9es

![05](https://github.com/ReZ3R0/404CTF-2024/blob/main/Images/That_Escalated_Quickly/wiki.png?raw=true)

Il suffit d'utiliser Maps et Itinéraire. J'ai d'abord soumis avec la Slovénie et ensuite ajusté avec la Croatie. :sweat_smile:

https://www.google.fr/maps/dir/Sofia,+Bulgarie/Milan,+Italie/@44.2361379,10.9701667,6z/data=!3m1!4b1!4m14!4m13!1m5!1m1!1s0x40aa8682cb317bf5:0x400a01269bf5e60!2m2!1d23.3218675!2d42.6977082!1m5!1m1!1s0x4786c1493f1275e7:0x3cffcd13c6740e8d!2m2!1d9.1824027!2d45.468503!3e2?entry=ttu

![MS](https://github.com/ReZ3R0/404CTF-2024/blob/main/Images/That_Escalated_Quickly/Milan-Sofia.png?raw=true)

Flag: **404CTF{patrick-edlinger_mont-caume_milan_croatie}**

