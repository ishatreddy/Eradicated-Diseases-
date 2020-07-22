eradicated_diseases = {'Name': 'Small Pox','Year of last Occurence': 1977,'Country of last Occurence': 'Somalia',
' Total Deaths': 500,'Vaccine Founder': 'Edward Jenner'}

import csv
import os.path
from datetime import datetime


def save_file(fieldnames, filename):
    file_exists = os.path.isfile(filename)

    with open(filename, 'a') as csvfile:
        csvEntry = csv.DictWriter(csvfile, fieldnames=fieldnames)

        if file_exists is False:
            csvEntry.writeheader()

        csvEntry.writerow({
            'name' : input("Enter a New Disease Name:\n").title(),
            'year' : int(input("Enter the Year of Last Occurence:\n")),
            'country' : input("Enter the Country of Last Occurence:\n").title(),
            'deaths' : int(input("Enter the Number of Deaths (Millions):\n")),
            'vaccine' : input("Enter the Founder of the Vaccine:\n").title()
        })

def view_file(fieldnames, filename):
    with open("eradicated_diseases.csv") as csvfile:
        csvReader = csv.DictReader(csvfile, delimiter=',', fieldnames=fieldnames)

        eradicated_diseases = list(csvReader)

        for disease in eradicated_diseases:
            print(f'{disease["name"]:10} {disease["year"]:10} {disease["country"]:10} {disease["deaths"]:10} {disease["vaccine"]}')

print("Eradicated Diseases List")
print("-" * 30)

fieldnames = ['name', 'year', 'country', 'deaths', 'vaccine']
filename = 'eradicated_diseases.csv'

selection = 0
while selection != 3:
    selection = int(input('''
Enter Option Number
--------------------
1. Add Disease
2. View Disease List
3. Search for a Disease
4. Exit Program'''))

    if selection == 1:
        save_file(fieldnames, filename)
    elif selection == 2:
        view_file(fieldnames, filename)
    elif selection == 4:
        exit()
    else:
        print("Wrong Selection")
