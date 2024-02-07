Build a Calculator using React Native
React Native is a well-known technology for developing mobile apps that can run across many platforms. It enables the creation of native mobile apps for iOS and Android from a single codebase. React Native makes it simple to construct vibrant, engaging, and high-performing mobile apps. In this tutorial, we will guide you through the process of building a simple calculator using React Native, enabling you to apply the fundamentals of React Native development.
To begin, you must configure your development environment. This requires the installation of Node.js, which acts as a runtime environment for executing JavaScript code outside of the limitations of a web browser.
Installation: In this article, we’ll use the Expo CLI edition, which provides a more seamless experience for running React Native apps. To create your React native environment, follow the tasks in the order listed.
Expo is a JavaScript and React-based platform that allows developers to use a unified codebase to construct cross-platform mobile applications for iOS, Android, and the web. This free and open-source framework provides a variety of tools and services that simplify the mobile app development process, allowing developers to create high-quality applications.

Steps to Create React Native Application
Step 1: Create a react native application by using this command
npx create-expo-app calculator-app-in-native
Step 2: After creating your project folder, i.e. calculator-app-in-native, use the following command to navigate to it:
cd calculator-app-in-native
Basic Approach: The fundamental method entails developing a calculator featuring conventional mathematical operations like addition, subtraction, multiplication, and division. It is necessary to devise a user interface (UI) comprising buttons for every digit and operation, alongside a display region for presenting the input and outcome. JavaScript functions can be employed to execute button interactions and carry out the required computations, thereby implementing the calculator’s logic.
Step 3: Open the App.js file. Simply paste the source code into the App.js file.
Explanation
This code imports required components from react-native and set up the functional component “App”. It initializes state variables for managing the calculator’s display value, selected operator, and first value.
The handleNumberInput function updates the display value when a number button is pressed, checking and adjusting if the current value is ‘0’.
The handleOperatorInput function is triggered by an operator button press. It assigns the selected operator, saves the current display value as the first value, and resets the display to ‘0’.
The handleEqual function calculates the result based on the operator, first value, and current display. It updates the display value, and resets the operator and first value.
The handleClear function resets the display value, operator, and first value when the clear button (C) is pressed.
The return statement constructs the calculator UI using View, Text, and TouchableOpacity components. The display value is in a separate container, while the number and operator buttons, equal button, and clear button are in the button container. The code includes a styles object that defines the styles for calculator components and elements. These styles are applied in the JSX code for the desired visual appearance.
Step 4: To run the react native application, open the Terminal and enter the command listed below. 
npx expo start
