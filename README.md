# federated_gnns_project
final project for ee 381k machine learning on real work networks



client- 100 nodes with most connections
random subset of cora due nexthe t week 

need to correlate the clienttothe datasets

identify top most connected from cora similar to client one and take their subgraphs 

client graph fixed:
get avg degree, path length, avg path length, maximum path length
Degree distribution plot

Cora:
- fix seed 42
- select top 100 subgraphs and put avg over all clients 
- star like but connect neighbors if included in A 
- avgdegree for each subgraph, plot distribution
- distriution of degrees per client
- matrix to show howmany nodes are overlapping (between A and C) normalized by the number of nodes from all clients 
- degree and client distribution

synchronous communication routes (A shares data with B, etc)
train and then share data
fine tune with data from neighbors
have a unique story
training clients and aggregating models 
Compare against idealized (fully connected client and subset (read up on paper))