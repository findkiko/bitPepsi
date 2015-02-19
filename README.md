# bitPepsi

bitcoinify a pepsi vending machine

This application is designed to watch specific bitcoin wallet(s) for specific deposit amounts. When detected, the application will fire a specific GPIO on the Raspberry Pi which is then used to activate the vending mechanism in whatever vending machine you have it connected to. 

#/config/bitpepsi.json
This is the main configuration file, where you can specify wallets and other properties for the application.

Wallets
This array contains all the wallet data that the app monitors. This array is iterated over automatically; any wallet added in the correct format will be included.
pubkey: this is the public key that represents the wallet to be monitored
itemcost: What amount should the application looking for? This is measured in CAD.
gpio: represents the gpio pin number to be fired. I recommend you refer to the pi-gpio mapping found here: https://www.npmjs.com/package/pi-gpio
pricetolerance: Used in conjunction with itemcost, applies a tolerance to the monitored price to account for realtime fluctuations in value. Measured in dollars, so a value of 0.03 would mean that an amount detected that was less than three cents below the itemcost would still be a valid transaction.

