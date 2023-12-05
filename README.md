# federated_gnns_project


## requirements for running files:
appnope==0.1.3 <br/>
asttokens==2.4.0<br/>
backcall==0.2.0<br/>
certifi==2023.7.22<br/>
charset-normalizer==3.3.0<br/>
comm==0.1.4<br/>
contourpy==1.1.1<br/>
cycler==0.12.0<br/>
debugpy==1.8.0<br/>
decorator==5.1.1<br/>
exceptiongroup==1.1.3<br/>
executing==2.0.0<br/>
filelock==3.12.4<br/>
fonttools==4.43.0<br/>
idna==3.4<br/>
ipykernel==6.25.2<br/>
ipython==8.16.1<br/>
jedi==0.19.1<br/>
Jinja2==3.1.2<br/>
joblib==1.3.2<br/>
jupyter_client==8.3.1<br/>
jupyter_core==5.3.2<br/>
kiwisolver==1.4.5<br/>
MarkupSafe==2.1.3<br/>
matplotlib==3.8.0<br/>
matplotlib-inline==0.1.6<br/>
mpmath==1.3.0<br/>
nest-asyncio==1.5.8<br/>
networkx==3.1<br/>
numpy==1.26.0<br/>
opacus==1.4.0<br/>
opt-einsum==3.3.0<br/>
packaging==23.2<br/>
pandas==2.1.1<br/>
parso==0.8.3<br/>
pexpect==4.8.0<br/>
pickleshare==0.7.5<br/>
Pillow==10.0.1<br/>
platformdirs==3.11.0<br/>
prompt-toolkit==3.0.39<br/>
psutil==5.9.5<br/>
ptyprocess==0.7.0<br/>
pure-eval==0.2.2<br/>
Pygments==2.16.1<br/>
pyparsing==3.1.1<br/>
python-dateutil==2.8.2<br/>
pytz==2023.3.post1<br/>
pyzmq==25.1.1<br/>
requests==2.31.0<br/>
scikit-learn==1.3.1<br/>
scipy==1.11.3<br/>
seaborn==0.13.0<br/>
six==1.16.0<br/>
stack-data==0.6.3<br/>
sympy==1.12<br/>
threadpoolctl==3.2.0<br/>
torch==2.0.1<br/>
torch-cluster==1.6.2<br/>
torch-geometric==2.3.1<br/>
torch-scatter==2.1.2<br/>
torch-sparse==0.6.18<br/>
torch-spline-conv==1.2.2<br/>
tornado==6.3.3<br/>
tqdm==4.66.1<br/>
traitlets==5.10.1<br/>
typing_extensions==4.8.0<br/>
tzdata==2023.3<br/>
urllib3==2.0.6<br/>
wcwidth==0.2.8<br/>



## files
1. ### client_network.ipynb

- Shows different methods for building the client network from the SNAP facebook dataset, ultimtely choosing method 3 (selecting the top 100 nodes with the highest node degree). 
- Plots the network and degree distribution graphs

2. ### facebook_data
- SNAP facebook dataset downloaded from online
 
3. ### data
- Cora dataset used for creating client subgraphs

4. ### cora_dataset.ipynb
- Creates the training and test set from the Cora dataset
- Creates the subgraphs of firdt/second order neighbors for each client node using the cora dataset (training set) and plots the subgraphs and their degree distributions
- Creates the test set using the nodes not present in the subgraphs and calculates different metrics for the test set
- Saves these graphs into files

5. ### client_subgraphs
- The subgraphs of each client node that only contained first order neighbors, resulting in smaller subgraphs. This was not used in our final results

6. ### second_order_client_neighbors
- The subgraphs of each client node that contained both the first and second order neighbors, resulting in larger subgraphs. These ended up being the final subgraphs used 

7. ### client_network.pickle
- Pickle file which stores the client network

8. ### new_facebook_network.gml
- Gml file which stores the client network

9. ### test_graph.gml
- The test graph for when only first order neighbors were used for subgraphs, which ended up not being used

10. ### second_order_test_graph.gml
- The final test graph that we used, which was when we created subgraphs of first and second order neuighbors

11. ### training_subgrph_gnns.ipynb
- The file where most of the training occurred
- Built GCN, GAT, and Differential Privacy models
- Contains functions for training and testing each model, as well as implementing both broadcast and gossip communication protocols between client nodes
- Contains different aggregation methods for sharing model parameters
- Contains training and testing on a fully connected decentralized graph as well as a centralized graph from the entire Cora dataset (to serve as benchmarks)
- Tested using different batch sizes and varying parameters 
- Tested using differential privacy model 
