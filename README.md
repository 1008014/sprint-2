# sprint-2
let schok = 0
let melding = 0
input.buttonsAB.onEvent(ButtonEvent.Click, function () {
    schok = 0
    melding = 0
    light.setAll(0x000000)
    console.log("Het is gereset")
})
input.onGesture(Gesture.Shake, function () {
    schok += 1
    console.log("Dit karretje schud")
    light.showAnimation(light.sparkleAnimation, 100)
})
forever(function () {
    if (schok > 25) {
        schok = 0
        light.setAll(0xff0000)
    }
    if (schok >= 25 && melding == 0) {
        console.log("Dit karretje is kapot")
        melding += 1
    }
})
