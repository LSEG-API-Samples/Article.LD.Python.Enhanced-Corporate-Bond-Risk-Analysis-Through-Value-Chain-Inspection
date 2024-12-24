## Enhanced Corporate Bond Risk Analysis Through Value Chain Inspection

### AUTHOR: Luke Perry
Traditional corporate bond selection strategies frequently rely on credit ratings to assess issuer risk. While these ratings provide a useful benchmark for evaluating creditworthiness, they may not adequately capture interconnected risks arising from supply chain dependencies. This analysis proposes a more nuanced risk management approach by integrating supply chain relationships into the evaluation process for corporate bond issuers.

By analyzing shared suppliers and potential bottlenecks within the value chain, investors can identify hidden risks that credit ratings might overlook. This method allows for improved diversification and risk mitigation within corporate bond portfolios by reducing exposure to systemic supply chain disruptions that could affect multiple issuers simultaneously.

The specific process we will be implmeneting in this notebook is to identify all value chain conflicts within a defined depth (suppliers, suppliers of suppliers etc).

To illustrate the real world effectiveness of this approach, we will use the [SPDR](https://www.morningstar.com/etfs/arcx/spbo/portfolio) corporate bond portfolio as our diversification candidate. This portfolio has been rated 3 stars by Morningstar, indicating it is "fairly valued."
