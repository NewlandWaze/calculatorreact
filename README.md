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

import React, { useState } from 'react'; 
import { StyleSheet, Text, View, TouchableOpacity }  
    from 'react-native'; 
  
export default function App() { 
  
    // State variables 
    const [displayValue, setDisplayValue] = useState('0'); 
    const [operator, setOperator] = useState(null); 
    const [firstValue, setFirstValue] = useState(''); 
  
    // Function to handle number inputs 
    const handleNumberInput = (num) => { 
        if (displayValue === '0') { 
            setDisplayValue(num.toString()); 
        } else { 
            setDisplayValue(displayValue + num); 
        } 
    }; 
  
    // Function to handle operator inputs 
    const handleOperatorInput = (operator) => { 
        setOperator(operator); 
        setFirstValue(displayValue); 
        setDisplayValue('0'); 
    }; 
  
    // Function to handle equal button press 
    const handleEqual = () => { 
        const num1 = parseFloat(firstValue); 
        const num2 = parseFloat(displayValue); 
  
        if (operator === '+') { 
            setDisplayValue((num1 + num2).toString()); 
        } else if (operator === '-') { 
            setDisplayValue((num1 - num2).toString()); 
        } else if (operator === '*') { 
            setDisplayValue((num1 * num2).toString()); 
        } else if (operator === '/') { 
            setDisplayValue((num1 / num2).toString()); 
        } 
  
        setOperator(null); 
        setFirstValue(''); 
    }; 
  
    // Function to handle clear button press 
    const handleClear = () => { 
        setDisplayValue('0'); 
        setOperator(null); 
        setFirstValue(''); 
    }; 
  
    return ( 
        <View style={styles.container}> 
            <View style={styles.displayContainer}> 
                <Text style={styles.displayText}> 
                    {displayValue} 
                </Text> 
            </View> 
            <View style={styles.buttonContainer}> 
                <View style={styles.row}> 
                    <TouchableOpacity 
                        style={styles.button} 
                        onPress={() => handleNumberInput(7)} 
                    > 
                        <Text style={styles.buttonText}>7</Text> 
                    </TouchableOpacity> 
                    <TouchableOpacity 
                        style={styles.button} 
                        onPress={() => handleNumberInput(8)} 
                    > 
                        <Text style={styles.buttonText}>8</Text> 
                    </TouchableOpacity> 
                    <TouchableOpacity 
                        style={styles.button} 
                        onPress={() => handleNumberInput(9)} 
                    > 
                        <Text style={styles.buttonText}>9</Text> 
                    </TouchableOpacity> 
                    <TouchableOpacity 
                        style={[styles.button, styles.operatorButton]} 
                        onPress={() => handleOperatorInput('/')} 
                    > 
                        <Text style={[ 
                            styles.buttonText,  
                            styles.operatorButtonText 
                        ]}> 
                            ÷ 
                        </Text> 
                    </TouchableOpacity> 
                </View> 
                <View style={styles.row}> 
                    <TouchableOpacity 
                        style={styles.button} 
                        onPress={() => handleNumberInput(4)} 
                    > 
                        <Text style={styles.buttonText}>4</Text> 
                    </TouchableOpacity> 
                    <TouchableOpacity 
                        style={styles.button} 
                        onPress={() => handleNumberInput(5)} 
                    > 
                        <Text style={styles.buttonText}>5</Text> 
                    </TouchableOpacity> 
                    <TouchableOpacity 
                        style={styles.button} 
                        onPress={() => handleNumberInput(6)} 
                    > 
                        <Text style={styles.buttonText}>6</Text> 
                    </TouchableOpacity> 
                    <TouchableOpacity 
                        style={[styles.button, styles.operatorButton]} 
                        onPress={() => handleOperatorInput('*')} 
                    > 
                        <Text style={[ 
                            styles.buttonText,  
                            styles.operatorButtonText 
                        ]}> 
                            × 
                        </Text> 
                    </TouchableOpacity> 
                </View> 
                <View style={styles.row}> 
                    <TouchableOpacity 
                        style={styles.button} 
                        onPress={() => handleNumberInput(1)} 
                    > 
                        <Text style={styles.buttonText}>1</Text> 
                    </TouchableOpacity> 
                    <TouchableOpacity 
                        style={styles.button} 
                        onPress={() => handleNumberInput(2)} 
                    > 
                        <Text style={styles.buttonText}>2</Text> 
                    </TouchableOpacity> 
                    <TouchableOpacity 
                        style={styles.button} 
                        onPress={() => handleNumberInput(3)} 
                    > 
                        <Text style={styles.buttonText}>3</Text> 
                    </TouchableOpacity> 
                    <TouchableOpacity 
                        style={[styles.button, styles.operatorButton]} 
                        onPress={() => handleOperatorInput('-')} 
                    > 
                        <Text style={[ 
                            styles.buttonText,  
                            styles.operatorButtonText 
                        ]}> 
                            − 
                        </Text> 
                    </TouchableOpacity> 
                </View> 
                <View style={styles.row}> 
                    <TouchableOpacity 
                        style={[styles.button, styles.zeroButton]} 
                        onPress={() => handleNumberInput(0)} 
                    > 
                        <Text style={[ 
                            styles.buttonText,  
                            styles.zeroButtonText 
                        ]}> 
                            0 
                        </Text> 
                    </TouchableOpacity> 
                    <TouchableOpacity 
                        style={[styles.button, styles.operatorButton]} 
                        onPress={() => handleOperatorInput('+')} 
                    > 
                        <Text style={[ 
                            styles.buttonText,  
                            styles.operatorButtonText 
                        ]}> 
                            + 
                        </Text> 
                    </TouchableOpacity> 
                    <TouchableOpacity 
                        style={styles.equalButton} 
                        onPress={handleEqual} 
                    > 
                        <Text style={styles.equalButtonText}>=</Text> 
                    </TouchableOpacity> 
                </View> 
                <TouchableOpacity  
                    style={styles.clearButton}  
                    onPress={handleClear}> 
                    <Text style={styles.clearButtonText}>C</Text> 
                </TouchableOpacity> 
            </View> 
        </View> 
    ); 
} 
  
// Styles 
const styles = StyleSheet.create({ 
    container: { 
        flex: 1, 
        backgroundColor: '#f5f5f5', 
        alignItems: 'center', 
        justifyContent: 'center', 
    }, 
    displayContainer: { 
        flex: 2, 
        justifyContent: 'flex-end', 
        alignItems: 'flex-end', 
        padding: 20, 
    }, 
    displayText: { 
        fontSize: 48, 
        color: '#333', 
    }, 
    buttonContainer: { 
        flex: 3, 
        width: '80%', 
    }, 
    row: { 
        flex: 1, 
        flexDirection: 'row', 
        justifyContent: 'space-between', 
        marginBottom: 10, 
    }, 
    button: { 
        flex: 1, 
        borderRadius: 50, 
        alignItems: 'center', 
        justifyContent: 'center', 
        backgroundColor: '#fff', 
        elevation: 3, 
        margin: 2, 
        padding: 15, 
    }, 
    buttonText: { 
        fontSize: 34, 
        color: '#333', 
    }, 
    zeroButton: { 
        flex: 2, 
        paddingLeft: 35, 
        paddingRight: 35, 
    }, 
    zeroButtonText: { 
        marginLeft: 10, 
    }, 
    operatorButton: { 
        backgroundColor: '#f0f0f0', 
    }, 
    operatorButtonText: { 
        color: '#ff9500', 
    }, 
    equalButton: { 
        flex: 1, 
        borderRadius: 50, 
        alignItems: 'center', 
        justifyContent: 'center', 
        backgroundColor: '#ff9500', 
        elevation: 3, 
    }, 
    equalButtonText: { 
        fontSize: 32, 
        color: '#fff', 
    }, 
    clearButton: { 
        borderRadius: 50, 
        alignItems: 'center', 
        justifyContent: 'center', 
        backgroundColor: '#f0f0f0', 
        marginTop: 10, 
        elevation: 3, 
        padding: 10, 
    }, 
    clearButtonText: { 
        fontSize: 24, 
        color: '#333', 
    }, 
});

Explanation
This code imports required components from react-native and set up the functional component “App”. It initializes state variables for managing the calculator’s display value, selected operator, and first value.
The handleNumberInput function updates the display value when a number button is pressed, checking and adjusting if the current value is ‘0’.
The handleOperatorInput function is triggered by an operator button press. It assigns the selected operator, saves the current display value as the first value, and resets the display to ‘0’.
The handleEqual function calculates the result based on the operator, first value, and current display. It updates the display value, and resets the operator and first value.
The handleClear function resets the display value, operator, and first value when the clear button (C) is pressed.
The return statement constructs the calculator UI using View, Text, and TouchableOpacity components. The display value is in a separate container, while the number and operator buttons, equal button, and clear button are in the button container. The code includes a styles object that defines the styles for calculator components and elements. These styles are applied in the JSX code for the desired visual appearance.
Step 4: To run the react native application, open the Terminal and enter the command listed below. 
npx expo start
