# Transportation
# Travelling Itineary Problem

import networkx as nx
import matplotlib.pyplot as plt
import itertools
import time
import pandas as pd
import copy

cities = pd.read_excel('city.xlsx')     
# sequence_travel = ['London', 'Paris', 'Berlin', 'Warsaw', 'Amsterdam', 'London'


def pre_defined_sequence_network():
    sequence_travel = []
    G = nx.MultiDiGraph()
    for i, nlrow in cities.iterrows():
        G.add_node(nlrow[0], attr_dict=nlrow[1:].to_dict())
        sequence_travel.append(nlrow[0])
    G.add_path(sequence_travel)

    # print("Sequence of Travel: ", sequence_travel)
    # print("Nodes in pre_defined_route (G): ", G.nodes())
    # print("Edges in pre_defined_route (G): ", G.edges())
    # nx.draw_circular(G, with_labels=True)
    # plt.show()
    
    return G
