# IPL-Trivia

Data visualisation of Indian Premere League for 2008-2016 with [kaggle dataset](https://www.kaggle.com/harsha547/indian-premier-league-csv-dataset)

# Live

View the web app [here](https://gifted-jang-4e2d88.netlify.app/) 

## Libraries/frameworks used

- `vuejs`: Vue Js is used as the main frontend framework. The app is built using the vue-cli tool that gives you the option to customize the plugins while bootstraping the project.

- `chota`: Chota is used instead of bootstrap because it's a micro CSS framework (~3kb) which is even smaller than bootstrap.

- `chartjs`: ChartJs is very minimal JavaScript library for producing chartjs.

- `vue-chartjs`: It is just a small wrapper around chartjs just to make you talk to chartjs in a very smooth manner.

## Data Cleaning and Analysis

- Data cleaning is done using `Google Collab` interactive cloud platform with the help of `Pandas`. Processed data is exported to JSON file via google drive which is then downloaded and used in the prject as a data source.
- You can find the analysis [here](https://colab.research.google.com/drive/1PenxDsS8lI7w4mKQywFvOhD3t2Z5qdBR?usp=sharing)

## Features

- Created in VueJS

- Mobile responsive

- It is a progressive web-app

- It works offline

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
