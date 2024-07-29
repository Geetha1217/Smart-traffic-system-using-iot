const int sensorNorth = A0; // IR sensor input for the north road
const int sensorSouth = A1; // IR sensor input for the south road
const int sensorEast = A2; // IR sensor input for the east road
const int sensorWest = A3; // IR sensor input for the west road
const int redNorth = 6; // Red LED for the north road
const int greenNorth = 7; // Green LED for the north road
const int redSouth = 8; // Red LED for the south road
const int greenSouth = 9; // Green LED for the south road
const int redEast = 10; // Red LED for the east road
const int greenEast = 11; // Green LED for the east road
const int redWest = 12; // Red LED for the west road
const int greenWest = 13; // Green LED for the west road
const int yellowNorth=2;
const int yellowSouth=3;
const int yellowEast=4;
const int yellowWest=5;
bool northOccupied = false;
bool southOccupied = false;
bool eastOccupied = false;
bool westOccupied = false;
void setup() {
 pinMode(sensorNorth, INPUT);
 pinMode(sensorSouth, INPUT);
 pinMode(sensorEast, INPUT);
 pinMode(sensorWest, INPUT);
 pinMode(redNorth, OUTPUT);
 pinMode(greenNorth, OUTPUT);
 pinMode(redSouth, OUTPUT);
 pinMode(greenSouth, OUTPUT);
 pinMode(redEast, OUTPUT);
 pinMode(greenEast, OUTPUT);
 pinMode(redWest, OUTPUT);
 pinMode(greenWest, OUTPUT);
 pinMode(yellowNorth, OUTPUT);
 pinMode(yellowSouth, OUTPUT);
 pinMode(yellowEast, OUTPUT);
 pinMode(yellowWest, OUTPUT);
}
void loop() {
 // Read sensor inputs
 northOccupied = digitalRead(sensorNorth) == LOW;
 southOccupied = digitalRead(sensorSouth) == LOW;
 eastOccupied = digitalRead(sensorEast) == LOW;
 westOccupied = digitalRead(sensorWest) == LOW;
 // Traffic signal control logic
 if (northOccupied && !southOccupied && !eastOccupied && !westOccupied) {
 // Only north road has traffic
 digitalWrite(greenNorth, HIGH);
 digitalWrite(redNorth, LOW);
 digitalWrite(greenSouth, LOW);
 digitalWrite(redSouth, HIGH);
 digitalWrite(greenEast, LOW);
 digitalWrite(redEast, HIGH);
 digitalWrite(greenWest, LOW);
 digitalWrite(redWest, HIGH);
 digitalWrite(yellowNorth, LOW);
 digitalWrite(yellowSouth, LOW);
 digitalWrite(yellowEast, LOW);
 digitalWrite(yellowWest, LOW);
 } else if (!northOccupied && southOccupied && !eastOccupied && !westOccupied) {
 // Only south road has traffic
 // (Similar logic for other directions)
 digitalWrite(greenNorth, LOW);
 digitalWrite(redNorth, HIGH);
 digitalWrite(greenSouth, HIGH);
 digitalWrite(redSouth, LOW);
 digitalWrite(greenEast, LOW);
 digitalWrite(redEast, HIGH);
 digitalWrite(greenWest, LOW);
 digitalWrite(redWest, HIGH);
 digitalWrite(yellowNorth, LOW);
 digitalWrite(yellowSouth, LOW);
 digitalWrite(yellowEast, LOW);
 digitalWrite(yellowWest, LOW);
 }else if (!northOccupied && !southOccupied && eastOccupied && !westOccupied) {
 // Only east road has traffic
 // (Similar logic for other directions)
 digitalWrite(greenNorth, LOW);
 digitalWrite(redNorth, HIGH);
 digitalWrite(greenSouth, LOW);
 digitalWrite(redSouth, HIGH);
 digitalWrite(greenEast, HIGH);
 digitalWrite(redEast, LOW);
 digitalWrite(greenWest, LOW);
 digitalWrite(redWest, HIGH);
 digitalWrite(yellowNorth, LOW);
 digitalWrite(yellowSouth, LOW);
 digitalWrite(yellowEast, LOW);
 digitalWrite(yellowWest, LOW);
 } else if (!northOccupied && !southOccupied && !eastOccupied && westOccupied) {
 // Only WEST road has traffic
 // (Similar logic for other directions)
 digitalWrite(greenNorth, LOW);
 digitalWrite(redNorth, HIGH);
 digitalWrite(greenSouth, LOW);
 digitalWrite(redSouth, HIGH);
 digitalWrite(greenEast, LOW);
 digitalWrite(redEast, HIGH);
 digitalWrite(greenWest, HIGH);
 digitalWrite(redWest, LOW);
 digitalWrite(yellowNorth, LOW);
 digitalWrite(yellowSouth, LOW);
 digitalWrite(yellowEast, LOW);
 digitalWrite(yellowWest, LOW);
 }else if (!northOccupied && !southOccupied && !eastOccupied && !westOccupied) {
 // No traffic on any road, flash yellow on all roads
 // (Similar logic for other directions)
 digitalWrite(yellowNorth,HIGH);
 digitalWrite(yellowSouth,HIGH);
 digitalWrite(yellowEast,HIGH);
 digitalWrite(yellowWest,HIGH);
 digitalWrite(redNorth,LOW);
 digitalWrite(redSouth,LOW);
 digitalWrite(redEast,LOW);
 digitalWrite(redWest,LOW);
 digitalWrite(greenNorth, LOW);
 digitalWrite(greenSouth, LOW);
 digitalWrite(greenEast, LOW);
 digitalWrite(greenWest, LOW);
 } else {
 // Intersection is busy, all red
 //digitalWrite(greenNorth, LOW);
 //digitalWrite(redNorth, HIGH);
 //digitalWrite(greenSouth, LOW);
 //digitalWrite(redSouth, HIGH);
 //digitalWrite(greenEast, LOW);
 //digitalWrite(redEast, HIGH);
 //digitalWrite(greenWest, LOW);
 //digitalWrite(redWest,HIGH);
 //digitalWrite(yellowNorth, LOW);
 //digitalWrite(yellowSouth, LOW);
 //digitalWrite(yellowEast, LOW);
 //digitalWrite(yellowWest, LOW);
 digitalWrite(redNorth,LOW);
 digitalWrite(greenNorth,HIGH);
 digitalWrite(yellowNorth,LOW);
 digitalWrite(redSouth,HIGH);
 digitalWrite(greenSouth,LOW);
 digitalWrite(yellowSouth,LOW);
 digitalWrite(redEast,HIGH);
 digitalWrite(redWest,HIGH);
 digitalWrite(greenWest,LOW);
 digitalWrite(greenEast,LOW);
 digitalWrite(yellowEast,LOW);
 digitalWrite(yellowWest,LOW);
 delay(10000);
 digitalWrite(redSouth,LOW);
 digitalWrite(yellowSouth,LOW);
 digitalWrite(greenSouth,HIGH);
 digitalWrite(redEast,HIGH);
 digitalWrite(redWest,HIGH);
 digitalWrite(greenWest,LOW);
 digitalWrite(greenEast,LOW);
 digitalWrite(yellowEast,LOW);
 digitalWrite(yellowWest,LOW);
 digitalWrite(redNorth,HIGH);
 digitalWrite(greenNorth,LOW);
 digitalWrite(yellowNorth,LOW);
 delay(10000);
 digitalWrite(redEast,LOW);
 digitalWrite(yellowEast,LOW);
 digitalWrite(greenEast,HIGH);
 digitalWrite(redNorth,HIGH);
 digitalWrite(greenNorth,LOW);
 digitalWrite(yellowNorth,LOW);
 digitalWrite(redSouth,HIGH);
 digitalWrite(greenSouth,LOW);
 digitalWrite(yellowSouth,LOW);
 digitalWrite(redWest,HIGH);
 digitalWrite(greenWest,LOW);
 digitalWrite(yellowWest,LOW);
 delay(10000);
 digitalWrite(redWest,LOW);
 digitalWrite(yellowWest,LOW);
 digitalWrite(greenWest,HIGH);
 digitalWrite(redNorth,HIGH);
 digitalWrite(greenNorth,LOW);
 digitalWrite(yellowNorth,LOW);
 digitalWrite(redSouth,HIGH);
 digitalWrite(greenSouth,LOW);
 digitalWrite(yellowSouth,LOW);
 digitalWrite(redEast,HIGH);
 digitalWrite(greenEast,LOW);
 digitalWrite(yellowEast,LOW);
 delay(10000);
 }}
