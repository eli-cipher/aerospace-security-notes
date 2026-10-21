# Why Satellite Cybersecurity

Earlier, when humanity looked at the stars, we questioned what was above the ground, what was in the night sky, what lay beyond Earth. Now, in today's era, we are moving to build a Moon base, trying to make Mars habitable for humanity, searching for life on other planets. For the new generation, it seems like the work of a few blinks of an eye. But in those blinking seconds, we forget one of the most important things: security. We are racing to build a life beyond Earth, but we forget that we have to defend it too — because this is the infrastructure the whole of humanity already depends on.

## The infrastructure nobody notices

That's the part easy to miss: satellites aren't just "space stuff" happening somewhere far away from ordinary life. They're already the quiet backbone underneath things people use every single day without ever thinking about where the signal comes from — internet and phone connectivity, GPS navigation, emergency communications, TV and radio broadcast, defense systems, weather and environmental monitoring. None of this is in orbit as a future promise. It's already up there, already load-bearing, right now.

Which means when a satellite system breaks — not from age or weather, but because someone deliberately broke it — the damage isn't abstract. It isn't a line in a tech report. It's real people, on the ground, suddenly without the service they didn't know they were relying on.

## Why satellites specifically are a weak point

It's tempting to assume a billion-dollar piece of hardware orbiting the planet must be close to unbeatable. The physics says otherwise.

A satellite's signal has to travel an enormous distance before it reaches anything on the ground — a GPS satellite's signal, for instance, covers roughly 20,000 kilometers before it hits your phone's antenna. The further a radio signal travels, the weaker it gets, and it weakens fast: the energy drops off with the *square* of the distance. By the time that signal reaches Earth, it's faint enough that something as ordinary as a cheap software-defined radio, sitting much closer to the ground, can simply shout over it. Jamming or spoofing a satellite signal isn't some exotic, elite capability reserved for nation-states — it's often a matter of proximity and a few hundred dollars of hardware.

Add to that the practical realities of how these systems are actually built and run: many satellites already in orbit were designed years before today's threats existed, and there's no walking up to one to patch it. Modern satellites increasingly rely on commercial, off-the-shelf components to cut cost and speed up launches — which also means they inherit whatever weaknesses those commercial parts already have. And a satellite doesn't respect borders: in a single day it passes over dozens of countries, and from geostationary orbit it can see a third of the Earth's surface at once. A law passed in one country against "hacking satellites" means very little when the signal itself is reachable from just across a border.

## When this stopped being theoretical

None of this is a hypothetical. It has a history.

In 1986, a satellite-radio enthusiast going by "Captain Midnight" hijacked HBO's live satellite broadcast, interrupting it with his own message to protest a pricing change — not a government, not an organization, just one person with the right equipment. In 2009, a group of Brazilian truckers — not hackers by trade, just ham radio hobbyists — hijacked a U.S. military satellite's transponder and used it as a long-range radio for themselves. In 2018, Norway and Finland accused Russia of jamming GPS signals during NATO exercises, not in wartime, but as peacetime harassment — a reminder that states interfere with each other's space assets even when nothing is officially at war.

Then came February 2022. Hours before Russia's invasion of Ukraine began, attackers compromised the update servers of Viasat's KA-SAT satellite network and pushed out a wiper malware known as AcidRain. It didn't steal anything — it destroyed data on tens of thousands of modems, first across Ukraine, then spreading to fixed broadband customers across Europe. Viasat had to ship around 30,000 replacement modems. And in a detail that says everything about how unpredictable this kind of damage is: roughly 5,000 wind turbines in Germany lost their remote monitoring access as pure collateral damage — a cyberattack aimed at a war thousands of kilometers away, reaching into infrastructure that had nothing to do with it at all.

## What this should leave you with

None of these incidents happened because the attackers were unstoppable geniuses. They happened because, again and again, security was treated as something to worry about later — after the launch, after the growth, after the next milestone. The pattern echoes the opening of this note: we keep reaching further outward, toward the Moon, toward Mars, while leaving doors unlocked on the infrastructure we've already built.

That's the point this whole repository exists to work against. Understanding exactly how these systems get broken — not vaguely, but in real technical detail — is what makes it possible to build the next generation of space infrastructure so it doesn't repeat the same mistakes. Security isn't a feature bolted onto space systems after the fact. It has to be foundational to whether any of this — the Moon bases, the Mars missions, the satellites quietly running daily life down here — actually survives long enough to matter.

That's where the rest of this repo picks up: starting from the fundamentals of what a satellite actually is, then working toward exactly where and how these systems can be broken.
