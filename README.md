# q4

Country By Last Letter game


import random

import time



def get_country(countries):

    """Returns a random country from the list."""

    return random.choice(countries)



def get_player_input(prompt, timeout=20):

    """Gets input from the player with a timeout."""

    start_time = time.time()

    user_input = ""

    print(prompt)

    while time.time() - start_time < timeout:

            user_input = input()

            break

    end_time = time.time()

    if end_time - start_time >= timeout:

        print("Time's up! You lost!")

        return None

    return user_input.strip().capitalize()



def play_solo_game(countries):

    """Handles the solo game mode."""

    print("Welcome to Country by Last Letter - Solo Mode!")

    print("You will play against the computer. I'll start by naming a country, and you have 20 seconds to name a country starting with the last letter of mine.")

    

    used_countries = set()

    player_attempts = 3

    correct_answers = 0



    current_country = get_country(countries)

    print("Computer starts with:", current_country)

    used_countries.add(current_country)



    while player_attempts > 0:

        last_letter = current_country[-1].lower()



        user_input = get_player_input(f"Your country (starts with '{last_letter}'): ", 20)

        if not user_input:

            break



        if user_input.lower() in used_countries:

            print("This country has already been used. Try again.")

            continue

        elif user_input[0].lower() != last_letter:

            print("Your country doesn't start with the correct letter.")

            player_attempts -= 1

            continue

        elif user_input.lower() not in (country.lower() for country in countries):

            print("That's not a valid country.")

            player_attempts -= 1

            continue

        else:

            print("Correct!")

            used_countries.add(user_input.lower())

            correct_answers += 1

            current_country = user_input

            if correct_answers >= 7:

                print("Game over, you win!")

                return



        if player_attempts == 0:

            print("Game over, you lost!")

            return



def play_multiplayer_game(countries):

    """Handles the multiplayer game mode."""

    num_players = int(input("Enter the number of players: "))

    players = [input(f"Enter name for player {i+1}: ") for i in range(num_players)]

    random.shuffle(players)



    print("The playing order will be:")

    for i, player in enumerate(players):

        print(f"{i+1}. {player}")



    used_countries = set()

    player_attempts = {player: 3 for player in players}

    correct_answers = {player: 0 for player in players}

    

    current_country = get_country(countries)

    used_countries.add(current_country)

    print(f"Starting country: {current_country}")



    current_index = 0

    while True:

        current_player = players[current_index]

        last_letter = current_country[-1].lower()



        user_input = get_player_input(f"{current_player}'s turn (starts with '{last_letter}'): ", 20)

        if not user_input:

            break



        if user_input.lower() in used_countries:

            print("This country has already been used. Try again.")

            continue

        elif user_input[0].lower() != last_letter:

            print("Your country doesn't start with the correct letter.")

            player_attempts[current_player] -= 1

            if player_attempts[current_player] == 0:

                print(f"{current_player}, you're out of attempts! Game over, you lost!")

                return

            continue

        elif user_input.lower() not in (country.lower() for country in countries):

            print("That's not a valid country.")

            player_attempts[current_player] -= 1

            if player_attempts[current_player] == 0:

                print(f"{current_player}, you're out of attempts! Game over, you lost!")

                return

            continue

        else:

            print("Correct!")

            used_countries.add(user_input.lower())

            correct_answers[current_player] += 1

            current_country = user_input

            if correct_answers[current_player] >= 7:

                print(f"Game over, {current_player} wins!")

                return



        current_index = (current_index + 1) % num_players



def main():

    countries = [

        'Abkhazia', 'Afghanistan', 'Albania', 'Algeria', 'Andorra', 'Angola', 'Antigua and Barbuda', 'Argentina', 

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

        'Venezuela', 'Vietnam', 'Yemen', 'Zambia', 'Zimbabwe'

    ]



    print("Welcome to Country By Last Letter game!")
    print( "Do you want to play solo or with multiple players?")

    mode = input("Type 'solo' for solo mode or 'multi' for multiplayer mode: ").strip().lower()

    

    if mode == 'solo':

        play_solo_game(countries)

    elif mode == 'multi':

        play_multiplayer_game(countries)

    else:

        print("Invalid option. Please restart the game and choose a valid mode.")



if __name__ == "__main__":

    main()







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


I'm working on my code

     
