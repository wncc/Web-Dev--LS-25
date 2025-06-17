## <a name="_6gqh41kkurqg"></a>**Practice 3: Memory Card Matching Game**
### <a name="_wxi4tjuvun8e"></a>**Project Statement:**
**Build an interactive Memory Card Game using React.**
In this classic game, users flip over pairs of cards to find matching symbols or images. The game reinforces React concepts like dynamic rendering, state management, conditional UI updates, and handling timed user interactions — all while being engaging and visually fun.
### <a name="_2n7uz4nbfaov"></a>**Learning Outcomes:**
- Use *useState* to track dynamic game state (flipped cards, matches, moves)
- Apply conditional rendering to control card flipping and visibility
- Handle event-based updates and user interaction (click to flip)
- Use *useEffect* for delays and game logic (e.g., flipping back unmatched cards)
- Design reusable card components with props
### <a name="_gni3ebdzfm0e"></a>**Core Features:**
1. **Card Grid:**

   - Display a grid of cards (e.g., 4x4 or 6x6)
   - Each card has a hidden symbol/image and can be flipped
1. **Flip & Match Logic:**

   - When a player clicks two cards:
      - Show both temporarily
      - If they match, keep them revealed
      - If not, flip them back after a short delay
1. **Move Counter:**

   - Track the number of moves or attempts made
1. **Winning State:**

   - When all pairs are matched, show a “You Win” message with stats
### <a name="_rfgsvy81k1xh"></a>**Bonus Features (Optional Enhancements):**
1. **Card Shuffle on Start:**

   - Randomly shuffle the cards each time the game begins to ensure a fresh challenge.
1. **Countdown Timer:**

   - Add a timer that tracks how long the player takes to finish the game..
1. **Theming & Emoji Packs:**

   - Allow players to switch between different **card themes** (e.g., emojis, animals, numbers, icons)
1. **Matched Pair Animation:**

   - Add a small animation (like a glow or bounce) when a correct match is made for a more interactive feel.
1. **Dark Mode Support:**

   - Include a toggle for switching between light and dark modes for eye comfort.
1. **Win Screen with Stats:**

  - At the end, show a summary screen with:
      - Time taken
      - Number of moves
      - “Play Again” option
<p align="center"> Created with ❤️ by WnCC </p>
