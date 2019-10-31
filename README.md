# PRO-Bot
This was my attempt at making a bot for the video game Pokemon Revolution Online. I learned a lot about reverse engineering and game networking through this project.

The hardest part was undoubtably the beginning.  Before I could do anything else, I had to find out how PRO encoded their packets.  To accomplish this I examined the login request packets, which I knew had to contain my username and password.  I soon saw that it was a very simple system- they simply XORed each character in a message with "00000001".  For example, 'b' would become 'c' and vice versa.  This was a bit alarming (my password was being sent to the game's login server with such trivial 'encryption', if it can even be called that), but I was happy to have cracked the code.  I then wrote a quick python script to grab all network traffic from PRO, decrypt them, and print them out for my viewing pleasure.  I systematically tested different actions in-game, such as moving in various directions, sending messages, and entering battles.  Based on these tests, I could derive what various numbers and values represented, and use this information to my advantage.  For example, I discovered that a particular integer represented a wild Pokemon's ID.  Using this, I could create a script that kept on encountering Pokemon (a time consuming process) until eventually it encountered a desirable, rare Pokemon with a pre-specified ID.



Disclaimer: This project serves as a learning oportunity for analyzing web traffic.  Botting in Pokemon Revolution Online violates their terms of service and may result in a ban.  Using this bot for anything other than learning purposes is not advised.
