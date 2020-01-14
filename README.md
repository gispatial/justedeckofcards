# justedeckofcards
 test assessment for justED, a simple implementation of a deck of playing cards with nodejs.

## API

### Card

Cards are a combination of a rank (`2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`,
`T` (Ten), `J` (Jack), `Q` (Queen), `K` (King), `A` (Ace)) and a suit
(`S` (Spades), `C` (Clubs), `H` (Hearts), `D` (Diamonds)).

#### constructor(rank, suit)

Accepts a rank (e.g. `4`) and a suit (e.g. `C`). Will throw on invalid input.

#### constructor(rankAndSuit)

Accepts a rank and a suit string (e.g. `4C`). Will throw on invalid input.

#### constructor(Card)

Copy constructor. Accepts a Card. Will throw on invalid input.

#### static parse(s)

Parses a card string (e.g. `4C`) and returns a new `Card`.

#### static stringify(c)

Returns a string representation of the card (e.g. `KH`).

#### toString()

Returns a string representation of the card (e.g. `KH`).

#### valueOf()

Returns a string representation of the card (e.g. `KH`).

#### inspect()

Returns a string representation of the card (e.g. `KH`).

#### ranks[]

An array of valid ranks.

#### suits[]

An array of valid suits.

### Deck

A Deck is just a set of 52 unique cards made by combining all legal suits and
ranks.

#### constructor()

Initializes a new shuffled deck of cards.

#### shuffle()

Randomizes the order of the cards.

#### draw()

Returns the next card from the deck.

#### reset()

Puts the dealt cards back in the deck and performs a shuffle.

#### toString()

Returns a string representation of the deck.

## Testing

    npm test
    
## Examples

### What is the probability that when two cards are drawn from a deck of cards without replacement that both of themwill be 8’s?

Cards are a combination of a rank (`2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`,
`T` (Ten), `J` (Jack), `Q` (Queen), `K` (King), `A` (Ace)) and a suit
(`S` (Spades), `C` (Clubs), `H` (Hearts), `D` (Diamonds)).

#### 𝑃(𝐵𝑜𝑡ℎ𝑎𝑟𝑒8′𝑠)=𝑃(𝐹𝑖𝑟𝑠𝑡𝑐𝑎𝑟𝑑𝑖𝑠𝑎𝑛8)∙𝑃(𝑆𝑒𝑐𝑜𝑛𝑑𝑐𝑎𝑟𝑑𝑖𝑠𝑎𝑛8)
Accepts a rank (e.g. `4`) and a suit (e.g. `C`). Will throw on invalid input.

#### 𝑃(𝐹𝑖𝑟𝑠𝑡𝑐𝑎𝑟𝑑𝑖𝑠𝑎𝑛8)=452

There are three 8’s left in the deck if one is pulled and not replaced, and 51 total cards remaining.

---

𝑃(𝑆𝑒𝑐𝑜𝑛𝑑𝑐𝑎𝑟𝑑𝑖𝑠𝑎𝑛8)=351

---

𝑃(𝐵𝑜𝑡ℎ𝑎𝑟𝑒8′𝑠)=452∙351=122652=1221=.0045𝑜𝑟.45%

#### What is the probability that both cards drawn (without replacement) will be spades?

𝑃(𝐵𝑜𝑡ℎ𝑎𝑟𝑒𝑠𝑝𝑎𝑑𝑒𝑠)=𝑃(𝐹𝑖𝑟𝑠𝑡𝑐𝑎𝑟𝑑𝑖𝑠𝑎𝑠𝑝𝑎𝑑𝑒)∙𝑃(𝑆𝑒𝑐𝑜𝑛𝑑𝑐𝑎𝑟𝑑𝑖𝑠𝑎𝑠𝑝𝑎𝑑𝑒)𝑃(𝐹𝑖𝑟𝑠𝑡𝑐𝑎𝑟𝑑𝑖𝑠𝑎𝑠𝑝𝑎𝑑𝑒)=1352

---

There are 12 spades left in the deck if one is pulled and not replaced, and 51 total cards remaining.𝑃(𝑆𝑒𝑐𝑜𝑛𝑑𝑐𝑎𝑟𝑑𝑖𝑠𝑎𝑠𝑝𝑎𝑑𝑒)=1251𝑃(𝐵𝑜𝑡ℎ𝑎𝑟𝑒𝑠𝑝𝑎𝑑𝑒𝑠)=1352∙1251=1562652=117=.0588𝑜𝑟5.88%
What is the probability of drawing a red king and then a black 7 without replacement?𝑃(𝑅𝑒𝑑𝑘𝑖𝑛𝑔𝑡ℎ𝑒𝑛𝑏𝑙𝑎𝑐𝑘7)=𝑃(𝑅𝑒𝑑𝑘𝑖𝑛𝑔)∙𝑃(𝑆𝑒𝑐𝑜𝑛𝑑𝑐𝑎𝑟𝑑𝑖𝑠𝑎𝑏𝑙𝑎𝑐𝑘𝑠𝑒𝑣𝑒𝑛)

----

There are 4 of each card, so there are2 red and 2 black of each card. This means we have 2 red kings in the deck, and 2 black 7’s in the deck.𝑃(𝑅𝑒𝑑𝑘𝑖𝑛𝑔)=252*Even with a red king drawn first, there will still be 2 black 7’s in the deck, but only 51 cards remaining.𝑃(𝑆𝑒𝑐𝑜𝑛𝑑𝑐𝑎𝑟𝑑𝑖𝑠𝑎𝑏𝑙𝑎𝑐𝑘𝑠𝑒𝑣𝑒𝑛)=251𝑃(𝑅𝑒𝑑𝑘𝑖𝑛𝑔𝑡ℎ𝑒𝑛𝑏𝑙𝑎𝑐𝑘7)=252∙251=42652=1663=.0015𝑜𝑟.15%What is the probability of being dealt a flush (5 cards of all the same suit) from the first 5 cards in a deck?

---

The first card it does not matter what the suit is. Any of the suits can be drawninitially, as long as the next four cards are of thesame suit as the original card.

---

There are 13 of each suit in the deck, so after the first card is drawn, there are only 12 of that suit, then 11 left for the third card, 10 left for the fourth card, and 9 left for the final card. Also, there will be one less card total in the deck each time. 𝑃(𝑓𝑙𝑢𝑠ℎ)=𝑃(2𝑛𝑑𝑖𝑠𝑠𝑎𝑚𝑒𝑠𝑢𝑖𝑡)∙𝑃(3𝑟𝑑𝑖𝑠𝑠𝑎𝑚𝑒𝑠𝑢𝑖𝑡)∙𝑃(4𝑡ℎ𝑖𝑠𝑠𝑎𝑚𝑒𝑠𝑢𝑖𝑡)∙𝑃(5𝑡ℎ𝑖𝑠𝑠𝑎𝑚𝑒𝑠𝑢𝑖𝑡)𝑃(𝑓𝑙𝑢𝑠ℎ)=1251∙1150∙1049∙948=118805997600=3316660=.00198𝑜𝑟.198%What is the probability of drawing two face cards, and then 2 numbered cards, without replacement?

---

There are 12 face cards (Kings, queens, and jacks) and there are 36 numbered cards (2’s through 10’s).After the first face card is drawn, there will be 11 face cards leftover, and 51 total cards remaining.
