# clone und push mit ssh im Ubuntu Terminal 
Die Eingabe `git push`erzeugt die Ausgabe `Username for 'https://github.com': chainlaboratory
Password for 'https://chainlaboratory@github.com':
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-https-urls for information on currently recommended modes of authentication.`

### Support for password authentication was removed on August 13, 2021.
Was jetzt? Wir brauchen einen ssh key.

`ssh-keygen -t ed25519 -C "your_email@example.com"`

...dann Enter  um das Standard File zu akzeptieren.
Die Aufforderung zur Passwortgenerierung ist fakultativ
und kann mit Enter übersprungen werden. Der Public Key
befindet sich im Verzeichnis `.ssh/id_ed25519.pub`

Den ssh Key Agent aktivieren

starten des ssh-agent im Hintergrund

`$ eval "$(ssh-agent -s)"`

Agent pid 59566

`$ ssh-add`

Enter passphrase for /home/YOU/.ssh/id_rsa: [tippy tap]

Identity added: /home/YOU/.ssh/id_rsa (/home/YOU/.ssh/id_rsa)


Den Key kopieren (copy/paste)

`$ cat ~/.ssh/id_ed25519.pub`

Der Key kann jetzt im Github Account eingefügt werden. Im Hauptmenu => Settings => SSH and GPG keys

Jetzt funktionieren

`git clone git@github.com:chainlaboratory/clone-push-ssh.git`

`git push`

