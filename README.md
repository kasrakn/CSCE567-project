# Final Project Writeup: Visualizing Global AI Tool Adoption

### **1. Midterm Proposal Outline Update**

This section includes the originally submitted Midterm Proposal outline, followed by a description of the changes made after its submission and in response to peer feedback.

**Project Proposal:** [`Kasra-Korminejad-project-proposal.pdf`](Kasra-Korminejad-project-proposal.pdf)

**Description of Changes:**

The project largely adheres to the original proposal, successfully creating all seven visualizations. The primary change made was in the choice of tools for implementation.

* **Original Plan:** The proposal outlined a hybrid approach using Python and Tableau, with Tableau specifically planned for the interactive map and treemap.
* **Final Implementation:** The final project was completed entirely within Python, using the `Plotly Express` library for the interactive map and treemap.
* **Reasoning for Change:** **This decision was driven by a practical limitation. As I do not have a Windows or Mac operating system, I had to use Tableau Cloud, which was only free for a two-week trial period. When the trial expired, I needed an alternative for the choropleth map and treemap visualizations. I discovered that the `Plotly Express` library in Python could provide all the necessary interactive functionalities with excellent quality, making the switch seamless and removing the dependency on Tableau.**

**Additionally, in response to peer feedback suggesting that "Plan A" might result in too many similar graphs, care was taken to ensure each of the seven visualizations tells a distinct part of the story.** The charts were sequenced to guide the user from a high-level geographic overview to more granular industry and demographic comparisons, ensuring minimal redundancy and that each visualization provided unique insights.

***

### **2. Summary / Visualization Access**

**The Story of Global AI Adoption**

This project tells the story of the rapid, yet uneven, global proliferation of Artificial Intelligence tools. Through a series of clear and interactive visualizations, it unveils the landscape of AI adoption, revealing key trends across geography, industry, and demographics. The visualizations guide the viewer from a high-level world map showing adoption hotspots to granular breakdowns that compare how different AI tools are being embraced by startups versus large enterprises, and by younger versus older professionals. The key finding is that while AI's reach is broad, its integration is highly specific, with certain tools dominating niche industries and specific age groups leading the charge in this technological revolution.

**Personal Impact and Takeaways**

**As suggested by a peer reviewer, this project has prompted a reflection on how these findings can be used personally. The visualized data highlights that proficiency with specific AI tools is becoming a key differentiator in high-adoption sectors like Technology and Finance. Going forward, this will change my educational focus to include deeper dives into the leading tools identified in these high-growth industries. In seeking paying jobs, I will now use this data to target companies and sectors that are at the forefront of AI integration, as they are more likely to value and invest in skills related to these emerging technologies.**

**Visualization Access and Interaction**

To view and interact with the visualizations, the user needs to run the provided `project.ipynb` Jupyter Notebook locally. The notebook requires the `ai_adoption_dataset.csv` file to be in the same directory. The following Python libraries must be installed, which can be done using pip:

```bash
pip install pandas plotly seaborn matplotlib
```

The notebook is designed to be run sequentially. The bar charts are static, while the choropleth map and treemap are interactive, allowing users to hover for details, zoom, pan, and click to explore the data hierarchy.

### **3. Challenges Encountered and Addressed**

The primary technical challenge in this project was creating compelling, interactive visualizations without relying on Tableau, as was initially planned. The original proposal identified the choropleth map and treemap as ideal candidates for Tableau because of its powerful built-in tools for these chart types. Replicating this functionality solely in Python required research into the appropriate libraries. The `Plotly Express` library was chosen as the solution, as it offers a high-level API for creating these complex, interactive charts with minimal code. A secondary challenge was ensuring the grouped bar charts (e.g., "Adoption Rate by Industry and AI Tool") remained readable and not overly cluttered. This was addressed by using a wider figure size, rotating the x-axis labels for clarity, and selecting a color palette designed for distinguishing categorical data effectively.

***

### **4. Design Decisions**

Several design choices were made to ensure the visualizations told a clear and cohesive story.

* **Choice of Environment:**
    * **The entire project was developed within a Python Jupyter Notebook.**
    * **Reason: Jupyter Notebook is a handy environment, especially for data scientists, as it allows for the gathering of code, results, visualizations, and textual context all in one place. This makes it more comfortable and efficient to have all the necessary components together, creating a clear and reproducible narrative.**

* **Global Adoption Visualization:**
    * **Choice:** A **choropleth map** was used to show the geographic distribution of AI adoption rates.
    * **Reason:** It is the most intuitive way to display geographic density data, allowing for immediate identification of regional trends.
    * **Alternative:** A **bubble map** was considered but rejected because it would show total user numbers, which is less effective than adoption *rate* for comparing national integration levels across countries with different populations.

* **Hierarchical Data (DAU by Industry/Tool):**
    * **Choice:** A **treemap** was selected to visualize the breakdown of Daily Active Users.
    * **Reason:** This chart is excellent for showing part-to-whole relationships in hierarchical data.
    * **Alternative:** A **sunburst chart** was an option but was not chosen because comparing the area of rectangular segments is often more direct than comparing angular slices.

* **Categorical Comparisons:**
    * **Choice:** **Grouped bar charts** were used to compare adoption rates across categories like age and company size.
    * **Reason:** This allows for direct, side-by-side comparison of different segments.
    * **Alternative:** A **line chart showing the adoption rate of AI across different countries**, as suggested by a peer reviewer, was considered. While this would be excellent for showing trends over a longer period, it was decided against for this project because the two-year time span in the data would result in very short trend lines. The choropleth map was prioritized to better tell the story of current geographic disparity in a single view.

* **Interactivity and Color:**
    * **Choice:** Interactivity was focused on **hover-for-detail tooltips**, which allow for data exploration without cluttering the initial view.
    * **Reason:** This provides depth without overwhelming the user. Purposeful color palettes were chosen to distinguish categories clearly without implying a false order or trend.

***

### **5. Discussion of Future Work**

While the current project provides a robust snapshot of AI adoption, several future enhancements could provide deeper, more dynamic insights, focusing primarily on expanding the visualization possibilities. The following ideas describe how additional data could be collected and used to create new visualizations that further engage the intended audience.

* **Longitudinal Trend Analysis and Animated Visualizations:** The current dataset spans two years, which is excellent for a snapshot comparison but limits true trend analysis. A valuable next step would be to collect similar data for subsequent years (e.g., 2025, 2026). This additional data would enable the creation of new visualizations:
    *A **series of line charts** could track the adoption rate growth over time for specific countries or industries, revealing who the early adopters are and which markets are reaching maturity.
    *An **animated choropleth map** could be developed to show the geographic spread and intensification of AI tool adoption year-over-year, providing a more dynamic and compelling story of global integration than the current static map.

* **Feature-Based Comparative Visualizations:** To better understand *why* certain tools are adopted more than others, the dataset could be augmented with specific attributes for each AI tool, such as its primary function (e.g., 'Text Generation', 'Image Creation', 'Code Assistant') and a user-friendliness score. This would allow for more sophisticated visualizations:
  * A **scatter plot** could be created to map `Adoption Rate` against a `User-Friendliness Score`, with points colored by the tool's primary function. This could reveal key insights, such as whether ease-of-use is a greater driver of adoption for image-generation tools compared to coding assistants. 
    * A **parallel coordinates plot** could also be used to compare multiple tools across several features at once (Adoption Rate, Daily Users, User-Friendliness), helping to identify the distinct profiles of the most successful AI applications.


## How to Run the Project
The project is designed to be run in a Jupyter Notebook environment. Here are the steps to get started:

1. **Clone the Repository:**
   Clone the repository to your local machine using:
   ```bash
   git clone https://github.com/kasrakn/CSCE567-project.git
   ```

2. **Navigate to the Project Directory:**
   Change into the project directory:
   ```bash
   cd CSCE567-project
   ```

3. **Install Required Libraries:**
   Ensure you have the necessary Python libraries installed. You can install them using pip:
   ```bash
   pip install -r requirements.txt
   ```

4. **Open the Jupyter Notebook:**
   - Launch Jupyter Notebook `project.ipynb`:
   - Run all the cells in the notebook sequentially to generate the visualizations.