
# Overview sCT

Repository to collect all the references on generation of synthetic computed tomography (sCT) with deep learning/convolutional networks. Generated from Spadea MF, Maspero M et al Med. Phys. 2021 (submitted). The preprint is available at: [http://arxiv.org/abs/2102.02734](http://arxiv.org/abs/2102.02734)

**The site is just a placeholder that will be finally released upon acceptance**

## License
[![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa] 

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

In short, this means that anyone, even a commercial entity may re-use the content of this page as long as it will cite our paper and the source.

## Contributors

Maspero M is the owner administrator of the project. Spadea Maria Francesca and Paolo Zaffino greatyl contributed to the data collection for the pubication.

The following added content: ...

## Make the table sortable

If you wish to extend the interaction with the tables, you can sort the columns in your favourite browser, as described [here](https://github.com/Mottie/GitHub-userscripts/wiki/GitHub-sort-content). We have tested on Chrome the following combination:
* install [Tampermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo/related);
* install [Github Sort Content](https://greasyfork.org/en/scripts/21373-github-sort-content);

## If you see any typos/mistakes

Ok, we did our best, but you got us! That can happen, but you can contribute to the accuracy of the information in this page by proposing a commit, after having forked this repository. Matteo will keep monitored the repository and updated every two months.
If you wish to see some changes, just reach out: we are human, so w

## MRI without dose evaluation

This is just an example of how one of the table will look like:

| Tumour site   | train | val | test | x-fold | field [T] | sequence | conf | arch | pair reg | MAE [HU] | PSNR [dB] | SSIM | others |  reference    | pub date |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
Brain	|	18	|		|		|	6x	|	1.5 |	3D T1 GRE		|	2D	|	U-net		|	rig	|	85±17	|		|		|	MSE ME	| [Han2017](https://doi.org/10.1002/mp.12155)	| 2017-02-13 |
Brain <br>Prostate	|	16<br>22	|		|		|	LoO	|	n.a.	|	T1	|	2.5D patch	|		CNN+ 	|	rig	|	85±9<br>43±2	|	27.3±1.1<br>33.5±0.8	|		| | [Xiang2018](https://doi.org/10.1016/j.media.2018.03.011)	| 2018-03-30   
Brain	|	15	|		|		|	x5	|	1.0	|	T1 Gd	|	2D	|		GAN<sup>\*</sup> 	|	def	|	89±10	|	26.6±1.2	|	.83±.03	| tissues | [Emami2018](https://doi.org/10.1002/mp.13047)	| 2018-06-14    
