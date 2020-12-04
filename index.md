## Welcome to TagLok

Introducing TagLok! A project to make NFC based locking systems cheap and easy!

### How it Works

TagLok harnesses the power of Arduino and the PN532 NFC chip to provide a proof-of-concept locking system for car doors. It can be made to work in one of five ways

1. TagLok can directly power door lock actuators to lock/unlock doors
2. TagLok can emit an RF code that emulates an existing keyless entry fob to lock/unlock doors
3. TagLok can power an existing RF keyfob that can already lock/unlock doors
4. TagLok can be used to start/stop a car without the use of the key
5. TagLok can be used as a secondary, active anti-theft system by preventing ignition unless the tag is present.

More information will be made available as each TagLok module is completed.

### Security

The security for TagLok is primarily dependent on how it is used. On a physical level, TagLok should be equally as secure as anything else inside your car because all components are mounted inside the vehicle. On the software side, TagLok utilizes the NFC protocol. NFC (Near-Field Communication) is the same underlying technology used in Tap to Pay and Mobile Contactless payment systems. It requires close contact to clone, and is relatively compact. In the planning for TagLok we considered using NDEF technology to send a passphrase or even using a phone's NFC chip and a Raspberry Pi to create a dynamically changing passphrase passed through NDEF to combine the strengths of NFC and TOTP. Eventually we settled on the use of raw NFC and authentication of the tag's unique ID. This makes it significantly harder to spoof, and prevents accidental overwriting of the security code.

This does however simplify the code, and allows for all of the security codes to be written directly to the firmware of the TagLok.

### Future Plans

We are still in the process of fully implementing TagLok with several Arduino and PN532 shields. Our end goal however is to simplify both the Arduino and PN532 platforms into one board with the TagLok firmware hard coded as the bootloader on the device. This will free up the program side to make it suitable for more tags, and better authentication of these tags. This would also allow for dynamic changing and a possible second iteration of the device could free up the ability of dynamically changing passphrases in tandem with passively powered NFC tags.

### Where can I get it?

We are slowly working on publishing and documenting the TagLok software. We are making sure it is fully functional and bulletproof before releasing it because even as experimental software, it will be installed on personal vehicles. For anyone curious about testing the software and building the device themselves, they can contact us at taglok@protonmail.com.

### How much are the parts?

While we advise the use of bigger brand parts, the TagLok can be built using cheaper eBay Arduino clones. For the PN532 module/shield we used the ElecFreaks NFC Shield v1.6 in our initial prototype and continue to use it for testing due to its more limited feature set and weaknesses that make code written for it fully compatible with newer, more capable RFID shields. In total we estimate the project can be completed for less than $50, and likely even less than $20 if you play your cards right.

### Who are you?

The TagLok is the project of alteredgenome here on GitHub, a second year cybersecurity major with a focus in cryptographic systems and security analysis. The rest of the TagLok team is comprised of volunteer contributors ranging from cybersecurity veterans, electronic engineers, and other community contributors. As the project grows we will slowly take on more full time team members as the complexity increases.

### Will it stay open source?

In an effort to increase transparency and community security, the project will remain open source. Certain code that is implemented in future security layers such as the WIP MFS-Tag chipset may be closed source in order to increase the financial viability and real world effectiveness of it. Rest assured that this future chipset will be thorougly audited by several security vendors and will not be a necessary or integral part of the TagLok but would be both an addon for increased security, and a separate standalone product with the same goal but full integrated into the board.
