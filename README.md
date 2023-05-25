# Tic Tac Toe Android Application

The Tic Tac Toe Android application allows two players to play the classic game on a 3x3 grid. The app is built using Java and the Android framework. Let's take a closer look at the key components and functionalities of the application.

-------------------------------------------------------------------------------------------------------------------------------------
# Layout

The application consists of 4 layouts containing the XML code.

## activity_main.xml

This layout file represents the main activity of the application.
It uses a `RelativeLayout` as the root view, allowing for flexible positioning of child views.
The background of the layout is set using the `android:background` attribute, referencing the background drawable resource.
The main content of the layout is divided into two sections using a `LinearLayout` with a horizontal orientation.
The first section represents "Player One" and includes a `TextView` to display the player's name and an `ImageView` to show the player's symbol (an "X" image).
The second section represents "Player Two" and is similar to the first section but with a different background color and an "O" image for the player's symbol.
The bottom section contains a container `LinearLayout` that holds a grid of 9 `ImageView` elements arranged in a 3x3 format. These image views have a transparent background and can be used to display game-related images or icons.

* Source Code:

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/background"
    tools:context=".MainActivity">


    <LinearLayout
        android:layout_above="@id/container"
        android:layout_alignParentTop="true"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="center"
        android:orientation="horizontal">

        <LinearLayout
            android:id="@+id/playerOneLayout"
            android:layout_width="120dp"
            android:layout_height="wrap_content"
            android:orientation="vertical"
            android:background="@drawable/round_back_blue_border"
            android:gravity="center">

            <TextView
                android:maxLines="1"
                android:id="@+id/playerOneName"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginTop="20dp"
                android:text="Player One"
                android:textColor="#FFFFFF"
                android:textStyle="bold"
                android:textSize="16sp"
                android:gravity="center"/>

            <ImageView
                android:layout_gravity="center"
                android:layout_width="40dp"
                android:layout_height="40dp"
                android:src="@drawable/xx"
                android:layout_marginTop="20dp"
                android:layout_marginBottom="20dp"/>

        </LinearLayout>

        <LinearLayout
            android:id="@+id/playerTwoLayout"
            android:layout_marginStart="30dp"
            android:layout_width="120dp"
            android:layout_height="wrap_content"
            android:orientation="vertical"
            android:background="@drawable/round_back_dark_blue"
            android:gravity="center">

            <TextView
                android:maxLines="1"
                android:id="@+id/playerTwoName"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_marginTop="20dp"
                android:text="Player Two"
                android:textColor="#FFFFFF"
                android:textStyle="bold"
                android:textSize="16sp"
                android:gravity="center"/>

            <ImageView
                android:layout_gravity="center"
                android:layout_width="40dp"
                android:layout_height="40dp"
                android:src="@drawable/oo"
                android:layout_marginTop="20dp"
                android:layout_marginBottom="20dp"/>

        </LinearLayout>
    </LinearLayout>

    <LinearLayout
        android:id="@+id/container"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_alignParentBottom="true"
        android:layout_marginStart="10dp"
        android:layout_marginEnd="10dp"
        android:orientation="vertical"
        android:background="@drawable/round_back_purple"
        android:layout_marginBottom="50dp">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="horizontal"
            android:weightSum="3">

            <ImageView
                android:id="@+id/image1"
                android:layout_marginTop="10dp"
                android:layout_marginEnd="5dp"
                android:layout_marginStart="10dp"
                android:layout_width="0dp"
                android:layout_height="120dp"
                android:layout_weight="1"
                android:adjustViewBounds="true"
                android:padding="20dp"
                android:src="@drawable/transparent_back"
                android:background="@drawable/round_back_dark_blue"/>

            <ImageView
                android:id="@+id/image2"
                android:layout_marginTop="10dp"
                android:layout_marginEnd="5dp"
                android:layout_marginStart="5dp"
                android:layout_width="0dp"
                android:layout_height="120dp"
                android:layout_weight="1"
                android:adjustViewBounds="true"
                android:padding="20dp"
                android:src="@drawable/transparent_back"
                android:background="@drawable/round_back_dark_blue"/>

            <ImageView
                android:id="@+id/image3"
                android:layout_marginTop="10dp"
                android:layout_marginEnd="10dp"
                android:layout_marginStart="5dp"
                android:layout_width="0dp"
                android:layout_height="120dp"
                android:layout_weight="1"
                android:adjustViewBounds="true"
                android:padding="20dp"
                android:src="@drawable/transparent_back"
                android:background="@drawable/round_back_dark_blue"/>

        </LinearLayout>

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="horizontal"
            android:weightSum="3">

            <ImageView
                android:id="@+id/image4"
                android:layout_marginTop="10dp"
                android:layout_marginEnd="5dp"
                android:layout_marginStart="10dp"
                android:layout_width="0dp"
                android:layout_height="120dp"
                android:layout_weight="1"
                android:adjustViewBounds="true"
                android:padding="20dp"
                android:src="@drawable/transparent_back"
                android:background="@drawable/round_back_dark_blue"/>

            <ImageView
                android:id="@+id/image5"
                android:layout_marginTop="10dp"
                android:layout_marginEnd="5dp"
                android:layout_marginStart="5dp"
                android:layout_width="0dp"
                android:layout_height="120dp"
                android:layout_weight="1"
                android:adjustViewBounds="true"
                android:padding="20dp"
                android:src="@drawable/transparent_back"
                android:background="@drawable/round_back_dark_blue"/>

            <ImageView
                android:id="@+id/image6"
                android:layout_marginTop="10dp"
                android:layout_marginEnd="10dp"
                android:layout_marginStart="5dp"
                android:layout_width="0dp"
                android:layout_height="120dp"
                android:layout_weight="1"
                android:adjustViewBounds="true"
                android:padding="20dp"
                android:src="@drawable/transparent_back"
                android:background="@drawable/round_back_dark_blue"/>

        </LinearLayout>

        <LinearLayout
            android:layout_marginBottom="10dp"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="horizontal"
            android:weightSum="3">

            <ImageView
                android:id="@+id/image7"
                android:layout_marginTop="10dp"
                android:layout_marginEnd="5dp"
                android:layout_marginStart="10dp"
                android:layout_width="0dp"
                android:layout_height="120dp"
                android:layout_weight="1"
                android:adjustViewBounds="true"
                android:padding="20dp"
                android:src="@drawable/transparent_back"
                android:background="@drawable/round_back_dark_blue"/>

            <ImageView
                android:id="@+id/image8"
                android:layout_marginTop="10dp"
                android:layout_marginEnd="5dp"
                android:layout_marginStart="5dp"
                android:layout_width="0dp"
                android:layout_height="120dp"
                android:layout_weight="1"
                android:adjustViewBounds="true"
                android:padding="20dp"
                android:src="@drawable/transparent_back"
                android:background="@drawable/round_back_dark_blue"/>

            <ImageView
                android:id="@+id/image9"
                android:layout_marginTop="10dp"
                android:layout_marginEnd="10dp"
                android:layout_marginStart="5dp"
                android:layout_width="0dp"
                android:layout_height="120dp"
                android:layout_weight="1"
                android:adjustViewBounds="true"
                android:padding="20dp"
                android:src="@drawable/transparent_back"
                android:background="@drawable/round_back_dark_blue"/>

        </LinearLayout>


    </LinearLayout>


</RelativeLayout>
```


## activity_add_players.xml

This layout file represents the activity for adding players' names.
It uses a `LinearLayout` as the root view with a vertical orientation, centering its child views.
The background of the layout is set using the `android:background` attribute, referencing the background drawable resource.
The layout includes two sections for entering player names.
Each section consists of an `ImageView` to display the player's symbol (an "X" or "O" image) and an `EditText` for entering the player's name.
The layout also includes a button (`AppCompatButton`) labeled "Start Game" to initiate the game after entering player names.

* Source Code:


```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:background="@drawable/background"
    tools:context=".AddPlayers">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textColor="#FFFFFF"
        android:textSize="30sp"
        android:text="Enter Players Names"
        android:textStyle="bold"/>

    <LinearLayout
        android:gravity="center_vertical"
        android:layout_width="match_parent"
        android:layout_height="50dp"
        android:layout_marginStart="20dp"
        android:layout_marginEnd="20dp"
        android:background="@color/dark_blue"
        android:layout_marginTop="50dp"
        android:orientation="horizontal">

        <ImageView
            android:layout_marginStart="20dp"
            android:layout_width="30dp"
            android:layout_height="30dp"
            android:src="@drawable/xx"
            android:adjustViewBounds="true"/>

        <EditText
            android:inputType="text"
            android:maxLines="1"
            android:id="@+id/playerOneName"
            android:layout_width="match_parent"
            android:layout_height="50dp"
            android:layout_marginStart="20dp"
            android:layout_marginEnd="20dp"
            android:hint="Player One"
            android:textColorHint="@color/light_white"
            android:background="@color/dark_blue"
            android:textColor="#FFFFFF"/>


    </LinearLayout>

    <LinearLayout
        android:gravity="center_vertical"
        android:layout_width="match_parent"
        android:layout_height="50dp"
        android:layout_marginStart="20dp"
        android:layout_marginEnd="20dp"
        android:background="@color/dark_blue"
        android:layout_marginTop="20dp"
        android:orientation="horizontal">

        <ImageView
            android:layout_marginStart="20dp"
            android:layout_width="30dp"
            android:layout_height="30dp"
            android:src="@drawable/oo"
            android:adjustViewBounds="true"/>

        <EditText
            android:inputType="text"
            android:maxLines="1"
            android:id="@+id/playerTwoName"
            android:layout_width="match_parent"
            android:layout_height="50dp"
            android:layout_marginStart="20dp"
            android:layout_marginEnd="20dp"
            android:hint="Player Two"
            android:textColorHint="@color/light_white"
            android:background="@color/dark_blue"
            android:textColor="#FFFFFF"/>

    </LinearLayout>

    <androidx.appcompat.widget.AppCompatButton
        android:id="@+id/startGameBtn"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginEnd="20dp"
        android:layout_marginStart="20dp"
        android:layout_marginTop="40dp"
        android:text="Start Game"
        android:textColor="#FFFFFF"
        android:background="@drawable/round_black_blue1000"/>
</LinearLayout>
```

## activity_result.xml

This layout file represents the activity layout for displaying game results.
It uses a `ConstraintLayout` as the root view, allowing for more complex view positioning and constraints.
The layout includes a `TextView` to display the game result message and a button (`Button`) labeled "Try again" to restart the game.
The `TextView` and button are centered vertically and horizontally in the layout using constraints.

* Source Code:

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".Result">

    <TextView
        android:id="@+id/res"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Text"
        android:textSize="16sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.543"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.299" />

    <Button
        android:id="@+id/trybtn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="20dp"
        android:layout_marginTop="40dp"
        android:layout_marginEnd="20dp"
        android:background="@drawable/round_black_blue1000"
        android:text="Try again"
        app:backgroundTint="#3F51B5"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.574"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.41" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

## win_dialog_layout.xml

This layout file represents a custom dialog layout that can be used to display a win message.
It uses a `RelativeLayout` as the root view, allowing for relative positioning of child views.
The layout includes a `TextView` to display the win message and a button (`AppCompatButton`) labeled "Start Again" to restart the game.
Both the `TextView` and button are contained within a `LinearLayout` that has a dark blue background.

* Source Code:

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="@color/dark_blue"
        android:orientation="vertical">

        <TextView
            android:id="@+id/messageTxt"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:gravity="center"
            android:layout_marginTop="20dp"
            android:layout_marginStart="20dp"
            android:layout_marginEnd="20dp"
            android:text="Message Here"
            android:textColor="#FFFFFF"
            android:textSize="18sp"
            android:textStyle="bold"/>

        <androidx.appcompat.widget.AppCompatButton
            android:id="@+id/startAgainBtn"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_margin="20dp"
            android:background="@drawable/round_black_blue1000"
            android:textColor="#FFFFFF"
            android:text="Start Again"/>
    </LinearLayout>

</RelativeLayout>
```

* Conclusion:
* 
- These XML layout files define the structure and appearance of different screens or components within your application. They specify the arrangement and styling of views, such as text views, image views, buttons, and containers, enabling you to create visually appealing and functional user interfaces for your Android application.

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

```java
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
