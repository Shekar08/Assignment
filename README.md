import requests

def get_survey_numbers(district="YourDistrict", mandal="YourMandal", village="YourVillage"):
    url = "https://dharani.telangana.gov.in/knowLandStatus"
    payload = {
        "district": district,
        "mandal": mandal,
        "village": village
    }

    # Send a POST request with the payload
    response = requests.post(url, data=payload)

    # Print response status code
    print("Response Status Code:", response.status_code)

    if response.status_code == 200:
        # Print the HTML content of the response
        print(response.text)
    else:
        print("Failed to retrieve data. Status code:", response.status_code)

# Example usage with default values
get_survey_numbers()
