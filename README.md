# Sensorer - lyd, lys og bevegelse

## Step 1@showdialog
Å programmere micro:biten til å reagere på høye lyder og risting er lett med de vanlige blokkene vi finner i Input-menyen:
 ```blocks
 input.onGesture(Gesture.Shake, function () {
	
})
input.onSound(DetectedSound.Loud, function () {
	
})

```
Dessverre gir ikke disse blokkene oss mulighet til å være særlig presise, og det finnes ikke slike blokker til de andre sensorene (som lys og temperatur)


## Step 2@showdialog
Hvordan er lyden i klasserommet? La oss gjøre et eksperiment og måle med micro:biten. 

 ```blocks
basic.forever(function () {
    led.plotBarGraph(
    input.soundLevel(),
    255
    )
})

```
Last ned programmet og undersøk micro:biten. Hva skjer?

## Step 2
Bygg dette lille programmet og last ned til micro:biten. Hva skjer?

(Trykk på lyspæren for å se fasiten.)

 ```blocks
basic.forever(function () {
    led.plotBarGraph(
    input.soundLevel(),
    255
    )
})

```

## Step bro@showdialog
Alle verdiene micro:biten måler med sensorene, er tall-verdier. Dette gir oss muligheten til å bruke de på mange måter:

```blocks
input.onButtonPressed(Button.A, function () {
    basic.showNumber(input.soundLevel())
    basic.showNumber(input.lightLevel() + input.temperature())
    basic.showNumber(Math.sqrt(input.acceleration(Dimension.X)))
})
```

## Step ping 
Endre programmet slik at micro:biten piper når det er **mørkt.** (Lysnivå mindre enn 100)

(Trykk på lyspæren for å se fasiten.)

```blocks
basic.forever(function () {
    if (input.lightLevel() < 100) {
        music.playSoundEffect(music.createSoundEffect(WaveShape.Sawtooth, 3749, 4641, 255, 0, 500, SoundExpressionEffect.None, InterpolationCurve.Linear), SoundExpressionPlayMode.UntilDone)
    }
})
```
```template
basic.forever(function () {
    if (input.lightLevel() < 100) {
        music.playSoundEffect(music.createSoundEffect(WaveShape.Sawtooth, 3749, 4641, 255, 0, 500, SoundExpressionEffect.None, InterpolationCurve.Linear), SoundExpressionPlayMode.UntilDone)
    }
})
```



## Step 2i3

Godt jobbet! Nå har dere kanskje begynt å få noen ideer om hvordan smarthuset kan automatiseres.

Trykk "Slutt/Finish" for å avslutte veiledningen.


```template
basic.forever(function ()){}
```

```ghost
basic.showNumber(input.lightLevel())
    basic.showNumber(input.acceleration(Dimension.X))
```