# Design Notes for the Unambiguous Cards Framework

## Design Goals

Features that we would especially like to see in the system:

- Board as an (interesting) state machine
- Board updating necessarilly takes finite time without artificial cut-offs
- The underlying mathematical definitions are somewhat easy to comprehend
- The definitions are symantically incapable of violating the features of the game (such as having any syntax that would cause loops be impossible)
- Having the board also described by the underlying mathematical language rather than by being implemented
- Having new cards only need to be defined by the mathematical language to be implemented rather than by implementing card-specific code/fixes
- The mathematical notation is expressive enough to efficiently implement new features or definitions

Features that would be nice to see, but are not deal-breakers:

- A autowriter which takes a card and translates its mathematical definition to a summary english description
- Having the language be compatible with an autoprover, such as Coq or one of our own making
- Making a card/deck rating system, which rates a deck based on its power (for some definition of that)
- Making a feature which simulates the next step from a player's knowledge/perspective to see how a round would play out.

## The Mathematical Notation
