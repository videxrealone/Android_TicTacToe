# Tic Tac Toe Android Application

The Tic Tac Toe Android application allows two players to play the classic game on a 3x3 grid. The app is built using Java and the Android framework. Let's take a closer look at the key components and functionalities of the application.

# Introduction

In Tic-Tac-Toe game when it is played between two players, one player being the user and another player as the computer, it has been observed by us that applying optimal strategy it usually ends up in a win or draw condition for the first player. In this paper, we have
developed a simulation model using min-max algorithm over optimal strategy by giving the players five more moves to change the previous input to minimize the draw scenario and to increase the complexity level of the game. 
* Keywords: game theory, min-max, optimal strategy, Tic-Tac-Toe.

The player who firstencounters three crosses (‘X’) or three noughts (‘O’) in a particular row, column or diagonal is declared as winner. There are 39 = 19,683 possible states in the game. The purpose of filling the nine spaces can be considered as filling the sequence of nine boxes that is maximum three in a row, column or diagonal. Therefore, there are 9! = 362,880 ways to fill
the 9th position.

Interestingly, Tic-Tac-Toe game can be reviewed using game theory, in which rational decisions of winning strategy can be considered between the two players. Tic-Tac-Toe uses the strategy that puts the player in the most preferred position irrespective of the strategy of his opponents. This strategy is called an optimal strategy.

# Application Life Cycle

The normal version of tic-tac-toe is a solved game. It always ends up with draw if both players play their best, so for the first player, the minimum requirement for him is a draw. If it is possible, he should also try to win his unqualified opponent by adopting
the method with the highest winning strategy.

Because of the logic of the game, our app consists of the following life cycle:

![image](https://github.com/videxrealone/Android_TicTacToe/assets/91763346/39800ece-ae36-4812-b9e8-007a50ec15e3)

We can also see that the end of the game is described in this simple graph:

![image](https://github.com/videxrealone/Android_TicTacToe/assets/91763346/4601340b-675f-4f06-a92c-ed852b55d22f)


-------------------------------------------------------------------------------------------------------------------

# Application UI & Goals

## Design Objectives:

The design objectives of the Tic Tac Toe application are to create an enjoyable and intuitive gaming
experience for two players. The user interface should be user-friendly and easy to comprehend,
providing clear indications of the player&#39;s turn and the game state. The application should allow
players to enter their names for a personalized experience. Additionally, the design should
incorporate the game&#39;s logic, checking for win and draw conditions, and enabling players to restart
the game if needed. The ultimate goal is to provide a entertaining and competitive gaming
experience for the players.

## Target Audience:

The target audience for the Tic Tac Toe application is primarily individuals who enjoy casual gaming
and want to engage in a simple yet entertaining game. The game is suitable for players of all ages,
including children, teenagers, and adults. It caters to both experienced gamers looking for a quick,
nostalgic experience and casual gamers seeking a fun pastime. The application&#39;s simplicity and
intuitive design make it accessible to a wide range of users, regardless of their gaming expertise.

## User Interface:

The user interface of the Tic Tac Toe application is designed to be intuitive and visually appealing.
The grid layout prominently displays the game board, with clear indicators for player turns and
selectable cells. The use of recognizable X and O symbols ensures familiarity for players, while visual
cues, such as highlighting the winning combinations, enhance the gameplay experience.

## Gameplay Mechanics:

The gameplay mechanics of the Tic Tac Toe application adhere to the traditional rules of the game.
Players take turns marking their symbols (X or O) on an empty cell of the 3x3 grid, aiming to create a
winning combination of three symbols in a row, column, or diagonal. The application ensures fair
play by validating each move, detecting winning conditions, and determining a draw when the grid is
full without a winner.

## Design Elements:

The design elements of the Tic Tac Toe application focus on simplicity and visual clarity. A clean and
uncluttered interface with a balanced color scheme enhances the overall user experience. The

typography is legible, and the use of appropriate iconography provides intuitive navigation and
feedback. The design elements contribute to a cohesive and enjoyable gameplay environment.

## Platform Considerations:
The Tic Tac Toe application was developed with platform considerations in mind, considering the
specific guidelines and conventions of the target platforms, such as iOS and Android. Adhering to
platform-specific design principles ensures consistency and familiarity for users, making the
application feel native and optimized for each platform.

## Conclusion:
In conclusion, the Tic Tac Toe application successfully achieves its objective of providing an engaging
and accessible digital version of the classic game. The user interface, gameplay mechanics, and
design elements combine to deliver a user-friendly and visually appealing experience. User feedback
and iterative design updates further enhance the application&#39;s usability and enjoyment. By
considering platform-specific guidelines, the application offers a native experience on each platform.
Overall, the Tic Tac Toe application provides a fun and interactive gameplay experience for a diverse
range of users.

-------------------------------------------------------------------------------------------------------------------------------------
# Layout

The application consists of 4 layouts containing the XML code.

## activity_main.xml

![capt2](https://github.com/videxrealone/Android_TicTacToe/assets/91763346/185cacc0-a5f3-4ea0-bc42-8c0fc19d1b16)


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

![capt1](https://github.com/videxrealone/Android_TicTacToe/assets/91763346/f72d0ea5-af10-416a-9ed1-8a55d9c9fa44)

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

![capt3](https://github.com/videxrealone/Android_TicTacToe/assets/91763346/091ff9f3-23d8-4383-b1e9-86c1909042ef)

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

In conclusion, this application demonstrates the use of XML layout files to create visually appealing and functional user interfaces for an Android application. By utilizing different layout containers and view elements, such as RelativeLayout, LinearLayout, TextView, ImageView, and buttons, we were able to design and structure various screens within the application.

The main activity (activity_main.xml) showcases a flexible layout using RelativeLayout, allowing for easy positioning of child views. It presents two player sections with their respective symbols and names, along with a grid of ImageView elements for game-related images or icons.

The activity for adding players' names (activity_add_players.xml) utilizes a LinearLayout with vertical orientation, providing a centered layout for entering player names. It also includes symbols and an EditText for each player, as well as a "Start Game" button to initiate gameplay.

The activity for displaying game results (activity_result.xml) demonstrates the use of a ConstraintLayout, enabling more complex view positioning and constraints. It includes a TextView to show the game result message and a "Try again" button, both centered both vertically and horizontally within the layout.

Additionally, the application includes a custom dialog layout (win_dialog_layout.xml) to display a win message. This layout utilizes a RelativeLayout and a LinearLayout with a dark blue background, containing a TextView and a "Start Again" button.

By leveraging the power of XML layout files, developers can create dynamic and interactive user interfaces that enhance the overall user experience. These layouts provide flexibility in arranging and styling views, ensuring an engaging and visually appealing interface for the application's users.

Overall, the successful implementation of these XML layout files highlights the importance of thoughtful design and user-friendly interfaces in creating compelling Android applications.

------------------------------------------------------------------------------------------------------------------------------------
# Java Project Files

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

# Conclusion

In conclusion, the development of this application has demonstrated the successful integration of Java code and XML layout files to create a fully functional and engaging Android application. By combining the power of programming logic with thoughtful UI design, the app provides an intuitive and immersive user experience.

The Java code forms the backbone of the application, implementing the game logic and user interactions. It encompasses features such as handling player input, tracking game progress, and determining the game's outcome. The well-structured and modular Java code enables smooth gameplay and ensures the app functions as intended.

The XML layout files play a crucial role in defining the visual structure and appearance of the application's screens and components. They provide flexible and responsive layouts, leveraging different layout containers like RelativeLayout, LinearLayout, and ConstraintLayout. These layouts enable the proper placement and styling of various view elements such as TextViews, ImageViews, and buttons. By utilizing XML layouts, the app achieves an appealing and user-friendly interface.

The integration of Java and XML in this application showcases the seamless collaboration between code and design. The Java code implements the logic and functionality, while the XML layout files handle the visual presentation and organization. This harmonious combination ensures a cohesive and engaging user experience, promoting ease of use and interactivity.

Furthermore, the app demonstrates effective utilization of user input, feedback mechanisms, and visual cues to enhance the overall gameplay experience. The UI elements, such as symbols, player names, and game result messages, are intelligently designed and thoughtfully placed, contributing to a polished and professional app.

Overall, the successful development of this application highlights the importance of synergy between Java code and XML layout files in creating robust and visually appealing Android applications. By leveraging the strengths of both aspects, developers can deliver user-centric and feature-rich apps that captivate and delight users.



