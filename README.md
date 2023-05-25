# Tic Tac Toe Android Application

The Tic Tac Toe Android application allows two players to play the classic game on a 3x3 grid. The app is built using Java and the Android framework. Let's take a closer look at the key components and functionalities of the application.

## MainActivity.java
- This class represents the main activity of the Tic Tac Toe game.
- It handles the game logic, player turns, and grid state.
- The `performAction` method is called when a player clicks on a box in the grid, updating the game state and checking for a winning condition or draw.
- The `changePlayerTurn` method updates the UI to indicate the current player's turn.
- The `checkPlayerWin` method checks if the current player has won the game by comparing the box positions with the winning combinations.

This class represents the main activity of the Tic Tac Toe game. It handles the game logic, player turns, and grid state. Let's explore the important methods:

- `performAction(ImageView imageView, int selectedBoxPosition)`: This method is called when a player clicks on a box in the grid. It updates the box state, sets the appropriate image (X or O), checks for a winning condition or draw, and changes the player's turn accordingly.

```java
image1.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        if(isBoxSelectable(0)){
            performAction((ImageView)v, 0);
        }
    }
});
```

- `changePlayerTurn(int currentPlayerTurn)`: This method updates the UI to indicate the current player's turn. It changes the background color of the active player's layout.

```java
private void changePlayerTurn(int currentPlayerTurn) {
    playerTurn = currentPlayerTurn;
    if(playerTurn == 1){
        playerOneLayout.setBackgroundResource(R.drawable.round_back_blue_border);
        playerTwoLayout.setBackgroundResource(R.drawable.round_back_dark_blue);
    } else {
        playerTwoLayout.setBackgroundResource(R.drawable.round_back_blue_border);
        playerOneLayout.setBackgroundResource(R.drawable.round_back_dark_blue);
    }
}
```

- `checkPlayerWin()`: This method checks if the current player has won the game by comparing the box positions with the winning combinations. It returns true if the current player wins, and false otherwise.

```java
private boolean checkPlayerWin() {
    boolean response = false;
    for (int i = 0; i < combinationsList.size(); i++) {
        final int[] combination = combinationsList.get(i);
        if (boxPositions[combination[0]] == playerTurn &&
            boxPositions[combination[1]] == playerTurn &&
            boxPositions[combination[2]] == playerTurn) {
            response = true;
        }
    }
    return response;
}
```

## Result.java
This class represents the result activity that displays the game outcome and provides an option to restart the match. Let's explore the important methods:

- `onCreate(Bundle savedInstanceState)`: This method initializes the result text view and the try button. It retrieves the game result and player names from the intent extras and displays them in the UI.

```java
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_result);
    TextView result = findViewById(R.id.res);
    Button trybtn = findViewById(R.id.trybtn);
    trybtn.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View view) {
            MainActivity mainActivity = new MainActivity();
            mainActivity.restartMatch();
        }
    });

    Bundle extras = getIntent().getExtras();
    String NameOfPlayer = extras.getString("name");
    String msg = extras.getString("result") + " " + NameOfPlayer;
    result.setText(msg);
}
```

## AddPlayers.java
This class represents the activity where players can enter their names before starting the game. It collects the player names and validates them. Let's explore the important methods:

- `onCreate(Bundle savedInstanceState)`: This method initializes the player name EditText fields and the start game button. It retrieves the player names entered in the EditText fields, validates them, and starts the game when the start game button is clicked.

```
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_add_players);

    final EditText playerOne = findViewById(R.id.playerOneName);
    final EditText playerTwo = findViewById(R.id.playerTwoName);
    final Button startGameBtn = findViewById(R.id.startGameBtn);

    startGameBtn.setOnClickListener(new View.OnClickListener() {
        @Override
        public void onClick(View v) {

            final String getPlayerOneName = playerOne.getText().toString();
            final String getPlayerTwoName = playerTwo.getText().toString();

            if (getPlayerOneName.isEmpty() || getPlayerTwoName.isEmpty()) {
                Toast.makeText(AddPlayers.this, "Please enter player names", Toast.LENGTH_SHORT).show();
            } else {
                Intent intent = new Intent(AddPlayers.this, MainActivity.class);
                intent.putExtra("playerOne", getPlayerOneName);
                intent.putExtra("playerTwo", getPlayerTwoName);
                startActivity(intent);
            }
        }
    });
}
```
