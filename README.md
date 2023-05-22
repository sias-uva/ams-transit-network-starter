# Getting started with the Amsterdam Transit Network

## Install
`conda env create --file environment.yml`

## Run
`python main.py`

## Extracting Socio-economic Status data per Neighbourhood
1. Read the excel file `nl_fig = pd.read_excel('./input/nb_main_figures.xls')`
2. Keep only Amsterdam Neigbhorhoods `ams_fig = nl_fig[np.isin(nl_fig['gwb_code_10'], ams_nb['BU_CODE'].unique())]`
3. Join with the amsterdam neigbhorhoods dataframe `ams_nb = pd.merge(ams_nb, ams_fig, on='BU_CODE', how='left')`

nb_main_figures_explainer.pdf is a guide for the labels of nb_main_figures. 
Some examples:
- a_inw: total number of inhabitants.
- a_hh: total number of households.
- p_hh_lkk: percentage of household with low income 
- p_hh_li: percentage of households with the lowest 20% income.
- a_w_all: nr of people with western migration background.
- a_nw_all: nr of people with non-western migration background.

![amsterdam transit network image](https://github.com/dimichai/ams-transit-network-starter/blob/main/amsterdam_transit_network.png)
