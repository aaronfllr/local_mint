# Hacker's Kotlin Local on Mint

> This serves as an exposé and example of the typical [competent local](https://github.com/readme/guides/developer-onboarding "Optimize local dev environments for better onboarding") setup for [the modern 12-factor-app](https://12factor.net/ "The Twelve-Factor App") development workflow within [**fluent-development-style**](https://martinfowler.com/articles/agileFluency.html "Fluent Development Style") of [Extreme Programming (XP).](https://en.wikipedia.org/wiki/Extreme_programming "Extreme Programming") _This is how the world's most competent and performant software engineers, ["hackers," work](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3682183/ "The relationship between intelligence and creativity: New support for the threshold hypothesis by means of empirical breakpoint detection; Meaning, competent intelligent people seeking elegance are required to create anything worthwhile creating. AKA, 'deadbeat Cog theory'") to disrupt markets, generate value and profit, and make the world a better place._ - and so can you!

## Basic Principles

1. _There's only production, and your local is part of it, **treat it as such**:_ [Factor X](https://12factor.net/dev-prod-parity "Factor X of The Twelve-Factor App")
2. _Only absolutely common packages and configurations are global configurations._
3. **_The world is multifaceted, and so Linux is multiuser._**

## The Global Setup Journey 

> _Everything begins with the local..._

1. Install your OS: [Linux Mint](https://linuxmint.com/download.php "Linux Mint"), Mate in our case - [beginner's guide](https://itsfoss.com/install-linux-mint/).
2. **Concept:** _Your first user is **reserved** for you and is the only user with `sudo` access. If you have multiple customers or entities to code for separate them by creating additional accounts, leaving the first one untarnished. If you have separate boxes for separate gigs like we do the one user may suffice for you, yet a separate single user for coding is best recommended._
3. Upgrade base packages: [step 01 - the base](step-01-base.md)
4. Configure your shell: [step 02 - the 'oh your shell'](step-02-shell.md)
5. Useful Global Apps!: [step 03 - global apps](step-03-global-apps.md)

**_From this point, each local user development tools are configured "as a user," including if only one user opted to be used._**

## Dev User Setup

ToDo: