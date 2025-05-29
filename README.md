# AI-Powered Analysis of Government GitHub Projects – Final Report
This project aimed to identify high-impact government-led open-source projects hosted on GitHub
that demonstrate potential for innovation, scalability, and positive societal outcomes. The goal was
to analyze a subset of repositories created by public sector organizations across multiple countries
and determine where investment, collaboration, or replication efforts should be directed. The
strategy relied on a mix of GitHub data mining, natural language processing (NLP), and large
language model (LLM) reasoning to extract insight from code repositories, particularly focusing on
README content, which typically provides the project's purpose and technical summary.
The first phase involved scraping data from a curated YAML list of GitHub accounts belonging to
governments around the world. This dataset, sourced from the governments.yml file on
GitHub, lists official public sector GitHub accounts from different countries. To reduce noise and
focus the analysis, a filtering mechanism was applied using a predefined list of key organizations
known for active and impactful technology development, such as GSA (USA), alphagov (UK),
canada-ca (Canada), and opengovsg (Singapore). For each selected GitHub user, a list of
public repositories was fetched using the GitHub REST API, and relevant metadata such as
repository name, description, number of stars, primary programming language, and README
contents was collected.
Once the data was gathered, the project focused on analyzing the README files using OpenAI’s
GPT-based models via the Azure OpenAI service. To interface with these models, the
AzureChatOpenAI wrapper from LangChain was used, configured with the proper
deployment credentials stored securely in a .env file. Each README was passed to the LLM
with prompts to perform two specific tasks: summarization and sentiment analysis. Summarization
aimed to condense the core purpose of each project into a short description, while sentiment
analysis assessed the tone and enthusiasm present in the README, indicating the author's
confidence and clarity of communication.
The summarized and sentiment-tagged data was compiled into a structured DataFrame using
pandas. This enabled further slicing of the data by country and organization to identify regional
trends. For instance, it became evident that Singapore’s opengovsg consistently released high-
quality civic technology tools, while the United States’ GSA focused more on foundational digital
infrastructure and security.
A particularly noteworthy discovery was the “AskGov” project developed by opengovsg.
AskGov is a conversational AI-powered Q&A platform that helps citizens find answers to public
service questions. It stood out due to its direct civic utility, open-source availability, and alignment
with global digital transformation goals. The sentiment analysis for this project was strongly
positive, and the project was implemented using scalable technologies like TypeScript and hosted
under a government-endorsed GitHub repository. Given these characteristics, AskGov was selected
as the top candidate for further investment or replication.
Finally, the results of the analysis were saved into multiple formats for downstream use, including
CSV and JSON files that store the enriched repository data, along with files that detail sentiment
trends by country and organization. These outputs ensure transparency and reusability for
stakeholders interested in cross-border civic tech collaboration.
In summary, this project successfully combined automated scraping, cloud-based LLM analysis,
and data science workflows to produce actionable insights into global government-led open-source
projects. The selection of AskGov as a strategic investment opportunity reflects a data-informed
approach to identifying scalable and impactful civic technology. This methodology can be expanded
in future work to include issue tracking, contributor behavior, and real-time project activity to refine
investment decisions further.
