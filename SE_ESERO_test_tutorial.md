# SE_ESERO_test_tutorial
## Multi-räknaren @unplugged
<div style="display: flex; justify-content: space-around;">
  <img src="https://github.com/ElinTeknikensHus/esero_test/blob/master/logotyp%20esero-sweden_svart.png?raw=true" alt="DampVibrations" width="300"/>
  <img src="https://github.com/ElinTeknikensHus/esero_test/blob/master/TH-logo-liggande-svart%403x.png?raw=true" alt="DampVibrations" width="300"/>
</div>

## Räknevariablen
Skapa en variabel, till att räkna antal skakningar/steg med. Kalla den `||variables:antalSkakningar||`. 

## Sätt räknevariablen
* Hitta blocket `||variables: ändra ... med 1||` och dra in den i  `||input.när skaka||`    

```blocks
input.onGesture(Gesture.Shake, function () {
    antalSkakningar += 1
})
```

## Nollställ multiräknaren
* Hitta blocket `||input:när knapp A trycks||` och dra in det till arbetsytan. 

```blocks
input.onButtonPressed(Button.A, function () {
})
```

## Nollställ multiräknaren
* Hitta blocket `||variables: sätt ... till ...||` och dra in den i `||input:när knapp A trycks||`

```blocks
input.onButtonPressed(Button.A, function () {
    antalSkakningar = 0
})
```

## Nollställ multiräknaren
* Hitta blocket `||basic.visa siffra||`. Dra in den i `||input:när knapp A trycks||` nedanför `||variables: sätt...||`

```blocks
input.onButtonPressed(Button.A, function () {
    antalSkakningar = 0
    basic.showNumber()
})
```

## Nollställ multiräknaren
* Sätt in variabeln `||variables:antalSkakningar||` i `||basic.visa siffra||`

```blocks
input.onButtonPressed(Button.A, function () {
    antalSkakningar = 0
    basic.showNumber(antalSkakningar)
})
```

## visa antal skakningar
* Dra in blocket  `||loops:every||`

```blocks
loops.everyInterval(500, function () {
    
})
```

## visa antal skakningar
* Ställ in `||loops:every||` till 1 sekund (1000 ms)

```blocks
loops.everyInterval(1000, function () {

})
```

## visa antal skakningar
* Sätt in  `||basic.visa siffra||` i `||loops:every||` 

```blocks
loops.everyInterval(1000, function () {
    basic.showNumber()
})
```

## visa antal skakningar
* Sätt in variabeln `||variables:antalSkakningar||` i `||basic.visa siffra||`
```blocks
loops.everyInterval(1000, function () {
    basic.showNumber(antalSkakningar)
})
```

## Koden är nu färdig att användas!
* Tryk på knappen "Klar" och prova sedan din multiräknare.


```template
input.onGesture(Gesture.Shake, function () {
})
```