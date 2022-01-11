---
description: Improvements and Design Choices
---

# 💭 Design Considerations

Talk about why this solution was chosen over any other hypothesized solution.

Example from Census Explorer:

## Design Choices

React and Leaflet were used in this project to display the choropleth. We looked into using other options, like Dash in Python, as well as using SVG to display the map. From testing, Leaflet proved to be the best option for balancing performance with a good user interface.

AWS Glue was initally used as part of the ETL, but it was found to be much simpler to use a Step Function, as the ETL only needed to be run once, and it fulfilled the use case just as well.

## Recommendations for Further Improvement

These are features that are recommended to be included in a production-ready version of this solution.

- Making the platform available in both official languages: English and French.
- Ability to save selections / queries, so that the user can return to previous queries
- Allow the user to select combinations of variables to filter and search the information. For example: FSA, age and income; FSA, income and language; sex, age and language.
- To improve performance, have the FSAs join together as the user zooms out of the heatmap, drawing fewer shapes.
- Add a “super-user” mode, in which users can input their own queries into a command line interface.
- Include more data sets that can fulfill multiple User Stories.
- The ability for users to input their own data to compare it with the datasets of the platform.
- The ability to create charitable profiles for recommendations.
- Implement Amazon DynamoDB cache in case the application reaches hundreds of thousands of users to reduce the Amazon DynamoDB Read costs.
