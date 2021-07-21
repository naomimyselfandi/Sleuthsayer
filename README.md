# Sleuthsayer

_Hidden information roleplay bot_

> Check out our [wiki](https://github.com/naomimyselfandi/Sleuthsayer/wiki) or [Discord server](https://discord.gg/J9T2sMuyHZ)!

Sleuthsayer creates a personalized roleplaying game on your Discord server. Most Discord roleplays create a single channel for each location in the game. Sleuthsayer turns that on its head by creating a channel for every _player character,_ which only that character's player can see. Sleuthsayer keeps track of who can see whom, and copies messages around as needed. This means that players don't know anything their character doesn't know, without any effort from the game host. This is Sleuthsayer's "killer feature," and makes it particularly effective for games based around exploration, intrigue, and deception - hence the name.

## Basic gameplay

Sleuthsayer keeps track of the state of the game world. Under ordinary circumstances, the world only changes when a player or a game master runs a _command._ Commands look like English sentences: `take the lantern`, `read the flyer`, or `go north`, for example. For reasons we'll get to later, they may also be written in the past tense - `took the lantern` instead of `take the lantern`, perhaps. When Sleuthsayer gets a command, it processes it, narrates it, and updates the game world. If the command is invalid, it instead produces a diagnostic message so the player can try to correct it.

But a roleplaying game with only purely mechanical actions would hardly be a roleplaying game, would it? Sleuthscript assumes that anything written in a player's channel is _narration,_ and automatically copies it to anyone else who should be aware of it. In the spirit of intrigue, awareness isn't necessary two-way! If two characters are having a private conversation, and a third player is hiding in a cabinet, they'll overhear the conversation without anyone else knowing about it!

Commands must be enclosed in \`backticks\` (for convenience, the final backtick may be omitted if there's nothing after it). This allows commands to be embedded in narration if desired:

> With a dramatic sigh, Alice `opened the attic door`. "I guess we better see what's up there, right?"

If Alice's posted that message in their private channel, whoever she's talking to would also see it, and the bot would describe the door opening... after checking that it isn't locked, of course.

## For game hosts: Customizing Sleuthsayer

Sleuthsayer is configured in a scripting language called Sleuthscript. It's a relatively straightforward language, and it should be easy enough for even someone with no programming experience to take code samples and adapt them for their purposes. Sleuthscript has two major use cases: creating _actions,_ and creating _rules._

Actions are anything a player can do. When a player runs a command, Sleuthsayer looks at the actions it knows about and tries to find one that matches. (There are also special actions that help a game master manage the game state; these work the same way.) Adding a few custom actions is a great way to make your game world unique, and they open up a lot of options for puzzles, if you're into that.

Rules govern how the game world works. A rule can be anything from an alarm that triggers when a vault is opened, to an elevator your players can call, to a complex inventory management system that simulates the difficulties of carrying big, heavy items. (In fact, most of Sleuthsayer's mechanics are implemented as Sleuthscript rules!) In general, if an object needs unique behavior, or you're looking to create a new game mechanic, custom rules are the way to do it.

Technically, the world map is also set up in Sleuthscript, but you don't need to think about it that way if you want it to - the code for rooms and items _without_ special behavior is extremely simple. in a game with X-ray vision goggles, for a totally random example.

## When can I use it?

Sleuthsayer is currently in _active development_. Work on core gameplay features should be wrapped in up in the coming months. If you want to get involved, either as a developer or just part of the community, join the discussion on our [Discord server](https://discord.gg/J9T2sMuyHZ)! We're looking for not only people with technical skills, but also game masters and players who're interested in this project. You're the ones who'll actually use this thing, and we'd love your feedback!
