# Mbot With Arduino Cheat Sheet

### Utiliser le bouton

Bouton enfoncé : 
    
```
while(!(analogRead(A7)>10?0:1)){
    
}
```
 
### Utiliser les LED
 
Pour utiliser les LED intégrés au Mbot, on crée un objet ( ici `led` ) avec la fonction MeRGBLed

```
MeRGBLed led(7, 7==7?2:4);
```

Puis on peut utiliser la méthode `setColor`, cette méthode prends quatre arguments

```
led.setColor(led,R,G,B);
```

L'argument led correspond à la led que l'on veut sélectionner selon le tableau suivant

|argument|led|
|--|--|
|0|toutes|
|1|droite|
|2|gauche|

### Utiliser le capteur de distance (ultrason)

Pour utiliser un capteur de distance, on crée un objet ( ici `dist_sensor` ) avec la fonction MeUltrasonicSensor

```
MeUltrasonicSensor dist_sensor(4);
```

Puis on peut utiliser la méthode `distanceCm` pour retourner la distance en cm mesurée par le robot

```    
while(!(ultrasonic_4.distanceCm() < 5)){

}
```

### Utiliser le buzzer

Pour utiliser un buzzer, on crée un objet ( ici `buzzer` ) avec la fonction MeBuzzer

```
MeBuzzer buzzer;
```

Puis, on peut utiliser la méthode `tone` pour faire jouer une note précise, cette méthode prend deux arguments

```
buzzer.tone(tone, duration)
```

L'argument tone correspond à la note a jouer, l'agument duration correspond a la durée (en milliseconde) que la note doit etre jouée

```
buzzer.tone(900, 500);
```

### Utiliser le 7 segments

Pour utiliser un 7 segments, un crée un objet ( ici `seg7` ) avec la fonction Me7SegmentDisplay

```
Me7SegmentDisplay seg7(1);
```

Puis, on peut utiliser la méthode `display` pour afficher un ou des chiffre(s), cette méthode prend un argument

```
seg7.display((float)toPrint);
```

L'agument toPrint correspond au(x) chiffre(s) a afficher sur le 7 segment

```
seg7_1.display((float)1234);
```

### Utiliser le gyroscope

Pour utiliser un gyroscope, un crée un objet ( ici `gyro` ) avec la fonction MeGyro

```
MeGyro gyro;
```

Puis, on peut utiliser la méthode `begin` pour intialiser le gyroscope, on utilise ensuite la méthode `getAngle`

```
gyro.begin();
while(!((gyro.getAngle(2)) > (100))) {
    move(4,100);
}
```
