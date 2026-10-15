# BANK Dice Game

A browser-based implementation of **Bank**, a press-your-luck dice game for playing with friends using either app-rolled dice or physical dice.

- **Play online:** https://shhosting.net/bank-dice-game
- **Current version:** 1.5.6
- **License:** MIT (see [LICENSE](LICENSE))

## Features

- Play with app-rolled dice or enter results from real dice.
- Add and manage player names.
- Choose 3, 6, or 12 rounds, or set a custom total from 1 to 999.
- Track the shared Bank, player status, scores, and whose turn it is.
- Undo the most recent roll in either dice mode.
- View final standings and round-by-round history.
- Continue a game after refreshing the page.
- Restart a game or return to setup with confirmation dialogs.
- Keep the same players for another game, or reset the saved game and setup.
- Use the optional immersive layout to hide the site's header and footer and give the game more screen space.
- Responsive layout with keyboard and accessibility support for key controls.

## How to play

Bank is played over a chosen number of rounds. Players take turns rolling two dice, and the rolls change one shared Bank total for everyone still playing in that round.

1. **Start a game.** Add the players, choose the number of rounds, and select **App rolls** or **I'll roll real dice**. The game works with one player, though it is designed for two or more.
2. **Rolls 1–3 of a round.** If the dice total 7, add 70 to the Bank. Any other result adds the dice total to the Bank; doubles do not multiply the Bank during these first three rolls.
3. **Roll 4 onward.** A 7 busts the round: the Bank resets to 0, and any player who has not banked receives 0 for the round. Doubles multiply the current Bank by 2. Any other result adds the dice total.
4. **Bank your points.** On your turn, choose **Bank** to lock in the current Bank total as your score for the round. You sit out until the next round.
5. **Finish the round.** A round ends when every player has banked or a bust occurs. Banked scores are kept; players who had not banked before a bust score 0 for that round.
6. **Win the game.** After the final round, the player or players with the highest cumulative score win.

With physical dice, roll two real dice and enter the result in the game. The interface provides buttons for the possible totals and doubles.

## Data and privacy

Game play runs in the browser. The game saves its current state and setup in the browser's `localStorage`, allowing a refresh to restore the game and its undo history. That saved state is local to the same browser profile and site origin; it does not sync across devices or browsers.

**Game state is not uploaded to a game server.** When served from shhosting.net, the page also loads shared site assets—such as the common stylesheet, navigation script, and branding—from the site.

To clear the saved game, use **Exit to setup → Reset game**. This clears Bank's saved state for this site; it does not clear unrelated browser data.

## Running and development

The game is implemented in `index.html` with no build step or third-party JavaScript framework.

The page uses the shhosting.net site shell and references shared resources through root-relative paths, including:

- `/assets/css/style.css` — shared site styling
- `/assets/js/nav.js` — shared hamburger-menu behavior
- `/assets/img/` — site logos and wordmarks

For local development with the complete site header, footer, theme behavior, and navigation, serve the page with those shared assets available at their expected paths. If you are only inspecting the game logic, the main game implementation and its styles are in `index.html`.

## Repository layout

```text
bank-dice-game/
├── index.html   # Game interface, styles, game logic, and browser persistence
├── LICENSE      # MIT License
└── README.md    # Project documentation
```

## License

This project is distributed under the [MIT License](LICENSE). Assistant/provider logos included in the AI tools menu remain the trademarks of their respective owners.
