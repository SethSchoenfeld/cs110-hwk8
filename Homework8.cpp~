/*	Homework 8: Problem D
 *  This program reads a file of grades, displays letter, averages and lowest
 *  Inputs: File
 *  Outputs: message
 *  Created on: Oct 31, 2012 by Michael Shaw
 */

#include <iostream>
#include <fstream>
using namespace std;

// prototypes
int get_input_file(ifstream& infile);
void get_inputs (ifstream& infile, int& s1, int& s2, int& s3,int& s4);
int calcAverage(int s1, int s2, int s3, int s4);
char determineGrade(int n);
void minScore(int s2, int s3, int s4, int &min);


// main
int main() {
	//init variables
	int s1, s2, s3, s4, min;
	char average;
	ifstream infile;

	//get number of sets and initialize file
	int scoreSets = get_input_file(infile);

	//go through all score sets, one line at a time
	for (int i = 0; i < scoreSets; i++) {
		get_inputs (infile, s1, s2, s3, s4);

		//output scores as grades and the average grade
		cout << "Grade set " << i + 1 << ": " << determineGrade(s1) << " " << determineGrade(s2) << " "
				<< determineGrade(s3) << " " << determineGrade(s4) << endl;
		average = determineGrade(calcAverage(s1,s2,s3,s4));
		cout << "Average grade = " << average << endl;

		//finds lowest grade and outputs
		min = s1;
		minScore(s2, s3, s4, min);
		cout << "Lowest grade: " << determineGrade(min) << endl << endl;

	}

	return 0;

} //end of main

// gets input file
int get_input_file(ifstream& infile) {
	int n;

	// get file, check fail
	infile.open("scores.data");

	if (infile.fail()) {
			cout << "Input file failed\n";
			exit(1);
	}

 //writes file header value (number of data sets) to n
 infile >> n;
 return n;
}

// gets one set of values, writes values by reference
void get_inputs (ifstream &infile, int &s1, int &s2, int &s3,int &s4) {
	infile >> s1;
	infile >> s2;
	infile >> s3;
	infile >> s4;
}

// Calculates the average of four numbers casted as int
int calcAverage(int s1, int s2, int s3, int s4) {
	double temp = s1 + s2 + s3 + s4;
	temp = temp / 4;
	return int(temp);
}

// Sets letter grade for ints between 0 and 100
char determineGrade(int n) {
	char grade;

	//error out of range
	if (n > 100 || n < 0) {
		cout << "Invalid data";
		return 1;
	}
	//check grades
	else if (n > 89)
		grade = 'A';
	else if (n > 79)
		grade = 'B';
	else if (n > 69)
		grade = 'C';
	else if (n > 59)
		grade = 'D';
	else
		grade = 'F';

	return grade;
}

/* Out of four ints, finds lowest value and writes to address of min
 * min is arbitrarily set to first int in main to avoid extra looping
 * min is written back into main by reference
 * */
void minScore(int s2, int s3, int s4, int &min) {
	if (s2 < min)
		min=s2;
	if (s3 < min)
		min=s3;
	if (s4 < min)
		min=s4;

}


