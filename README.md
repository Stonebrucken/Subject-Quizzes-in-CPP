#include <iostream> 
#include <string>

using namespace std;

int Guess;
int Total;
 
// Question Class or Question Prompt
class Question {
private:
    string Question_Text;
    string Answer_1;
    string Answer_2;
    string Answer_3;
    string Answer_4;
    int Correct_Answer;
    int Question_Score;
 
public:
    // Setter Function
    void setValues(string, string,
                   string, string,
                   string, int, int);
 
    // Function to ask questions
    void askQuestion();
};
 
// Driver code
int main()
{
    cout << "\n\n\t\t\t\tTHE GCSE MATHEMATICS QUIZ"
         << endl;
    cout << "\nPress Enter to start "
         << "the quiz... " << endl;
 
    // Input
    cin.get();
 
    string Name;
    int Age;
 
    // Input the details
    cout << "What is your name mathematician?"
         << endl;
    cin >> Name;
    cout << endl;
 
    string Respond;
    cout << "Are you ready to take"
         << " the quiz " << Name
         << "? yes/no" << endl;
    cin >> Respond;
 
    if (Respond == "yes") {
        cout << endl;
        cout << "Good Luck!" << endl;
    }
    else {
        cout << "Okay Bye!" << endl;
        return 0;
    }
 
    // Objects of Question Class
    Question q1;
    Question q2;
    Question q3;
    Question q4;
    Question q5;
    Question q6;
    Question q7;
    Question q8;
 
    // The Second last Integer will be equatable to the correct answer
    q1.setValues("Question 1: What equation is used to find the distance?", "S * T",
                 "D/T", "D/S",
                 "None of the above", 1, 5);
    q2.setValues("Qeustion 2: How do we workout the area of a Trapezium?: ", "2 + a div 2",
                 "div2(a + b)*c", "a * c",
                 "None of the above", 2, 5);
    q3.setValues("Question 3: Expand (2x + 8)(x + 3)", "2x squared + 11x + 24",
                 "2x squared + 12x + 24", "2x cubed + 11x + 24",
                 "None of the above", 1, 5);
    q4.setValues("Question 4: Factorise x squared + 14x + 24", "(x + 13)(x + 2)",
                 "(x + 12)(x + 2)", "(x + 12)(x + 3)",
                 "(x + 11)(x + 2)", 2, 5);
    q5.setValues("Question 5: What would sin 180 be equal to in terms of non-calculator trigonometry", "2/3pi",
                 "4/5pi", "2pi",
                 "pi", 4, 5);
    q6.setValues("Question 6: Work of Simultaneous Equation 2x - 3y = 11/2x - 2y = 7", "x = 4, y = 6.3 rec",
                 "x = 4, y = 3", "x = 2, y = 6.3 rec",
                 "x = 4, y = 6", 1, 5);            
    q7.setValues("Question 7: Simplify the Surd root 50", "5 root 2",
                 "3 root 5", "1 root 3",
                 "None of the above", 1, 5);
    q8.setValues("Question 8: Differentiate 4x^3 + 2x^2 + 7x + 8", "13x^2 + 4x + 7",
                 "12x^2 + 7x + 7 + c", "12x^2 + 4x + 7",
                 "None of the above", 3, 5);

 
    q1.askQuestion();
    q2.askQuestion();
    q3.askQuestion();
    q4.askQuestion();
    q5.askQuestion();
    q6.askQuestion();
    q7.askQuestion();
    q8.askQuestion();

 
    // Displays the total score
    cout << "Total Score = " << Total
         << "out of 40" << endl;
 
    // Displays the results
 
    // If the player passes the quiz then this happens
    if (Total >= 20) {
        cout << "Congrats you passed the Mathematics"
             << " quiz!" << endl;
    }
 
    // Otherwise
    else {
        cout << "Alas! You failed the quiz."
             << endl;
        cout << "Better luck next time."
             << endl;
    }
    return 0;
}
 
// Function to set the values of
// the questions
void Question::setValues(
    string q, string a1,
    string a2, string a3,
    string a4, int ca, int pa)
{
    Question_Text = q;
    Answer_1 = a1;
    Answer_2 = a2;
    Answer_3 = a3;
    Answer_4 = a4;
    Correct_Answer = ca;
    Question_Score = pa;
}
 
// Function to ask questions
void Question::askQuestion()
{
    cout << endl;
 
    // Print the questions
    cout << Question_Text << endl;
    cout << "1. " << Answer_1 << endl;
    cout << "2. " << Answer_2 << endl;
    cout << "3. " << Answer_3 << endl;
    cout << "4. " << Answer_4 << endl;
    cout << endl;
 
    // Display the answer
    cout << "What is your answer?(enter your answer as an integer ranging from answers 1-4)"
         << endl;
    cin >> Guess;
 
    // If the answer is correct
    if (Guess == Correct_Answer) {
        cout << endl;
        cout << "Correct !" << endl;
 
        // Update the correct score
        Total = Total + Question_Score;
        cout << "Score = " << Question_Score
             << " out of "
             << Question_Score
             << "!" << endl;
        cout << endl;
    }
 
    // Otherwise
    else {
        cout << endl;
        cout << "Wrong !" << endl;
        cout << "Score = 0"
             << " out of "
             << Question_Score
             << "!" << endl;
        cout << "Correct answer = "
             << Correct_Answer
             << "." << endl;
        cout << endl;
    }
