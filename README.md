# Mission-to-Mars

### Project Overview
This project is to gather the data about the mission to mars from various websites by using web scraping tools, and store the scraped data into Mongo database. After that, put the data all together in a web application, Flask. Users are able to get the latest news and updates with the click of a button.
### Process

- Web scraping
([scraping.py](Challenge/scraping.py))

1. **Mars news**: scrape the lastst news title and its paragraph from NASA mars news webpage.
2. **Featured Image**: gather the featured images from the Jet Propulsion Laboratory's webpage.
3. **Mars Facts**: scrape a table contain Mars information.
4. **Mars’s hemispheres**: scrape full-resolution images of Mars’s hemispheres and the titles of those images.

- Create a web application with Flask and store data into MongoDB database
([app.py](Challenge/app.py))
```python
# Use flask_pymongo to set up mongo connection
app.config['MONGO_URI'] = 'mongodb://localhost:27017/mars_app'
mongo = PyMongo(app)

@app.route('/scrape')
def scrape():
    mars = mongo.db.mars
    mars_data = scraping.scrape_all()
    mars.update({}, mars_data, upsert=True)
    return redirect('/',code=302)
```

- Design the web app
([index.html](Challenge/templates/index.html))

### Results
Demo for websites
[]()

Demo for mobile-responsive
[]()
