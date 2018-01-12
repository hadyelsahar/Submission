# ArticlePlaceholder with Text

The baselines that were used are located in the `baselines` folder. Their respective results along with the results from our model are in the `results` folder.


The code contained in the `crowdevaluation` folder was made in order to prepare and evaluate the community evaluation. The languages are abbreviated with their respective language codes (ar for Arabic and eo for Esperanto).

- `Preparation` contains files that were used to create the surveys.
  - `Arabic` and `Esperanto` respectively contain:
    - `<languagecode>-final-file`: sample of generated summaries evaluated 
    - `<languagecode>-news-sentences.csv`: sentences of the news corpus
    - `<languagecode>-wikipedia-sentences.csv`: sentences from the original Wikipedia 
  - The `code` folder contains scripts to prepare the corpus according to the requirements of the survey. It contains a README how to use those scripts.
- `Results` contains the result files of the survey, after annonymization and cleaning 
- `evaluation-results` contains scripts that were used to process the results
  - `Arabic` and `Esperanto` respectively contain:
    - `Fluency` for processing the results of the Fluency and Appropriateness survey
      - `<languagecode>-quality.py` calculates scores for the quality in terms of fluency
      - `<languagecode>-approp.py` calculates scores for the quality in terms of fluency
    - `Editors` for processing the results of the Editors 

In the `Models` folder you will find all the necessary files to sample (i.e. beam-sample) from our trained models in both Arabic and Esperanto.

1. First you need to run the shell script located at: `Models/download_trained_models.sh` in order to download all the required trained models and post-processing files.
2. After you follow the instructions and install [Torch](http://torch.ch/) on your machine, run `Models/beam-sample.lua`.
3. Make sure that the following Python packages are installed: (i) `h5py`, (ii) `pandas`, and (iii) <`numpy` are installed.
3. Run `Models/beam-sample.py` in order to create a `.csv` file with the sampled summaries.

Please bare in mind that you need to have access to a GPU with at least 8 GB of memory in order to sample from the trained models. The experiments were conducted on a Titan X (Pascal) GPU. For all the possible sampling alterations, please check the comment sections of the above mentioned files.
