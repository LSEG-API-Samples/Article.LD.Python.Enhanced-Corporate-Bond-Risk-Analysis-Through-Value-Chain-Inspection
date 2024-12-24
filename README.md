## Enhanced Corporate Bond Risk Analysis Through Value Chain Inspection

### AUTHOR: Luke Perry
Traditional corporate bond selection strategies frequently rely on credit ratings to assess issuer risk. While these ratings provide a useful benchmark for evaluating creditworthiness, they may not adequately capture interconnected risks arising from supply chain dependencies. This analysis proposes a more nuanced risk management approach by integrating supply chain relationships into the evaluation process for corporate bond issuers.

By analyzing shared suppliers and potential bottlenecks within the value chain, investors can identify hidden risks that credit ratings might overlook. This method allows for improved diversification and risk mitigation within corporate bond portfolios by reducing exposure to systemic supply chain disruptions that could affect multiple issuers simultaneously.

The specific process we will be implmeneting in this notebook is to identify all value chain conflicts within a defined depth (suppliers, suppliers of suppliers etc) - these conflicts are then evalauted with the following risk formula.

$$
\text{risk\_for\_conflict}(\text{conflict}) = \sum_{\text{constituent} \in \text{conflict}} \left( P_{\text{default}}(\text{constituent}) \times 10 \cdot e^{-\text{depth}_{\text{constituent}}} \right)
$$

This formula is a simplified approach, evaluating risk by using depth as a proxy for risk attenuation scaled by the probability of default for the common supply chain ancestor. It assumes that greater distance from the ancestor default allows the chain to absorb defaults (represented in the exponential decay in the e term); however, it is worth noting that it is possible that the bullwhip effect actually exacerbates the risk implications. Additionally, this formula does not consider factors such as the availability of substitute suppliers or potential response times. The decision to omit these considerations stems from their unpredictable nature, which would likely require a considerable machine learning solution to estimate reasonably.

Overall portfolio risk is evaluated as the sum of risks from all conflicts:

$$
\text{risk\_for\_portfolio}(\text{portfolio}) = \sum_{\text{conflict} \in \text{portfolio}} \text{risk\_for\_conflict}(\text{conflict})
$$

To illustrate the real world effectiveness of this approach, we will use the [SPDR](https://www.morningstar.com/etfs/arcx/spbo/portfolio) corporate bond portfolio as our diversification candidate. This portfolio has been rated 3 stars by Morningstar, indicating it is "fairly valued."
