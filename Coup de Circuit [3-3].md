![01](https://github.com/ReZ3R0/404CTF-2024/blob/main/Images/Cc03.png?raw=true)

Sur le Panneau de contrôle on voit : **BatteC2**

![Panel](https://github.com/ReZ3R0/404CTF-2024/blob/main/Images/Panel.png?raw=true)

Rapidement j'ai eu l'idée d'aller sur Github voir si nous avions quelque chose ; Bingo, **Brigitte Heubbe** alias **BribriTireuse** semble être à l'origine de ce command and control framework :joy:

https://github.com/BribriTireuse/BatteC2

À ce moment du challenge, je ne suis pas trop fier de moi car je me suis fait avoir comme un bleu :sweat_smile:

Dans https://github.com/BribriTireuse/BatteC2/blob/main/c2.py on peut voir un commentaire: 

```python3
self.files_counter += 1  # Smyler's note: race condition goes brrrrr
```
What ! Une race condition à exploiter ?  Mais où ? :scream: J'ai cherché et je n'ai jamais trouvé... Mouais $\textcolor{orange}{\text{reZ3R0}}$ Comme souvent tu pars trop loin ! :innocent:

Oh Pu... j'avais pourtant bien vu dans https://github.com/BribriTireuse/BatteC2/blob/main/app.py 

```python3
download_dir = Path("227eb601e5bf8ea0c5da13a26be3eba2e5fea2cd7d75dcd2951cf615dd790da5")
```

et plus loin:

```python3
def download_file(uuid):
    uuid = UUID(uuid)
    agent = c2.agents.get(uuid)
    if agent is None:
        return "Not found", 404
    path = request.args["file"]
    local = Path(path)
    agent.download_file(path, Path("static") / download_dir / local.name)
    return redirect(f"/static/{download_dir}/{local.name}")
```

Avec l'énoncé du challenge, nous savons que le fichier est nommé: Secret-Mojo.pdf

Allez plus qu'à ce rendre sur: https://panel-5d4213f3bf078fb1656a3db8348282f482601690.takemeouttotheballgame.space/static/227eb601e5bf8ea0c5da13a26be3eba2e5fea2cd7d75dcd2951cf615dd790da5/Secret-Mojo.pdf

![Flag-Mojo](https://github.com/ReZ3R0/404CTF-2024/blob/main/Images/FlagMojo.png?raw=true)

404CTF{M4i5_p0urt@n7_mOn_s3rvEur_d3_C_&_c_3t4i7_s1_53cUrisE}


Je me suis vraiment mais vraiment régalé sur cette série. Merci à Smyler !



