# InterruptIn
#include "mbed.h"

// Initialize a DigitalIn object for the button
InterruptIn button(USER_BUTTON);

// Function to be called when the button is pressed
void onButtonPress() {
    printf("Button pressed\n");
}

int main() {
    // Attach the address of the onButtonPress function to the rising edge
    button.rise(&onButtonPress);

    // Sleep on the main thread forever
    while(true) {
        ThisThread::sleep_for(1000ms);
    }
}
