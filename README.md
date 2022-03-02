# Getting started with the Amsterdam Transit Network

## Install
`conda env create --file environment.yml`

## Run
`python main.py`

## Extracting Socio-economic Status data per Neigbhorhood
1. Read the excel file `nl_fig = pd.read_excel('./input/nb_main_figures.xls')`
2. Keep only Amsterdam Neigbhorhoods `ams_fig = nl_fig[np.isin(nl_fig['gwb_code_10'], ams_nb['BU_CODE'].unique())]`
3. Join with the amsterdam neigbhorhoods dataframe `ams_nb = pd.merge(ams_nb, ams_fig, on='BU_CODE', how='left')`
