BibleStudy
===

A simple mini-pipeline to generate biblical articles based on keywords by chatGPT APIs, and render the results with a Latex template.

Prerequisites
--

1. Need to have a [openAI](https://openai.com) token

2. OpenAI support a wide range of Python version from 2.7 to 3.11+, this script is tested with Python 3.10.11.
More details about how to install Python can be found from [Python Site](https://www.python.org/downloads/).

Setup Steps
--

1. Setup Python dev environment

`$ pip install -r requirements.txt`

Depends on yor network, the installation can be completed within 30 seconds.

2. Setup the openAI token

Setup one environment variable `OPENAI_API_KEY = YOUR_OPENAI_TOEN`.

You can verify the variable by call bellow Python code:
`os.getenv("OPENAI_API_KEY")`


It is crucial to consistently safeguard your openAI token. In the event of any inadvertent disclosure, it is imperative to promptly reset your token within the openAI user console. 

3. Run the script

`cd` to root of your project folder, run command :

`python BiblicalStuday.py`

4. Print out to pdf

After run the python script, the output from chatPGT will be generated in a file in root folder `biblical_article_rendered.tex`.

* If you already installed the [Latex]() in your local, you can use Python package [pdflatex](https://pypi.org/project/pdflatex/) convert the Latex to pdf automatically.

* Otherwise can use [Overleaf](https://www.overleaf.com/) to convert it manually. 

Use it Wisely
-
The purpose of this tool is to offer a convenient and efficient method for searching the Bible using specific keywords of interest. However, it is important to understand that it does not serve as a substitute for your current in-person Bible study groups. Therefore, it is advised to utilize this tool wisely and exercise caution by carefully and prudently reviewing the output, as the AI's reasoning and inferencing capabilities are still in the early stages. 


Notes
===

**Used prompts**

|Type | Prompt |
|----|----|
|Word List | "Please generate a Latex formatted table for these words: " + word_list_str + ", including three columns, 'word', 'meaning', 'word root and meaning' in latex format with width ratio 0.3, 0.4 and 0.3 respectively. table's row and cell should have separator lines. Please only return the Latex content, nothing else."|
|Article | "now you are biblical article writer for Sunday message, please use all these words: " + word_list_str + ", write one article within 500 words. This article should include all these words and quote bible NIV verses as more as possible. Make sure the content is safe for youth. Please include a title at the beginning, bold it, no other content except the title and content. Please list all the bible verses at the end of the article with bible version.  Article should NOT include any URL."|


The generated contents of this script are retrieved by utilizing the openAI API, and it is important to note that they may potentially contain inaccurate information. This script is specifically designed for educational purposes only. Furthermore, the prompts used in this script are subject to modification for any given reason.
Due to the utilization of the openAI API in this script, there is a associated cost for each execution, approximately amounting to $0.1 cent per run.
