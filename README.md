# RecipesScraper

This repo contains various spiders to scrape different recipe websites.  

## Spiders

* [All Recipes](http://allrecipes.com/)
* [Jamie Oliver](http://www.jamieoliver.com/)
* [Epicurious](http://www.epicurious.com/)

## Running a spider

Each spider takes in a corresponding seed list (available in [`sitemap/seed_lists`](sitemap/seed_lists)) and either scrapes the recipe itself or follow recipes links on the section page.

To run a spider, use the following command:

```bash
nohup scrapy crawl <spider_name> &
```

where `<spider name>` is the name of the spider (`allrecipes` or `jamieoliver` for now).  This will create a JSON file named `<spider_name>_recipes.json` in the [`output`](output) folder.

Since this will be a long running process, it's a good idea to run it as a background process in no-hangup mode.

```bash
nohup scrapy crawl <spider_name> &
```

## Sample Output

Here's sample output for a [Black-Bean Quesadilla recipe from Epicurious](http://www.epicurious.com/recipes/food/views/black-bean-quesadillas-239962).

```JSON
{
    "date_scraped": "2017-02-11 22:33:05.667233",
    "recipes": [
        {
            "url": "http://www.epicurious.com/recipes/food/views/black-bean-quesadillas-239962",
            "ingredients": [
                "1 (19-ounce) can black beans, rinsed and drained",
                "1 (8-ounce) bag mixed grated \"taco cheese\"",
                "1 1/4 cups chopped cilantro, divided",
                "1 cup chopped white onion, divided",
                "8 (10-inch) flour tortillas",
                "1 tablespoon vegetable oil, divided",
                "2 large tomatoes, quartered",
                "1 to 2 teaspoons hot sauce",
                "Equipment: a large (2-burner) ridged grill pan (preferably cast-iron)"
            ],
            "recipe_name": "Black-Bean Quesadillas",
            "description": "Have we found Tex-Mex heaven? This very easy vegetarian meal satisfies with the heft of beans and melted mixed cheese.",
            "tags": [
                "Bean",
                "Cheese",
                "Tomato",
                "Vegetarian",
                "Quick & Easy",
                "Gourmet",
                "Tex-Mex"
            ]
        }
    ]
}
```
