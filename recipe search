import requests


def search_recipes(ingredient):
    base_url = "https://api.edamam.com/search"
    app_id = "174fbb6d"
    app_key = "67940bb4105a711b1183a12c29218fde"
    params = {
        "q": ingredient,
        "app_id": app_id,
        "app_key": app_key,
        "to": 5
    }

    response = requests.get(base_url, params=params)
    data = response.json()

    if response.status_code == 200:
        for recipe in data["hits"]:
            recipe_info = recipe["recipe"]
            print("Recipe:", recipe_info["label"])
            print("URL:", recipe_info["url"])
            print("Ingredients:", recipe_info["ingredientLines"])
            print("")

        print("Total recipes found:", len(data["hits"]))
    else:
        print("Error occurred:", data["error"])


ingredient = input("Enter an ingredient to search recipes: ")
search_recipes(ingredient)
