# Online-Quiz-Application-Web-App
This C program runs a simple multiple choice quiz in the console. It asks a set of questions, takes user input,check answers, and displays the score at the end. It mimics the core logic of an online quiz app but runs locally.
#include <stdio.h>
#include <string.h>

struct Question {
    char question[200];
    char optionA[50];
    char optionB[50];
    char optionC[50];
    char optionD[50];
    char correct;
};

int main() {
    struct Question quiz[3] = {
        {"What is the capital of France?", "A) Paris", "B) London", "C) Berlin", "D) Rome", 'A'},
        {"Which language is used in Django?", "A) C", "B) Python", "C) Java", "D) PHP", 'B'},
        {"HTML stands for?", "A) Hyper Text Markup Language", "B) High Text Machine Language",
         "C) Hyperlink Mark Language", "D) None of these", 'A'}
    };

    int score = 0;
    char answer;

    printf("Welcome to the Quiz!\n\n");

    for (int i = 0; i < 3; i++) {
        printf("Q%d: %s\n", i+1, quiz[i].question);
        printf("%s\n%s\n%s\n%s\n", quiz[i].optionA, quiz[i].optionB,
               quiz[i].optionC, quiz[i].optionD);
        printf("Enter your answer (A/B/C/D): ");
        scanf(" %c", &answer);

        if (toupper(answer) == quiz[i].correct) {
            printf("Correct!\n\n");
            score++;
        } else {
            printf("Wrong! Correct answer: %c\n\n", quiz[i].correct);
        }
    }

    printf("Your final score: %d/%d\n", score, 3);
    return 0;
}
