#include<iostream>
using namespace std;

//global variables
string inventory[10];
int health = 100;

//function declarations
void shop();
void Monster();
void NPC();


int main() {


	void shop();

	int room = 1;
	char input;

	cout << "You wake up tp find yourslef in a SPOOPY dungeon. Can you escape? Good luck!" << endl;

	do {
		switch (room) {
		case 1:
			NPC();
			cout << "You are in room 1. You can go (N)orth." << endl;
			cout << "press p for shop" << endl;
			cin >> input;
			if (input == 'N')
				room = 2;
			else if (input == 'p')
				shop();
			else
				cout << "sorry, not an option." << endl;
			break;
		
		case 2:
			cout << "You are in room 2. You can go (S)outh ,  (E)ast or (W)est." << endl;
			cin >> input;
			if (input == 'S')
				room = 1;
			else if (input == 'E')
				room = 4;
			else if (input == 'W')
				room = 3;
			else
				cout << "sorry, not an option." << endl;
			break;
		case 3:
			cout << "You are in room 3. You can go (E)" << endl;
			cin >> input;
			if (input == 'E')
				room = 2;
			else
				cout << "Sorry, not an option" << endl;
		case 4:
			cout << "You are in room 4. You can go (E)ast or (N)orth" << endl;
			cin >> input;
			if (input == 'E')
				room = 2;
			else if (input == 'N')
				room = 5;
			else
				cout << "Sorry, not an option" << endl;
		case 5:
			cout << "You are in room 5. You can continue (N)orth to room 6 or go (S)outh." << endl;
			cin >> input;
			if (input == 'N')
				room = 6;
			else if (input == 'S')
				room = 4;
			else
				cout << "Sorry, not an option" << endl;
		
		}
	} while (input != 'q');
}




void shop() {

	string input;
	do {
		cout << "Hi ! Welcome to my shop!" << endl;
		cout << "press 'p' for potion, 'k' for key, 'l' for lamp." << endl;
		cout << "press 'q' to quit." << endl;
		cin >> input;
		if (input == "p") {
			inventory[0] = "potion";

		}
		else if (input == "k") {
			inventory[1] = "key";
		}
		else if (input == "l")
			inventory[2] = "lamp";

	} while (input != "q");

}

void Monster() {
	int num = rand() % 100 + 1; 
	if (num < 20) {
		cout << "a skeleton appears!" << endl;
		health -= 10;
		cout << "the skeleton hits you for 10 damage" << endl;

	}
	else if (num < 50) {
		cout << "a zombie appears" << endl;
		health -= 20;
		cout << "the zombie bites you for 20 damge!" << endl;

	}
	else if (num < 75) {
		cout << "a spider appears!" << endl;
		health -= 15;
		cout << "the spider bites you for 10 damage!" << endl;

	}
	else
		cout << "no monsters" << endl;
}

void NPC() {
	int num = rand() % 3 + 1;
	switch (num) {
	case 1:
		cout << "a wizard appaears" << endl;
		num = rand() % 3 + 1;
		if (num == 1)
			cout << "Don't go into room 3, you'll get eaten" << endl;
		else if (num == 2)
			cout << "Make sure you pick up the swoard in room 2" << endl;
		else
			cout << "Did you find the key under the rug in room 3?" << endl;
		break;
	case 2:
		cout << "a grumpy frog appears" << endl;
		num = rand() % 3 + 1;
		if (num == 1)
			cout << "Ribbbbit...." << endl;
		else if (num == 2)
			cout << "Go away!" << endl;
		else
			cout << "it looks rainy" << endl;
		break;
	case 3:
		cout << "a happy hobbit appears" << endl;
		num = rand() % 3 + 1;
		if (num == 1)
			cout << "Good luck on your quest!" << endl;
		else if (num == 2)
			cout << "Nice wather!" << endl;
		else
			cout << "Stop by for a cup of tea sometime" << endl;
		break;
	}
}
