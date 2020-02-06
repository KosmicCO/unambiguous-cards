# Design Notes for the Unambiguous Cards Framework

## Design Goals

Features that we would especially like to see in the system:

- Board as an (interesting) state machine
- Board updating necessarilly takes finite time without artificial cut-offs
- The underlying mathematical definitions are somewhat easy to comprehend
- The definitions are symantically incapable of violating the features of the game (such as having any syntax that would cause loops be impossible)
- Having new cards only need to be defined by the mathematical language to be implemented rather than by implementing card-specific code/fixes
- The mathematical notation is expressive enough to efficiently implement new features or definitions

Features that would be nice to see, but are not deal-breakers:

- A autowriter which takes a card and translates its mathematical definition to a summary english description
- Having the language be compatible with an autoprover, such as Coq or one of our own making
- Making a card/deck rating system, which rates a deck based on its power (for some definition of that)
- Making a feature which simulates the next step from a player's knowledge/perspective to see how a round would play out.
- Having the board also described by the underlying mathematical language rather than by being implemented

## Mathematical Design of the Language

### Current Ideas and Definitions

The notation should, at the least, make it easy to create notions of a board, cards, players, and actions.

We would want our notation to easily construct objects (perhaps similarly to Haskell) so that an object can have multiple types. The board is an object that, upon being given a request from the user to apply an action (such as applying a card or passing, etc) functions like a state machine. Turns will be taken as the state machine takes in certain actions as valid or not from each player. The tricky thing will be to have the board also definable also using a similar syntax to the cards. This also may be more difficult to do given the requirement that the game be somewhat efficient.

Given that the board is implemented in a sufficiently simplistic way, the cards would just have to describe mathematically/instructionally how they should mutate the board. The key would be to make sure that the language be sufficiently powerful as to allow cards to essentially create new entities (perhaps those such as mana or whatnot) such that the board is not necessarilly in charge of keeping track of them. This would also free the board from having to be the source of game information, making its design simpler.
