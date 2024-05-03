# q4

Country by last letter game


import random
import time


def get_country():
    # List of countries
    countries = ['Abkhazia', 'Afghanistan', 'Albania', 'Algeria', 'Andorra', 'Angola', 'Antigua and Barbuda', 'Argentina', 
             'Armenia', 'Australia', 'Austria', 'Azerbaijan', 'Baden', 'Bahamas','Bahrain', 'Bangladesh', 'Barbados', 'Belarus',
             'Belgium', 'Belize', 'Benin', 'Bolivia', 'Bosnia and Herzegovina','Botswana', 'Brazil', 'Brunei', 'Brunswick and Lüneburg',
             'Bulgaria', 'Burkina Faso', 'Burundi', 'Cabo Verde', 'Cambodia', 'Cameroon', 'Canada', 'Central African Republic', 'Chad',
             'Chile', 'China', 'Colombia', 'Comoros', 'Congo, Democratic Republic of the', 'Congo', 'Costa Rica', 'Ivory Coast', 
            'Croatia', 'Cuba', 'Cyprus', 'Czech Republic', 'Denmark', 'Djibouti', 'Dominica', 'Dominican Republic','Timor-Leste',
            'Ecuador', 'Egypt', 'El Salvador', 'Equatorial Guinea', 'Eritrea', 'Estonia', 'Eswatini', 'Ethiopia', 'Fiji',
            'Finland', 'France', 'Gabon', 'The Gambia', 'Georgia', 'Germany','Ghana', 'Greece', 'Grenada', 'Guatemala', 
            'Guinea', 'Guinea-Bissau', 'Guyana', 'Haiti', 'Honduras', 'Hungary', 'Iceland', 'India', 'Indonesia',
            'Iran', 'Iraq', 'Ireland', 'Israel', 'Italy', 'Jamaica', 'Japan', 'Jordan', 'Kazakhstan', 'Kenya', 'Kiribati',
            'North Korea', ' South Korea', 'Kosovo', 'Kuwait', 'Kyrgyzstan', 'Laos', 'Latvia', 'Lebanon', 'Lesotho', 
            'Liberia', 'Libya', 'Liechtenstein', 'Lithuania', 'Luxembourg', 'Madagascar', 'Malawi', 'Malaysia', 'Maldives', 
            'Mali', 'Malta', 'Marshall Islands', 'Mauritania', 'Mauritius', 'Mexico', 'Micronesia', 
            'Moldova', 'Monaco', 'Mongolia', 'Montenegro', 'Morocco', 'Mozambique', 'Myanmar', 'Namibia', 'Nauru',
            'Nepal', 'Netherlands', 'New Zealand', 'Nicaragua', 'Niger', 'Nigeria','North Macedonia', 'Norway', 'Oman',
            'Pakistan', 'Palau', 'Panama', 'Papua New Guinea', 'Paraguay', 'Peru', 'Philippines', 'Poland', 'Portugal',
            'Qatar', 'Romania', 'Russia', 'Rwanda', 'Saint Kitts and Nevis', 'Saint Lucia', 'Saint Vincent and the Grenadines', 
            'Samoa', 'San Marino', 'Sao Tome and Principe', 'Saudi Arabia', 'Senegal', 'Serbia', 'Seychelles', 'Sierra Leone', 
            'Singapore', 'Slovakia', 'Slovenia', 'Solomon Islands', 'Somalia', 'South Africa', 'Spain', 'Sri Lanka', 'Sudan',
            'South Sudan', 'Suriname', 'Sweden', 'Switzerland', 'Syria', 'Taiwan', 'Tajikistan', 'Tanzania', 'Thailand', 
            'Togo', 'Tonga', 'Trinidad and Tobago', 'Tunisia', 'Turkey', 'Turkmenistan', 'Tuvalu', 'Uganda', 'Ukraine', 
            'United Arab Emirates', 'United Kingdom', 'United States', 'Uruguay', 'Uzbekistan', 'Vanuatu', 'Vatican City',
            'Venezuela', 'Vietnam', 'Yemen', 'Zambia', 'Zimbabwe']

  # Select a random country from the list
    return random.choice(countries)

def play_game(countries):
    print("Welcome to Country by Last Letter!")
    print("I'll start by naming a country, and you have 20 seconds to name a country starting with the last letter of mine.")
    print("Let's begin!")

    while True:
        # Get a country name
        current_country = get_country()
        print("My country is:", current_country)

        # Get the last letter of the country name
        last_letter = current_country[-1].lower()

        # Start timer
        start_time = time.time()

        # Get user input
        user_input = input("Your country (20 seconds): ").strip().capitalize()

        # End timer
        end_time = time.time()

        # Check if user input is valid and starts with the correct letter
        if user_input == "Exit":
            print("Thanks for playing!")
            break
        elif user_input[0].lower() != last_letter:
            print("Sorry, your country name doesn't start with the correct letter.")
            continue
        elif user_input.lower() not in (country.lower() for country in countries):
            print("Sorry, that's not a valid country.")
            continue
        else:
            print("Correct!")

        # Check time taken
        if end_time - start_time > 20:
            print("Time's up! You lost!")
            break

if __name__ == "__main__":
    countries = ['Abkhazia', 'Afghanistan', 'Albania', 'Algeria', 'Andorra', 'Angola', 'Antigua and Barbuda', 'Argentina', 
             'Armenia', 'Australia', 'Austria', 'Azerbaijan', 'Baden', 'Bahamas','Bahrain', 'Bangladesh', 'Barbados', 'Belarus',
             'Belgium', 'Belize', 'Benin', 'Bolivia', 'Bosnia and Herzegovina','Botswana', 'Brazil', 'Brunei', 'Brunswick and Lüneburg',
             'Bulgaria', 'Burkina Faso', 'Burundi', 'Cabo Verde', 'Cambodia', 'Cameroon', 'Canada', 'Central African Republic', 'Chad',
             'Chile', 'China', 'Colombia', 'Comoros', 'Congo, Democratic Republic of the', 'Congo', 'Costa Rica', 'Ivory Coast', 
            'Croatia', 'Cuba', 'Cyprus', 'Czech Republic', 'Denmark', 'Djibouti', 'Dominica', 'Dominican Republic','Timor-Leste',
            'Ecuador', 'Egypt', 'El Salvador', 'Equatorial Guinea', 'Eritrea', 'Estonia', 'Eswatini', 'Ethiopia', 'Fiji',
            'Finland', 'France', 'Gabon', 'The Gambia', 'Georgia', 'Germany','Ghana', 'Greece', 'Grenada', 'Guatemala', 
            'Guinea', 'Guinea-Bissau', 'Guyana', 'Haiti', 'Honduras', 'Hungary', 'Iceland', 'India', 'Indonesia',
            'Iran', 'Iraq', 'Ireland', 'Israel', 'Italy', 'Jamaica', 'Japan', 'Jordan', 'Kazakhstan', 'Kenya', 'Kiribati',
            'North Korea', ' South Korea', 'Kosovo', 'Kuwait', 'Kyrgyzstan', 'Laos', 'Latvia', 'Lebanon', 'Lesotho', 
            'Liberia', 'Libya', 'Liechtenstein', 'Lithuania', 'Luxembourg', 'Madagascar', 'Malawi', 'Malaysia', 'Maldives', 
            'Mali', 'Malta', 'Marshall Islands', 'Mauritania', 'Mauritius', 'Mexico', 'Micronesia', 
            'Moldova', 'Monaco', 'Mongolia', 'Montenegro', 'Morocco', 'Mozambique', 'Myanmar', 'Namibia', 'Nauru',
            'Nepal', 'Netherlands', 'New Zealand', 'Nicaragua', 'Niger', 'Nigeria','North Macedonia', 'Norway', 'Oman',
            'Pakistan', 'Palau', 'Panama', 'Papua New Guinea', 'Paraguay', 'Peru', 'Philippines', 'Poland', 'Portugal',
            'Qatar', 'Romania', 'Russia', 'Rwanda', 'Saint Kitts and Nevis', 'Saint Lucia', 'Saint Vincent and the Grenadines', 
            'Samoa', 'San Marino', 'Sao Tome and Principe', 'Saudi Arabia', 'Senegal', 'Serbia', 'Seychelles', 'Sierra Leone', 
            'Singapore', 'Slovakia', 'Slovenia', 'Solomon Islands', 'Somalia', 'South Africa', 'Spain', 'Sri Lanka', 'Sudan',
            'South Sudan', 'Suriname', 'Sweden', 'Switzerland', 'Syria', 'Taiwan', 'Tajikistan', 'Tanzania', 'Thailand', 
            'Togo', 'Tonga', 'Trinidad and Tobago', 'Tunisia', 'Turkey', 'Turkmenistan', 'Tuvalu', 'Uganda', 'Ukraine', 
            'United Arab Emirates', 'United Kingdom', 'United States', 'Uruguay', 'Uzbekistan', 'Vanuatu', 'Vatican City',
            'Venezuela', 'Vietnam', 'Yemen', 'Zambia', 'Zimbabwe']
    play_game(countries)







    Brainstorming #2
(improved version)
1)Game gives a random country.
2)I answer that by giving a country name that starts with the last letter of the country that game gave me.
3)My answer’s last letter is the beginning of the country’s name that now game should answer.

******************************************
(Game should ask: Do you want to play only with me, or with two and more people?
If with 2 or more then game should ask for names and then randomly say who starts first, who starts second(depending how many people is playing)
Then chosen person should name any country and after, each person should name a country that starts with the last letter of previous country
If with only you: game should randomly chose who starts first giving a country and then just play as I wrote)

(Time given in between is 20 seconds)
(Same countries cannot be used)
(Each person have 3 attempts for wrong answer)
(After attempts are used the game should say (Game over, you lost!))
(To win the game each person should name 7 right answers, game should say (Game over, you win!))

       
          
          
          
          
         **(corrections)        
           Brainstorming #2
          (improved version)
1)Game gives a random country.
2)I answer that by giving a country name that starts with the last letter of the country that game gave me.
3)My answer’s last letter is the beginning of the country’s name that now game should answer.

******************************************
(Game should ask: Do you want to play only with me, or with two and more people?
If with 2 or more then game should ask for names and then randomly say who starts first, who starts second(depending how many people is playing)
Then chosen person should name any country and after, each person should name a country that starts with the last letter of previous country
If with only you: game should randomly chose who starts first giving a country and then just play as I wrote)

(Time given in between is 20 seconds)
(Same countries cannot be used)
(Each person have 3 attempts for wrong answer)
(After attempts are used the game should say (Game over, you lost!))
(To win the game each person should name 7 right answers, game should say (Game over, you win!))
(Game cannot accept as an answer the same country as it was given.)
(Should not give:
Correct, good job!
Time's up! You lost!)
(If time is up then only:Time's up! You lost!)
    


(comments about current work and what needs to be changed:)
Code that I wrote above needs to be improved because if you give the same answer as the game gave to you, it counts for the correct answer.
Also only the game is asking for a country but not answering, which needs to be corrected. 
Game is not asking for how many people will play, it needs to be corrected.
Also I need to think about ways to fair this game if someone plays with a computer, (cause computer will anyways).
Add code for attempts that each person can have(3).
Add code to make a win for the person who named 7 right answers.


MAYBE:
Add not only countries, but also cities
First ask : Do you want to play a country game or city game?
(try to create those codes, if it too complicated then there is no need to change game)




     
