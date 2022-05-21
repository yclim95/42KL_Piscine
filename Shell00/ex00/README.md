# Ex00

```sh
mkdir ex00
cd ex00
vim z
enter "Z"
```

# Ex01

```sh
mkdir ex01/
touch testShell00
touch -t 202106012342 testShell00
echo "testing! Excersie 01 Go go go 42KL gogo" > testShell00
chmod 455 testShell00
tar -cf testShell00.tar testShell00
```

# Ex02

```sh
mkdir ex02
mkdir test0
touch test1
mkdir test2
touch test3
touch test4
ln test3 test5
ln -s test0 test6
chmod 715 test0
chmod 714 test1
chmod 504 test2
chmod 404 test3 
chmod 641 test4 
chmod 404 test5 
touch -t 202106012047 test0 
touch -t 202106012146 test1
touch -t 202106012245 test2 
touch -t 202106012344 test3 
touch -t 202106012343 test4
touch -t 202106012343 test5
chmod -h 777 test6
touch -mt 202106012220 test6
tar -cf exo2.tar *
```

# Ex03

```sh
mkdir ex03
cat ~/.ssh/id_rsa.pub >> id_rsa_pub
```

# Ex04

```sh
ls -t -p -m
```

# Ex05

```sh
git log  --pretty='%H' -5
```

# Ex06

```sh
git status --ignored -s | grep '!!' | cut -f 2 -d' '
```

# Ex07

```b
Episode V, A NEW H0PE It is a period of civil war
Rebel spaceships, striking from a hidden base, have won their first victory against the evil Galactic Empire. 
During the battle, Rebel spies managed to steal secret plans to the Empire's ultimate weapon, the STAR DEATH, an armored space station with enough power to destroy an entire planet.


Pursued by the Empire's sinister agents,
Princess Mehdi races home aboard her starship, custodian of the stolen plans that can save her people and restore the dictatorship to the galaxie..






```

# Ex08

```sh
#!/bin/sh
find . -type f \( -name '*~' -o -name '#*#' \) -print -delete
```

# Ex09

```sh
41	string 42	42 file
```
