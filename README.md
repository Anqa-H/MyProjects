
# Watch Data Scraper and Analyzer


This project consists of a web scraper and data analyzer for extracting and analyzing watch data from the Louis Erard website. The main functionalities include extracting various attributes of watches, storing the data in a CSV file, and generating visualizations to analyze the data.

## Requirements
in this project I used the following libraries

- Selenium
- BeautifulSoup
- Requests
- Pandas
- NumPy
- Matplotlib
- Seaborn




## Setup
### Web Scraping

The script uses Selenium to navigate to the Louis Erard website and extract watch data. Update the URL variable to specify the webpage to scrape.




```bash
  URL = "https://louiserard.com/creations/?v=baa904278574&size-attr=39-mm,40-mm,42-mm,42-5-mm,43-mm,44-mm"

```

## Running the Script
Execute the script to start the web scraping process. The extracted data is stored in a dictionary and saved to a CSV file.
## Running the Script
Execute the script to start the web scraping process. The extracted data is stored in a dictionary and saved to a CSV file.
```bash
  if __name__ == '__main__':
```

## File Output
The scraped data is saved in louiserard_data.csv on the specified file path.
```bash
  louiserard_df.to_csv(r"your file path\\\\\louiserard_data.csv", header=True, index=False)
```

## Data Extraction Functions
The following functions are used to extract specific attributes from the webpage:

- get_reference_number(soup)
- get_Watch_URL(soup)
- get_gender(soup)
- get_brand(soup)
- get_year_introduced(soup)
- get_parent_model(soup)
- get_specific_model(soup)
- get_nickname(soup)
- get_marketing_name(soup)
- get_style(soup)
- get_currency(soup)
- get_price(soup)
- get_image_URL(soup)
- get_made_in(soup)
- get_case_shape(soup)
- get_case_material(soup)
- get_case_finish(soup)
- get_case_Back(soup)
- get_diameter(soup)
- get_between_lugs(soup)
- get_lug_to_lug(soup)
- get_case_thickness(soup)
- get_bezel_material(soup)
- get_bezel_color(soup)
- get_case_Glass(soup)
- get_case_Water_resistance(soup)
- get_weight(soup)
- get_dial_color(soup)
- get_numerals(soup)
- get_Strap_bracelet_material(soup)
- get_Strap_bracelet_color(soup)
- get_Strap_clasp_type(soup)
- get_movement(soup)
- get_movement_caliber(soup)
- get_movement_power_reserve(soup)
- get_frequency(soup)
- get_jewels(soup)
- get_movement_Functions(soup)
- get_description(soup)
- get_short_description(soup)
## Data Visualization
The script also includes data visualization using Seaborn and Matplotlib. The following visualizations are created:
### Watch Prices Histogram

```bash
sns.histplot(louiserard_df['price'], bins=20, kde=True, color='Blue')
plt.title('Watch Prices')
plt.xlabel('Price')
plt.ylabel('Count of Price')
```

```bash
sns.histplot(louiserard_df['price'], bins=20, kde=True, color='Blue')
plt.title('Watch Prices')
plt.xlabel('Price')
plt.ylabel('Count of Price')
```
### Watch Power Reserve Histogram

```bash
sns.histplot(louiserard_df['power_reserve'], bins=1, kde=True, color='lightblue')
plt.title('Watch Power Reserve')
plt.xlabel('Power Reserve')
plt.ylabel('Number of Watches')
```
![Watch Power Reserve Histogram](https://github.com/Anqa-H/MyProjects/assets/80011409/f233058c-7e22-4836-b566-57fcabbf0d4c)

### Watch Case Material Pie Chart
```bash
case_material_counts = louiserard_df['case_material'].value_counts()
plt.pie(case_material_counts.values, labels=case_material_counts.index, autopct='%1.1f%%', colors=color)
plt.title('Watch Case Material')

```
![case_material_counts](https://github.com/Anqa-H/MyProjects/assets/80011409/8f82605d-4051-4b9e-a614-51e33c1a10a0)


### Watch Diameter Doughnut Chart
```bash
diameter_counts = louiserard_df['diameter'].value_counts()
plt.pie(diameter_counts.values, labels=diameter_counts.index, autopct='%1.1f%%', colors=blue_colors, wedgeprops={'edgecolor': 'white', 'linewidth': 2}, startangle=20)
center_circle = plt.Circle((0, 0), 0.5, color='white')
fig = plt.gcf()
fig.gca().add_artist(center_circle)
plt.title('Watch Diameter')
```

![diameter_counts](https://github.com/Anqa-H/MyProjects/assets/80011409/2cb2ff85-e006-48a2-bc75-da99c66c7fbf)

