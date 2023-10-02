// Import necessary packages and files
import 'package:flutter/material.dart';
import 'user_model.dart';
import 'hinted_text.dart';

// Entry point of the application
void main() => runApp(MyApp());

// Root widget of the application
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: ProfileScreen(), // Set ProfileScreen as the home screen of the app
    );
  }
}

// ProfileScreen class which is a StatefulWidget
class ProfileScreen extends StatefulWidget {
  @override
  _ProfileScreenState createState() => _ProfileScreenState(); // Create state for ProfileScreen
}

// State class for ProfileScreen widget
class _ProfileScreenState extends State<ProfileScreen> {
  final _textController = TextEditingController(); // Controller for the text input field
  User _user = User(favoriteBathroom: ''); // Create a User object with an empty favoriteBathroom
  bool _showFavoriteBathroom = false; // Boolean variable to determine whether to display favoriteBathroom text

  // Function to update the favoriteBathroom value in the User object
  void _updateFavoriteBathroom(String value) {
    setState(() {
      _user.favoriteBathroom = value;
    });
  }

  // Function called when the 'Enter' button is clicked
  void _onEnterClicked() {
    String favoriteBathroom = _textController.text.trim();
    if (favoriteBathroom.isNotEmpty) {
      setState(() {
        _user.favoriteBathroom = favoriteBathroom;
        _showFavoriteBathroom = true; // Set _showFavoriteBathroom to true to display the favorite bathroom text
      });
    } else {
      setState(() {
        _showFavoriteBathroom = false; // Set _showFavoriteBathroom to false to hide the favorite bathroom text
      });
    }
  }

  // Build method to create the UI of the widget
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Sign-Up'), // App bar title
      ),
      body: Padding(
        padding: EdgeInsets.all(20.0),
        child: Column(
          mainAxisAlignment: MainAxisAlignment.start,
          children: <Widget>[
            // Text asking for the user's favorite bathroom
            Text(
              'What is your favorite bathroom you\'ve used?',
              style: TextStyle(fontSize: 18),
            ),
            // Text input field for the user to enter their favorite bathroom
            TextField(
              controller: _textController,
              onChanged: _updateFavoriteBathroom,
              decoration: InputDecoration(
                  hintText: hintedText, // Display a hint text in the input field
                  border: OutlineInputBorder(),
                  suffixIcon: IconButton(
                    onPressed: () {
                      _textController.clear(); // Clear the text input field when the clear icon is pressed
                    },
                    icon: const Icon(Icons.clear),
                  )
              ),
            ),
            // Button to submit the favorite bathroom
            MaterialButton(
              onPressed: _onEnterClicked, // Call _onEnterClicked method when button is pressed
              color: Colors.blue,
              child: const Text('Enter', style: TextStyle(color: Colors.white)),
            ),
            SizedBox(height: 20), // Empty space for layout purposes
            // Display the text only if _showFavoriteBathroom is true
            if (_showFavoriteBathroom)
              Text(
                'Your favorite bathroom: ${_user.favoriteBathroom}',
                style: TextStyle(fontSize: 18),
              ),
          ],
        ),
      ),
    );
  }
}






