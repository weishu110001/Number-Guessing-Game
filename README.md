# Number-Guessing-Game

//This is the very first game that I created using C# and Unity Engine. It is a number guessing game, where the program will guess the number that user choose. 
_______________________________________________________________________________________________________________________________________________________________________________


using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class NumberWizard : MonoBehaviour
{
    int max; //Declare the variable max.
    int min; //Declare the variable for min.
    int guess; 


    // Start is called before the first frame update, use for initialization.
    void Start()
    {
        StartGame();
    }

    void StartGame()
    {
        max = 1000;
        min = 1;
        guess = 500;

        //Debug.log is essenitally same as print but with better practice.
        Debug.Log("Hello, welocome to my Number Guessing Game");
        Debug.Log("Please pick a number, and don't tell me what it is");
        Debug.Log("The highest number you can pick is: " + max); //string max value.
        Debug.Log("The Lowest number you can pick is: " + min); // string min value.
        Debug.Log("Please tell me if your number is higher or lower than: " + guess);
        Debug.Log("Push Up = higher, Push Down = Lower, Push Enter = Correct");
        max = max + 1;
    }

    // Update is called once per frame.
    // Below are the input commends for users. Keep in mind that if statements are conditional. 
    void Update()
    {
        ////Detect when the up arrow key is pressed down
        if (Input.GetKeyDown(KeyCode.UpArrow))
        {
            min = guess;
            NextGuess();
        }

        ////Detect when the down arrow key is pressed down
        else if (Input.GetKeyDown(KeyCode.DownArrow))
        {
            max = guess;
            NextGuess();
        }

        //Detect when the Return (Enter) key is pressed down
        else if (Input.GetKeyDown(KeyCode.Return))
        {
            Debug.Log("I got it right, thanks for playing :)");
            StartGame();
        }

    }
    void NextGuess()
    {
        guess = (max + min) / 2;
        Debug.Log("Is your number higher or lower than..." + guess);
    }
