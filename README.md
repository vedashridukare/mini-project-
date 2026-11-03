# #include <stdio.h> 
// Simulated sensor reading function 
void simulate_robot() { 
     // Array of mock sensor inputs: {Left_Sensor, Right_Sensor} 
     // 0 = White Surface, 1 = Black Line 
    int sensor_inputs[6][2] = {
         {0, 0}, // Step 1: On track -> Move Forward
         {1, 0}, // Step 2: Left on line -> Turn Left         
         {0, 0}, // Step 3: Back on track -> Move Forward         
         {0, 1}, // Step 4: Right on line -> Turn Right         
         {0, 0}, // Step 5: Back on track -> Move Forward         
         {1, 1}  // Step 6: Both on line -> Stop
    };
    printf("--- Line Following Robot Simulation ---\n\n"); 

     for (int i = 0; i < 6; i++) { 
         int leftSensor = sensor_inputs[i][0];         
         int rightSensor = sensor_inputs[i][1]; 
         
        printf("Step %d | Left Sensor: %d, Right Sensor: %d -> ", i + 1, leftSensor, rightSensor); 

        if (leftSensor == 0 && rightSensor == 0) {             
            printf("Action: Move FORWARD\n");         
            }          
        else if (leftSensor == 1 && rightSensor == 0) {             
             printf("Action: Turn LEFT\n");         
        }         
        else if (leftSensor == 0 && rightSensor == 1) {             
            printf("Action: Turn RIGHT\n");         
        }          
        else if (leftSensor == 1 && rightSensor == 1) {             
             printf("Action: STOP Robot\n");         
        }     
    }

     printf("\nSimulation Complete.\n"); 
 }
int main() {     
    simulate_robot();     
    return 0; 
}