# Optimal-ROute: Bengaluru Smart Traffic Router

A Streamlit app that finds a faster driving route between two places in Bengaluru by taking traffic into account. Built by team Mango Mavericks for the Google Solution Challenge.

## How it works

1. **Road network:** OSMnx downloads the Bengaluru driving network as a graph.
2. **Traffic:** live traffic data from the TomTom API is added to the road segments. Where there is no data, a default speed of 30 km/h is used.
3. **Weights:** each road gets a weight based on its type (motorway, primary, residential, …), multiplied by 1.5 during rush hours (8–9 am and 5–7 pm).
4. **Route:** NetworkX finds the shortest path by these weights, and Folium draws it on a map.
5. **Extras:** Gemini writes a short text analysis of the route. There is also an emergency-vehicle alert button. It only shows the alert message in the app; it does not send a real SMS.

`data_generation.py` creates `synthetic_traffic_data.csv`, a synthetic traffic dataset used in the experiments.

## Results

[TODO: add a screenshot of the map and an example of time saved on one route]

## How to run

The app needs a TomTom API key and a Gemini API key. [TODO: read both keys from environment variables instead of writing them in `app.py`]

```bash
pip install -r requirements.txt
streamlit run app.py
```
