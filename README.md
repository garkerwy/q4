# q4
Country by Last Letter game
countries = ['Afghanistan', 'Albania', 'Algeria', 'Andorra', 'Angola', 'Antigua and Barbuda', 'Argentina', 
            'Armenia', 'Australia', 'Austria', 'Azerbaijan', 'Baden', ' The Bahamas', 
            'Bahrain', 'Bangladesh', 'Barbados', 'Belarus', 'Belgium', 'Belize', 'Benin', 'Bolivia', 'Bosnia and Herzegovina',
            'Botswana', 'Brazil', 'Brunei', 'Brunswick and Lüneburg', 'Bulgaria', 'Burkina Faso', 'Burundi', 'Cabo Verde', 
            'Cambodia', 'Cameroon', 'Canada', 'Central African Republic', 'Chad', 'Chile', 'China', 'Colombia', 
            'Comoros', 'Congo, Democratic Republic of the', 'Congo, Republic of the', 'Costa Rica', 'Côte d’Ivoire', 
            'Croatia', 'Cuba', 'Cyprus', 'Czech Republic', 'Denmark', 'Djibouti', 'Dominica', 'Dominican Republic', 
            'Timor-Leste', 'Ecuador', 'Egypt', 'El Salvador', 'Equatorial Guinea', 'Eritrea', 
            'Estonia', 'Eswatini', 'Ethiopia', 'Fiji', 'Finland', 'France', 'Gabon', 'The Gambia', 'Georgia', 'Germany', 
            'Ghana', 'Greece', 'Grenada', 'Guatemala', 'Guinea', 'Guinea-Bissau', 'Guyana', 'Haiti', 'Honduras', 'Hungary', 
            'Iceland', 'India', 'Indonesia', 'Iran', 'Iraq', 'Ireland', 'Israel', 'Italy', 'Jamaica', 'Japan', 'Jordan', 
            'Kazakhstan', 'Kenya', 'Kiribati', 'North Korea', ' South Korea', 'Kosovo', 'Kuwait', 'Kyrgyzstan', 'Laos', 
            'Latvia', 'Lebanon', 'Lesotho', 'Liberia', 'Libya', 'Liechtenstein', 'Lithuania', 'Luxembourg', 'Madagascar', 
            'Malawi', 'Malaysia', 'Maldives', 'Mali', 'Malta', 'Marshall Islands', 'Mauritania', 'Mauritius', 'Mexico', 
            'Micronesia, Federated States of', 'Moldova', 'Monaco', 'Mongolia', 'Montenegro', 'Morocco', 'Mozambique', 
            'Myanmar (Burma)', 'Namibia', 'Nauru', 'Nepal', 'Netherlands', 'New Zealand', 'Nicaragua', 'Niger', 'Nigeria',
            'North Macedonia', 'Norway', 'Oman', 'Pakistan', 'Palau', 'Panama', 'Papua New Guinea', 'Paraguay', 'Peru', 
            'Philippines', 'Poland', 'Portugal', 'Qatar', 'Romania', 'Russia', 'Rwanda', 'Saint Kitts and Nevis', 
            'Saint Lucia', 'Saint Vincent and the Grenadines', 'Samoa', 'San Marino', 'Sao Tome and Principe', 
            'Saudi Arabia', 'Senegal', 'Serbia', 'Seychelles', 'Sierra Leone', 'Singapore', 'Slovakia', 'Slovenia', 
            'Solomon Islands', 'Somalia', 'South Africa', 'Spain', 'Sri Lanka', 'Sudan', 'South Sudan', 'Suriname', 
            'Sweden', 'Switzerland', 'Syria', 'Taiwan', 'Tajikistan', 'Tanzania', 'Thailand', 'Togo', 'Tonga', 
            'Trinidad and Tobago', 'Tunisia', 'Turkey', 'Turkmenistan', 'Tuvalu', 'Uganda', 'Ukraine', 
            'United Arab Emirates', 'United Kingdom', 'United States', 'Uruguay', 'Uzbekistan', 'Vanuatu', 
            'Vatican City', 'Venezuela', 'Vietnam', 'Yemen', 'Zambia', 'Zimbabwe']
def
play_country_by_last_letter_game():
    print("Welcome to the Country by Last Letter game!")
    print("Enter a country name. THe next country must start with the last letter of the previous country.")
    print("Let's start!")

    current_country = countries[0]    
    print("Current country:"+ current_country)
    
    if true:
      player_input = input("Enter a country:").capitalize()





      def get_country_by_last_letter(last_letter):

    valid_countries = [country for country in countries if country[0].lower() == last_letter]

    return 
random.choice(valid_countries) if valid_countries else None



def main():

    print("Welcome to the Country by Last Letter game!")
    print("I'll start by naming a country, and then you should name a country starting with the last letter of the country I named.")
    print("Let's begin!")

    country = random.choice(countries)

    

    while True:

        print("Computer:", country)

        time.sleep(20)  # 20 seconds to think

        last_letter = country[-1].lower()

        player_country = input("Your turn: ").strip()



        if player_country.lower() == 'exit':

            print("Thanks for playing!")

            break



        if player_country.lower() != '' and player_country[0].lower() == last_letter:

            country = get_country_by_last_letter(player_country[-1].lower())

            if country is None:

                print("No country found with that letter. You win!")

                break

        else:

            print("Oops! Please enter a valid country starting with the letter '{}'.".format(last_letter))



if __name__ == "__main__":

    main()
      
