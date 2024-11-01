# PageRank Implementation
Data Mining Project

This project aims to implement and analyze the PageRank algorithm. PageRank is a metric developed by Google founders Larry Page and Sergey Brin that ranks web pages based on the quantity and quality of links pointing to them. In this implementation, a code skeleton has been provided to compute PageRank, and users must implement the algorithm according to the given instructions.

## Datasets
The dataset provided with the project is called `gr0.California` and contains a graph of all websites related to the "California" search query. The dataset format is as follows:

* Lines starting with `n`: Define a node in the graph. Example: `n ID URL` where ID is a unique identifier for the node and URL is the webpage URL.
* Lines starting with `e`: Define an edge in the graph. Example: `e IDFROM IDTO` where IDFROM is the identifier of the source page and IDTO is the identifier of the destination page.

## Example Execution
To run the program with the provided dataset, use the following command:

```bash
python3 pagerank.py gr0.California.txt [--beta 0.85]
```

Where beta is the damping parameter. The default value (if not provided) is 0.85.

After executing the program, it will print the list of web pages ordered by their PageRank. It will also show the time taken for the algorithm to converge.

## Results Analysis
The implemented PageRank algorithm provides fast and accurate results, with surprisingly quick convergence for a dataset of 10,000 web pages, requiring less than 0.03 seconds to reach a solution. This efficiency highlights not only the power of the PageRank algorithm but also the quality of the implementation.

One of the central parameters of the PageRank algorithm is the damping factor, β. This parameter, which takes values between 0 and 1, represents the probability that a user continues following links within a webpage, rather than jumping to a random page. In fact, (1-β) is the probability that the user makes this random "jump".

In our implementation, β can be adjusted to see how it affects the final PageRank results. Key points about β include:

* Influence on Convergence: A higher β value can make the algorithm take longer to converge. This is because with a high β, the algorithm gives more weight to existing links, making PageRank scores distribute more slowly.
* Relevance vs. Randomness: With a high β, PageRank results are more influenced by existing links in the dataset, resulting in scores more based on web "reputation". Conversely, with a lower β, there's a higher probability of jumping to random pages, which can cause pages with fewer incoming links to obtain higher PageRank scores.
* Extreme Values: With β = 1, the user will always follow links and never make random jumps, which may not be realistic. With β = 0, the user will always jump randomly, completely ignoring the web's link structure.

After analyzing various β values, it's clear that the appropriate selection of this parameter can have a significant impact on the interpretation and application of PageRank results. Choosing a suitable β value is essential to ensure that the ranking produced by PageRank accurately reflects the real importance and relevance of web pages. Generally, a β value between 0.8 and 0.9 produces satisfactory results.
