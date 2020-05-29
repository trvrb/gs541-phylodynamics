# GENOME 541 Introduction to Computational Molecular Biology

## Day 1

Motivation: we can learn about outbreaks by sequencing infecting pathogens.

[Introduction: Phylodynamics and application to SARS-CoV-2](http://bedford.io/projects/gs541-phylodynamics/phylodynamics.html)

[Lecture 1: Molecular clocks and the coalescent](http://bedford.io/projects/gs541-phylodynamics/coalescent.html)

## Day 2

[Lecture 2: Discrete traits and phylogeography](http://bedford.io/projects/gs541-phylodynamics/phylogeography.html)

## Homework

This homework will focus on using [Nextstrain](https://nextstrain.org/) to infer global phylogeography of SARS-CoV-2.

Start by installing Nextstrain by following these instructions: [https://nextstrain.org/docs/getting-started/quickstart](nextstrain.org/docs/getting-started/quickstart). Slightly confusingly, we have two ways to get software installed. If you can run Docker on your computer, the ["container-based" installation](https://nextstrain.org/docs/getting-started/container-installation) should be easier and is what's recommended by the quickstart. If Docker is giving you problems, you should try the ["local" installation](https://nextstrain.org/docs/getting-started/local-installation) that relies on Conda.

You should check that the installation is working by running the "Zika tutorial" described here with:
* [Downloading Zika tutorial repository](https://nextstrain.org/docs/getting-started/quickstart#download-the-nextstrainzika-tutorial-repository)
* [Running the build](https://nextstrain.org/docs/getting-started/quickstart#run-the-build)
* [Visualize build results](https://nextstrain.org/docs/getting-started/quickstart#visualize-build-results)

Once things are correctly installed, download the "ncov" repository here: [github.com/nextstrain/ncov](https://github.com/nextstrain/ncov). There is an example dataset in `example_data`. To get this in place run:
* `mkdir data`
* `cp example_data/* data/`
To make things run faster, open the file `config/config.yml` and change `sequences_per_group` under `filter` from `2000` to `10`.
Then, run the build with:
* `nextstrain build .` (container-based installation) or `snakemake -p` (local installation)
This will complete in ~10 minutes. You can then view results with:
* `nextstrain view auspice/` (container-based installation) or `auspice view --datasetDir auspice` (local installation)
Open a browser to http://127.0.0.1:4000 (container-based installation) or http://localhost:4000 (local installation) to view the results.

Next:
* Create a new GitHub public repository on your personal account titled `gs541-phylogeography`.
* Rename the file `auspice/ncov_global.json` generated above to `auspice/gs541-phylogeography.json` and commit to this repository.
* Doing so will make the link nextstrain.org/community/{your-github-username}/gs541-phylogeography display this Auspice file.

For the assignment, please upload:
1. A link to your GitHub repository for `gs541-phylogeography` and a link to your community Nextstrain page. _30 points_
2. A paragraph write-up that describes your interpretation of the transmission history from an individual country or state from nextstrain.org/ncov (your choice). You can filter to a specific state by clicking under "Filter by Admin Division" here: [nextstrain.org/ncov/north-america?c=division&r=division](https://nextstrain.org/ncov/north-america?c=division&r=division). For countries outside North America, I'd recommend using a region specific build:
* [Africa](https://nextstrain.org/ncov/africa)
* [Asia](https://nextstrain.org/ncov/asia)
* [Europe](https://nextstrain.org/ncov/europe)
* [Oceania](https://nextstrain.org/ncov/oceania?c=division&r=division)
* [South America](https://nextstrain.org/ncov/south-america)
You can filter to a specific country by clicking under "Filter by County". _30 points_
