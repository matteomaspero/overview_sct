# Overview sCT

Repository to collect all the references on generation of synthetic computed tomography (sCT) with deep learning/convolutional networks. Generated from Spadea MF & Maspero M et al. Med. Phys. 2021 (in press), [https://doi.org/10.1002/mp.15150](https://doi.org/10.1002/mp.15150), preprint at: [http://arxiv.org/abs/2102.02734](http://arxiv.org/abs/2102.02734). This page is available at: [https://matteomaspero.github.io/overview_sct/](https://matteomaspero.github.io/overview_sct/) and its Github repository is: [https://github.com/matteomaspero/overview_sct/](https://github.com/matteomaspero/overview_sct/).

**By the end of 2021 the table will be updated, so far all the paper up to Jan 2021 should be included, if not; please, feel free to contribute!**

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

Maspero M is the owner administrator of the project. Spadea Maria Francesca and Paolo Zaffino greatly contributed to the data collection for the publication.

The following added content: ...

## Make the table sortable

If you wish to extend the interaction with the tables, you can sort the columns in your favourite browser, as described [here](https://github.com/Mottie/GitHub-userscripts/wiki/GitHub-sort-content). We have tested on Chrome the following combination:
* install [Tampermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo/related);
* install [Github Sort Content](https://greasyfork.org/en/scripts/21373-github-sort-content);

## If you see any typos/mistakes

Ok, we did our best, but you got us! That can happen, but you can contribute to the accuracy of the information in this page by proposing a commit, after having forked this repository. Matteo will keep monitored the repository and update it every two months.
If you wish to see some changes, just reach out; we are more than happy to hear your comments/suggestions.

## MRI without dose evaluation

| Tumour site   | train | val | test | x-fold | field [T] | sequence | conf | arch | Reg | MAE [HU] | PSNR [dB] | SSIM | others |  reference    | pub date |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
Abdomen |	10<sup>v</sup>	|		|	10	|	LoO	|		|	mDixon |	2D pair	|	GAN<sup>\*</sup> |	def	|	61±3	|		|		|	CC |  [Xu2019](https://doi.org/10.1109/ACCESS.2019.2951924) | 2019-11-06 |
Abdomen |	160	|		|		|	 LoO |	n.a.	|	n.a.	|	2D pair	|	GAN<sup>\*</sup>	|	rig	|	 5.1±0.5	|		|	.90±.43	|  (F/M)SIM IS ...	| [Xu2020](https://doi.org/10.1016/j.neunet.2020.05.001) | 2020-05-08 |
Brain	|	18	|		|		|	6x	|	1.5 |	3D T1 GRE		|	2D	pair |	U-net		|	rig	|	85±17	|		|		|	MSE ME	| [Han2017](https://doi.org/10.1002/mp.12155)	| 2017-02-13 |
Brain |	16	|		|		|	LoO	|	n.a.	|	T1	|	2.5Dp patch	|		CNN+ 	|	rig	|	85±9	|	27.3±1.1	|		| | [Xiang2018](https://doi.org/10.1016/j.media.2018.03.011)	| 2018-03-30 |  
Brain	|	15	|		|		|	x5	|	1.0	|	T1 Gd	|	2D pair	|		GAN<sup>\*</sup> 	|	def	|	89±10	|	26.6±1.2	|	.83±.03	| tissues | [Emami2018](https://doi.org/10.1002/mp.13047)	| 2018-06-14  |
Brain	|	98CT<br>84MR 	|		|	10	|		|	3	|	3D T2	|	2D pair/unp |		GAN	|	aff	|	19±3	|	65.4±0.9	|	.25±.01	|		| [Jin2019](https://doi.org/10.3390/s19102361) | 2019-05-22 |
Brain 	|	24	|		|		|	LoO	|	n.a.	|	T1  |	3Dp pair	|	GAN	|	rig	|	56±9	|	26.6±2.3	|		|	NCC, HD body	|  [Lei2019](https://doi.org/10.1002/mp.13617) | 2019-05-21 |
Brain	|	33<br>160	|		|		|	LoO	|	n.a.<br>n.a.	|	T1<sup>b</sup><br>n.a.	|	2D	|	GAN	|	yes<br>no	|	9.0±0.8<br> 5.1±0.5	|		|	.75±0.77<br>.90±.43	| FSIM MSIM IS SWD FID experts	| [Xu2020](https://doi.org/10.1016/j.neunet.2020.05.001) | 2020-05-08 |
Brain	|	28<sup>t</sup>	|	2	|	15 |		|	1.5	|	n.a.	|	2D	|	GAN<sup>\*</sup>		|	aff	|	134±12 | 24.0±0.9	| .76±.02	|		|  [Yang2020](https://doi.org/10.1109/tmi.2020.3015379) | 2020-11-30 |
Brain	|	28	|		|	6	|		|	1.5	|	T2	|	2D pair <br> 2D unp	|	U-net<br> GAN	| rig |	65±4<br>94±6	|	28.8±0.6<br> 26.3±0.6	| .972±.004<br>.955±0.007	| same metrics for synth MRI |[Li2020](https://doi.org/10.1155/2020/5193707) | 2020-11-05|
Brain	|	81	|		|	11	|	8x	|	1.5	|	3D T1 GRE<br> 3D T1 GRE Gd<br>2D T2 SE<br>2D T2 FLAIR 	|	2D	|	U-net 	|	aff |  45.4±8.5<br>44.6±7.4 <br>45.7±8.8 <br>51.2±4.5 | 43.0±2.0<br>43.4±1.2 <br>43.4±1.2 <br>44.9±1.2	| .65±.05<br>.63±.03 <br> .64±.03<br>.61±.04	|	metrics for air bone, soft tissue, DSC bones	|  [Massa2020](https://doi.org/10.1088/1361-6560/abc5cb) | 2020-11-27|
H&N	|	23	|		|	10	|		|	1.5|	T2	|	2D pair	|	U-net	|	def	|	131±24	|		|		|	MAE, ME soft tis./bone | [Wang2019](https://doi.org/10.3389/fonc.2019.01333) | 2019-11-29|
H&N	|	28	|	4	|		|	8x	|	1.5	|	2D T1±Gd, T2	|	2D pair	|	GAN	|	aff	|	75.7±14.6	|	29.1±1.6	|	.92±.02	|	DSC, MAE on bone	|  [Tie2020](https://doi.org/10.1002/mp.14062)|2020-02-03 |
H&N	|	60			|	30	|		|	3	|	T1	|	2D	unp |	GAN	|	n.a.	|	19.6±0.7	|	62.4±0.5	|	.78±0.2	|		| | [Kearney2020](https://doi.org/10.1148/ryai.2020190027) | 2020-03-25 |
H&N	|	7	|		|	8	|	LoO	|	1.5	|	3D T1, T2	|	2D pair|		GAN	|	def	|	83±49	|		|		|	ME	|	[Largent2020](https://doi.org/10.1016/j.canrad.2020.01.008)| 2020-03-14 |
H&N	|	10	|		|		|	LoO	|	1.5	|	3D T1, T2	|	2D	pair|	GAN<sup>\*</sup>	|	def	|	42-62	|		|		|	RMSE, CC	|  [Qian2020](https://doi.org/10.1007/s10723-020-09513-3) | 2020-03-10 |
H&N	|	32	|		|	8	|	5x	|	3	|	3D UTE	|	2D pair	|	U-net	|	def	|	104±21	|		|		|	DSC, spatial corr	|  [Su2020](https://doi.org/10.3174/ajnr.A6758) | 2020-10-06 |
Prostate	|	16<br>22	|		|		|	LoO	|	n.a.	|	T1	|	2.5Dp pair	|		CNN+ 	|	rig	|	85±9<br>43±2	|	27.3±1.1<br>33.5±0.8	|		| | [Xiang2018](https://doi.org/10.1016/j.media.2018.03.011)	| 2018-03-30 
Pelvis	|	20	|		|		|	LoO	|	n.a.	|	3D T2  |	3Dp pair	|	GAN<sup>\*</sup>	|	rig	|	51±16	|	24.5±2.6	|		|	NCC, Hausdorff on body	|  [Lei2019](https://doi.org/10.1002/mp.13617) | 2019-05-21 |
Prostate	|	20	|		|		|	5x	|	1.5	|	2D T1 TSE	|	2D pair<br>3D p pair	|		U-net	|	def	|	41±5<br>38±5	|		|		|	DSC bone 	| [Fu2019](https://doi.org/10.1002/mp.13672)| 2019-06-20 |
Pelvis human <br> Pelvis canine	|	27<br>18	|		|		|	3x	|	3<br>1.5	|	3D T1 GRE mDixon 	|	3Dp pair	|		U-net	|	def	|	32±8	|	36.5±1.6	|		|	MAE/DSC bone surf dist<0.5 mm |  [Florkow2019](https://doi.org/10.1002/mrm.28008) | 2019-10-08 |
Pelvis	|	15	|		|	4	|	5x	|	3	|	3D T2	|	2D	pair |	CNN <br> U-net		|	def	|	38±6 <br>43±9	|	29.5±1.2<br>28.2±1.6 	|	.96±.01<br>.95±.01	|	ME, PCC	|  [Bahrami2020](https://doi.org/10.1002/mp.14418) | 2020-07-30 |
Pelvis	|	100	|		|	 |		|	3	|	2D T2 FSE	|	2D unp	|	GAN	|	No	|		|		|		|	FID	|  [Fetty2020](https://doi.org/10.1016/j.zemedi.2020.05.001) | 2020-11 |
Breast	|	14	|		|	2	|	LoO	|	n.a. |	n.a.  |	2D	|	U-net<sup>1</sup>	|	def	|	|	 |	 | DSC .74-.76 	|  [Jeon2019](https://doi.org/10.14407/jrpr.2019.44.4.149) | 2019-12-31 |

**Super/subscripts**  
<sup>v</sup>volunteers, not patients; <sup>1</sup>to segment CT into 5-classes;  <sup>a</sup>multiple combinations of Dixon images was investigated but omitted here; <sup>b</sup>dataset from http://www.med.harvard.edu/AANLIB/ ; <sup>t</sup>robustenss to training size was investigated;<sup>\*</sup>comparison with other architecture has been provided; <sup>+</sup>trained in 2D on multiple view and aggregated after inference;   
**Abbreviations**  
H&N=head and neck ; val=validation;  x-fold=cross-fold ;conf=configuration; arch=architecture; GRE=gradient echo; (T)SE=(turbo) spin-echo, mDixon = multi-contrast Dixon reconstruction; LoO=leave-one-out; (R)MSE=(root) meas squared error; ME=mean error; DSC=dice score coefficient; (N)CC=normalized cross correlation; FSIM, MSIM, IS, SWD, FID, PCC look up the references ;)

## MRI-to-sCT with dose evaluation

| Tumour site   | train | val | test | x-fold | field [T] | sequence | conf | arch | pair reg | MAE [HU] | PSNR [dB] | others| Plan | DD [%] | GPR [%] | DVH | others |  reference    | pub date |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
Liver	|	21	|		|		|	LoO	|	3	| 3D T1 GRE	|	3D pair| GAN	|	def	|	73±18	|	22.7±3.6	|		NCC | 	p	| | 99.4±1.0<sup>3</sup> | <1%  | range γ<sub>2</sub> γ<sub>1</sub>  | [LiuY2019](https://doi.org/10.1088/1361-6560/ab25bc) | 2019-06-16|  
Abdomen	|	12	|		 		| 	 |	4x	| 0.3 1.5 |  GRE  |	2D pair br> 2D unp| GAN<sup>\*</sup>	|	def	| 90±19<sup>2</sup> <br>94±30<sup>2</sup>  | 27.4±1.6 <br>27.2±2.2|  | 	x+B<sub>0</sub>	| <±0.6<br>	<±0.6 | 98.7±1.5%<br>98.5±1.6%  | <±0.15  |  γ<sub> 3</sub>  | [Fu2020](https://doi.org/10.1088/2057-1976/ab6e1f) |  2020-01-31 |
Abdomen	|	46	|		|  	31	| 3x	 |	3	| 3D T1 GRE   |	2.5D pair | U-net	|	syn rig	| 79±18 |  |  MAE, ME organs |	x	|  |  | <2Gy  |   | [Liu2020](https://doi.org/10.1088/1361-6560/ab8cd2)| 2020-06-11 | 
Abdomen kids	|	54	|	18	|  12		|	 3x |	1.5	3| 3D T1 GRE, T2 TSE  |	3Dp pair | U-net	|	def	| 62±13 | 30.0±1.8	|  ME, DSC tissues | 	x<br>p| <0.1<br><0.5 | 99.7±0.3<sup>2</sup> <br>96.2±4.0<sup>2</sup> | <2% <br><3% | beam depth  | [Florkow2020](https://doi.org/10.1016/j.radonc.2020.09.056) | 2020-10-07
Abdomen |	39 	|		|  	19	|	 |	0.35	| GRE   |	2D pair | U-net	|	def	| 79±18 |  |  ME tissues |	x+B<sub>0</sub>| <0.1 | 98.7±1.1<sup>2</sup> | <2.5% | γ<sub>3</sub> γ<sub>1</sub>  | [Cusumano2020](https://doi.org/10.1016/j.radonc.2020.10.018) | 2020-10-17 |  
Brain	|	26	|		|		|	2x	|	1.5	| 3D T1 GRE	|	m2D+ pair | CNN	|	rig	|	67±11	|		|		ME, tissues DSC, dist body |	x	| -0.1±0.3 | 99.8±0.7<sup>2</sup> |   | beam γ<sub> 3</sub> depth γ<sub>1</sub>| [Dinkla2018](https://doi.org/10.1016/j.ijrobp.2018.05.058) | 2018-11 |   
Brain	|	40	|		|	10	|		|	1.5	| 3D T1 GRE Gd |	2D pair | CNN	|	def	|	75±23	|	|		DSC | 	x	| <0.2±0.5 | 99.2<sup>3</sup> |   |  | [LiuF2019](https://doi.org/10.1002/acm2.12554) | 2019-03-12 |   
Brain	|	54	|	9	|	14	|	5x	|	1.5	| 2D T1 SE Gd |	2D pair | GAN	|	rig	|	47±11	|	|		each fold |	x	| -0.7±0.5 | 99.2±0.8<sup>2</sup> | <1%  | 2D/3D γ<sub> 3</sub> γ<sub>1</sub> | [Kazemifar2019](https://doi.org/10.1016/j.radonc.2019.03.026) | 2019-04-11 |
Brain	|	55	|28 |	4	|		|	1.5	| 3D T1 GRE	|	2D pair<br>3Dp pair | U-net	|	rig	|	116±26<br>137±32	|		|		ME | 	x<br>p	|  | >98^2,98±2<sup>2</sup> <br>>98^2,97±3<sup>2</sup> |  | range  γ<sub>1</sub> | [Neppl2019](https://doi.org/10.1080/0284186X.2019.1630754) |  2019-07-04|  
Brain	|	25	|	2	|  25		|		|	1.5	| 3D T1 GRE  |	3Dp pair | GAN	|	rig	| 55±7 | 	|	 ME DSC|	x	| <2 | 98.4±3.5<sup>2</sup> | <1.65%   | range  γ<sub> 3</sub> γ<sub>1</sub>| [Shafai2019](https://doi.org/10.14338/ijpt-19-00062.1) | 2019-09-30|   
Brain | 47 | | 13 | 5x | 3 | T1 | 2D pair | U-net | rig |81±15 | |  ME air, tissues| x |2.3±0.1 |  |   |  align CBCT<0.5mm  | [Gupta2019](https://doi.org/10.3389/fonc.2019.00964) | 2019-10-25 |  
Brain	|	12	|	2	|  1		|	LoO	|	3	| 3D T1 GRE  |	2D+ pair | U-net	|	rig	| 54±7 | 	|	 ME, DSC | p	| 0.00±0.01 |  |   | range tissues | [Spadea2019](https://doi.org/10.1016/j.ijrobp.2019.06.2535) | 2019-11-01 |   
Brain	|	15	|		 		| 	 |	5x	| |  T1, T2 FLAIR<sup>c</sup> |	2Dp pair | GAN	|	def	| 108±24 |  |  tissues |	x	| 0.7 | 99.2±1.0<sup>2</sup>  | <1%  | beam depth γ<sub>3</sub>  γ<sub>1</sub> | [Koike2019](https://doi.org/10.1093/jrr/rrz063) | 2019-12-10 |  
Brain	|	66	|		 		| 11	 |	5x	| 1.5 |  2D T1 SE Gd  |	2D unp | GAN	|	rig	| 78±11 |  |   |	p	| 0.3±0.3 | 99.2±1.0<sup>2</sup>  | <3%  | beam γ<sub>3</sub>  depth γ<sub>1</sub> | [Kazemifar2020](https://doi.org/10.1002/acm2.12856) | 2020-03-26 |  
Brain kids	|	30<sup>t</sup>	|	10	|  20		|	 3x |	1.5 3	| 3D T1 GRE±Gd   |	 2D+<sup>\*</sup> pair | GAN<sup>\*</sup>	|	rig	| 61±14 | 26.7±1.9	|  ME DSC SSIM | 	x	<br> p| -0.1±0.3<br> 0.1±0.4 | 99.5±0.8<sup>2</sup><br>99.6±1.1<sup>2</sup> | <1% <br><3% | beam depth γ<sub>3</sub>  | [Maspero2020](https://doi.org/10.1016/j.radonc.2020.09.029) | 2020-10-23 |  
Brain	|	242<sup>m,t</sup>	|		 	81	| 79	 |		| 3 1.5|  3D T1 GRE±Gd  |	3Dp pair| CNN<br>U-net	|	def	| 81±22<br>90±21 | |tissues |	x	| 0.13±0.13<br>0.31±0.18  | 99.6±0.3<sup>2</sup><br>99.4±0.5<sup>2</sup>  | <±0.15  |  γ<sub> 3</sub>  | [Andres2020](https://doi.org/10.1016/j.ijrobp.2020.05.006) | 2020-11   |
Brain	|	26	|		 15		| 12	 |		| 1.0 | T1 Gd  |	2D | GAN	|	def	| |  | bone  | 	x	| <±1 | | <1.5%  |   | [Liu2021](https://doi.org/10.1002/acm2.13139) | 2021-01-07|  
Prostate <br>Rectum <br>Cervix	|	32	|		|	27<br>18<br>14 |		|	3<br>1.5<br>1.5/3	|	3D T1 GRE mDixon  	|	2D pair	|	GAN |	rig	|	60±6<br>56±5 <br>59±6  |	|		ME | x	| -0.3±0.4<br> -0.3±0.5<br>-0.1±0.3<sup>a</sup> | 99.4±0.6<sup>3</sup><br>98.5±1.1<sup>3</sup> <br> 99.6±1.9<sup>3</sup>|<1% | γ2</sub></sub> | [Maspero2018](https://doi.org/10.1088/1361-6560/aada6d) | 2018-09-10|   
Prostate| 36 | | 15 |   | 3 | T2 TSE | 2D pair | U-net | def |	30±5 |	|		ME tissues |  	x	| 0.16±0.09 | 99.4<sup>2</sup> | <0.2Gy  | γ<sub>3</sub> γ<sub>1</sub>| [Chen2018](https://doi.org/10.1002/mp.13247) | 2018-10-20 |
Prostate | 39 | | | 4x | 3 | 3D T2 | 2D pair | U-net | def |33±8 | |ME, DSC dist body | x |-0.01±0.64 | 98.5±0.7<sup>2</sup> | <3%  | γ<sub>3</sub> γ<sub>1</sub>| [Arabi2018](https://doi.org/10.1002/mp.13187) | 2018-10-14 |
Prostate	|	17	|		|		|	LoO	|	1.5	| T2  |	3D patch | GAN<sup>\*</sup>	|	No	|	51±17	| 24.2±2.5	|	 NCC, bone:dist, uniform	 | 	p	| -0.07±0.07 | 98±6<sup>2</sup> | <1%  | range peak γ<sub> 3</sub>  γ<sub>1</sub>| [LiuY2019b](https://doi.org/10.1088/1361-6560/ab41af) | 2019-10-21 |  
Prostate	|	25	|		| 	14	|	3x	|	3	| 3D T2 TSE |	2D | U-net<sup>\*</sup> <br>GAN<sup>\*</sup>	|	def	| 34±8<br>34±8 | 	|	 ME tissues | 	x	| <1%<br><1% | 99.2±1<sup>1</sup><br>99.1±1<sup>1</sup> | <1%  |  | [Largent2019](https://doi.org/10.1016/j.ijrobp.2019.08.049) | 2019-12-1 |      
Pelvis	|	11<sup></sup>m	|		 		| 8	 |		| 3 1.5|  T2 TSE  |	2D | GAN<sup>\*</sup>	|	def	| 49±6 |  | ME organs | 	x	| 0.7±0.4 | 99.2±1.0<sup>2</sup>  | <1.5%  |    | [Boni2020](https://doi.org/10.1088/1361-6560/ab7633) | 2020-04-02 |  
Pelvis	|	26	|		 15		| 10+19<sup>m</sup>	 |		| 0.35 1.5/3 | 3D T2  |	2.5D | GAN<sup>\*</sup>	|	def	| 41±4 | 31.4±1 | ME MSE bone | 	x	| <±1 | | <1.5%  |   | [Fetty2020](https://doi.org/10.1088/1361-6560/ab857b) | 2020-05-22|  
Pelvis	|	39	|		|  14	|	 |	0.35	| GRE   |	2D pair| U-net	|	def	| 54±12 |  |  ME tissues |	x+B<sub>0</sub>| <0.5 | 99.0±0.7<sup>2</sup> | <1%  | γ<sub>3</sub> γ<sub>1</sub>  | [Cusumano2020](https://doi.org/10.1016/j.radonc.2020.10.018) | 2020-10-17 |  
Rectum	|	46<sup></sup>m	|		 		| 44	 |		| 1.5 | 3D T2  |	2D | GAN	|	def	| 35±7 | | ME bone | 	x	| <±0.8 | 99.8±0.1<sup>2</sup>  | <1%  |  γ<sub> 3</sub> γ<sub>1</sub>  | [Bird2020](https://doi.org/10.1016/j.radonc.2020.11.027) | 2020-11-29 | 
H&N	|	34	|		|		|	3x	|	1.5	| 3D T2 TSE	|	3Dp pair | U-net	|	def	|	75±9	|		|		ME DSC bone | 	x	| -0.07±0.22 | 95.6±2.9<sup>2</sup> |   | γ<sub> 3</sub> | [Dinkla2019](https://doi.org/10.1002/mp.13663) | 2019-06-17 |
H&N	|	15	|		|  12		|	|	3	| T1 GRE  |	2Dp pair<sup>\*</sup> | GAN<sup>\*</sup>	|	def	|  | 68±2	|   SSIM RMSE | 	p	| <0.5 | <98<sup>2</sup> | <0.5  |   | [Klages2019](https://doi.org/10.1002/mp.13927) |2019-11-16 |  
H&N	|	30	|		|  15		|	|	3	| T1±Gd <br>T2 TSE<sup>c</sup>  |	2D pair | GAN<sup>\*</sup> <br> U-net	|	rig	| 70±12<br>71±12  | 29.4±1.3<br>29.2±1.3 	|   SSIM DSC, DRR | 	p	| -0.3±0.2<br>-0.2±0.2 | 97.8±0.9<sup>2</sup> <br>97.6±1.3<sup>2</sup> |   |   | [Qi2020](https://doi.org/10.1002/mp.14075) | 2020-02-06|  
H&N	|	135<sup>t</sup>	|	10	|  28		|	  |	3	| 3D T1 GRE   |	2D pair <br>unp | GAN<sup>\*</sup>	|	def	| 70±9<br>101±8 | 	| ME, DSC tissues | 	x	| -0.1±0.3<br>0.1±0.4 | 98.7±1.0<sup>2</sup><br>98.5±1.1<sup>2</sup> | <1.5% <br><1.5% | beam depth  | [Peng2020](https://doi.org/10.1016/j.radonc.2020.06.049) |2020-07-03 |
H&N	|	27	|		 | 	 |	3x	| 3 | 3D T1 GRE  |	2D+ pair | GAN	|	def	| 65±4 |  | ME | 	p	| <±0.2 | 93.5±3.4| <1.5%  | NTCP DSC  RS γ<sub>3</sub> | [Thummerer2020](https://doi.org/10.1088/1361-6560/abb1d6)| 2020-11-27|
Breast	|	12<sup>t</sup>	|		|  18		|	LtO	|	1.5	| 3D GRE mDixon  |	2D<br>+ patch | GAN<sup>\*</sup>	|	def	| 94±11<br>103±15  | 	|	 NCC | p	| <0.5 | 98.4±3.5<sup>2</sup> |   | DRR dist bone  | [Olberg2019](https://doi.org/10.1002/mp.13927) | 2019-11-16 |  

**Super/subscripts**  
<sup>\*</sup>comparison with other architecture has been provided; <sup>3</sup>γ<sub>3%,3mm</sub> = γ<sub>3</sub>; <sup>2</sup>γ<sub>2%,2mm</sub> = γ<sub>2</sub>; <sup>1</sup> γ<sub>1%,1mm</sub> = γ<sub>1</sub>; <sup>t</sup>robustenss to training size was investigated; <sup>+</sup>trained in 2D on multiple view and aggregated after inference;  <sup>c</sup> multiple combinations  (also ± Dixon reconstruction, where present) of the sequences were investigated but omitted;
<sup>m</sup> data from multiple centers   
**Abbreviations**  
H&N=head and neck ; val=validation;  x-fold=cross-fold ;conf=configuration; arch=architecture; GRE=gradient echo; (T)SE=(turbo) spin-echo, mDixon = multi-contrast Dixon reconstruction; LoO=leave-one-out; (R)MSE=(root) meas squared error; ME=mean error; DSC=dice score coefficient; (N)CC=normalized cross correlation;

## CBCT

| Tumour site   | train | val | test | x-fold |  conf | arch | pair reg | MAE [HU] | PSNR [dB] |SSIM | others| Plan | DD [%] | DPR [%] |GPR [%] | DVH | others |  reference    | pub date |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
Pancreas   | 30                     |                 |                    | LoO                 | 3Dp pair   | GAN<sup>\*</sup>   | def   | 56.89±13.84  | 28.80±2.46 | .71±.032  | NCC|   SNU       | x             |          | |   <1Gy |           | [Liu2020](https://doi.org/10.1002/mp.14121) | 2020-03-06|
Brain <br>Pelvis     | 24<br>20   | |     | LoO    | 3D patch     | GAN           |  rig   | 13±2<br>16±5 | 37.5±2.3 <br>30.7±3.7|   | NCC SNU      |       No      |                 | |          |  |  |[Harms2019](https://doi.org/10.1002/mp.13656)| 2019-06-17 |      
Prostate   | 16  | | 4  | 5x  | 2D pair   | U-net | def  |   | 50.9 |.967  | SNU RMSE   | No    |   || |  |  |  [Kida2018](https://doi.org/10.7759/cureus.2548) | 2018-04-29|  
Prostate   | 27  | 7  | 8  |     | 2D pair   | U-net<sup>\*</sup>  | def   | 88    |   | | ME|  x<br>p|  |      >98.4<sup>1</sup><br>88.5<sup>3</sup>    |  99.5<sup>2</sup> <br>>96.5<sup>2</sup> |      |    γ<sub> </sub>1 DPR<sub> 2</sub>     | [Landry2019](https://doi.org/10.1088/1361-6560/aaf496)     |  2019-01-24 |
Prostate    | 18 | | 8                     | 4x                  | 2D  ens unp   | GAN           | No|   rig   | 87±5   | |    | ME          | x<br>p|   99.9±0.3<sup>2</sup> <br>   80.5±5<sup>2</sup>   | 95.9±2.0<sup>2</sup>       |  <±1.5% <br>  <1%     | DPR<sup>1</sup>   DPR<sup>3</sup> RS γ<sub>3</sub>  |  [Kurz2019](https://doi.org/10.1088/1361-6560/ab4d8c) |   2019-11-15|
Prostate   | 16                     |                 | 4                     |                  | 2D pair                | GAN<sup>\*</sup>           | rig   |   | |    | SelfSSIM   tissues |         No      |                 | |      |    |      | [Kida2019](https://doi.org/10.1002/mp.13963)         | 2019-12-16|
Pelvis<br> H&N|   135                    | 15                 | 15<br>   10         | 10x                 | 2.5D pair              | GAN<sup>\*</sup>           |  def   | 24±5<br> 24±4                 | 20.1±3.4<br> 22.8±3.4             |    |     |     x, p | <1% |        | |   |     RS | [Zhang2020](https://doi.org/10.1002/mp.14624)      |2020-12-01 |   
H&N<br>  Lung<br>   Breast     | 15<br> 15<br> 15  | 8<br>8<br>8 | 10<br>10<br>10 |                  | 2D                 | GAN<sup>\*</sup>           | No  rig   | 53±12<br>83±10<br>66±18       | 30.5±2.2<br>  28.5±1.6<br> 29.0±2.1 | .81±.04<br> .78±.04<br> .76±.02 | ME          | x             | 0.1±0.5 <br>   0.2±0.9 <br>0.1±0.4        |   |     97.8±1<sup>2</sup><br> 94.9±3<sup>2</sup><br>   92±8<sup>2</sup>   | <2%     | γ<sub> 3</sub>    | [Maspero2020](https://doi.org/10.1016/j.phro.2020.04.002)  | 2020-04-29 |   
H&N | 81   | 9            | 20          |                  | 2D                 | GAN<sup>\*</sup>           |  No   def   | 29.85±4.94   | 30.65±1.36 | .85±.03   | RMSE  phantom        |    x           |          |    |    98.4±1.7<sup>2</sup>    96.3±3.6<sup>1</sup>   |      |          |  [Liang2019](https://doi.org/10.1088/1361-6560/ab22f9) | 2019-06-10 |   
Nasophar| 50                     | 10                 | 10                    |       | 2D                 | U-net         | rig   | 6-27| |    | ME   organs      |   x      |        0.2±0.1| |95.5±1.6<sup>1</sup>   | <1%   |      |     [Li2019](https://doi.org/10.1088/1361-6560/ab2770)   | 2019-07-16 |  
H&N | 30                     | 7                  | 7                     |                  | 2D                 | U-net<sup>\*</sup>         | rig   | 18.98| 33.26      | 0.8911| RMSE   tissues        |      No         |            |     | |       |          | [Chen2019](https://doi.org/10.1002/mp.13978) | 2019-12-18 | 
H&N | 30                     |                 | 14                    |                  | 2D                 | GAN           | def   | 82±11    | |    | ME  tissues          | x                              | 91.0±5.3<sup>2</sup>    | |      <1Gy|  <1% |         | [Barateau2020](https://doi.org/10.1002/mp.14387)| 2020-07-12 |   
H&N | 22                     |                 | 11                    | 3x                  | 2D+ | U-net         | def   | 36±6     | |    | ME DSC   SNU   | p           |    -0.1±0.3      | | 98.1±1.2<sup>2</sup>    |      | RS    γ<sub> 3</sub> |[Thummerer2020](https://doi.org/10.1088/1361-6560/ab7d54) | 2020-04-27|   
H&N | 50<sup>t</sup>               |                 | 10                    |                  | 2.5D               | U-net         | rig   | 49   | | .85  | SNR         |         No      |                 | |      |   |       | [Yuan2020](https://doi.org/10.1088/1361-6560/ab6240) |2020-01-24|    
H&N    | 23   | |     | LoO    | 3D patch     | GAN<sup>\*</sup>           |  rig   |  | 24.3±1.4| .80±.05  | stop power      |       p |     |     | 88.4<sup>2</sup> |   <1%       | γ<sub>3</sub> γ<sub>2</sub> |  [Harms2019](https://doi.org/10.1002/mp.14347)| 2019-06-17 |
H&N <br> Thorax <br> Pelvis | 25  <br>   53 <br>   205 || |    15  <br>   15 <br>   15                 | 2D                 | GAN           | def    | 77±13  <br>   94±32  <br>   42±5 |  | |    ME DSC   HD tissues    |            x |  |  91.5±4.3<sup>2</sup> <br>   76.7±17.3<sup>2</sup> <br>   88.9±9.3<sup>2</sup> | 95.0±2.4<sup>2</sup>  <br>  93.8±5.9<sup>2</sup>   <br>  98.5±1.7<sup>2</sup> |   <2.4  <br>  <2.6  <br>  <1  | γ<sub> 3</sub>   | [Eckl2020](https://doi.org/10.1016/j.ejmp.2020.11.007)          |   2020-11-24 |


**Super/subscripts**  
<sup>\*</sup>comparison with other architecture has been provided; <sup>3</sup>γ<sub>3%,3mm</sub> = γ<sub>3</sub>; <sup>2</sup>γ<sub>2%,2mm</sub> = γ<sub>2</sub>; <sup>1</sup> γ<sub>1%,1mm</sub> = γ<sub>1</sub>; <sup>t</sup>robustenss to training size was investigated; <sup>+</sup>trained in 2D on multiple view and aggregated after inference;  <sup>c</sup> multiple combinations  (also ± Dixon reconstruction, where present) of the sequences were investigated but omitted;
<sup>m</sup> data from multiple centers   
**Abbreviations**  
H&N=head and neck ; val=validation;  x-fold=cross-fold ;conf=configuration; arch=architecture; GRE=gradient echo; (T)SE=(turbo) spin-echo, mDixon = multi-contrast Dixon reconstruction; LoO=leave-one-out; (R)MSE=(root) meas squared error; ME=mean error; DSC=dice score coefficient; (N)CC=normalized cross correlation;

----------------------

## PET

| Region  | train | val | test | x-fold | field [T] | image contrast | conf | arch | pair reg | MAE [HU] | DSC | tracer| PET<sub>err</sub> [%] | others |  reference    | pub date|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
Pelvis| 10             |           | 16               |                  | 3    | Dixon  ZTE    | 3D  patch            | U-net         | def              |                   |              | <sup>1</sup>8F-FDG   <sup></sup>68Ga-PSMA || RMSE    SUV diff    | [Leynes2017](https://doi.org/10.2967/jnumed.117.198051)           |2017-05-01  |
Head  | 30             |           | 10               |                  | 1.5  | T1 GRE    Gd       | 2D            | auto-enc         | def                        | .971±.005<sup>a</sup>   .936±.011<sup>s</sup>|   .803±.021<sup>b</sup>      |n.a.    | -0.7±1.1               | | [Liu2018](https://doi.org/10.1148/radiol.2017170700)                  |  2017-10-19 |
Pelvis| 12             |           | 6                |                  | 3    | T1 GRE    T2 TSE         | 3D            | CNN<sup>1</sup>           | def               |                 | .98±.01<sup>s</sup> .79±.03<sup>b</sup>  .49±.17<sup>a</sup>    | <sup>1</sup>8F-FDG    | | RMSE     | [Bradshaw2018](http://dx.doi.org/10.18383/j.tom.2018.00023) |   2018-09 |
Head  | 30<sup></sup>p+6             |           |     8          |          |    |  UTE mDixon        | 2D          | U-net<sup>1</sup>         | def              |                 | .96±.006<sup>b</sup>      | <sup>1</sup>8F-FDG|   <1% |       | [Jang2018](https://doi.org/10.1002/mp.12964)      |   2018-5-15 |
H&N  | 32 <br> 12          |           | 8 <br> 2      | 5<br>7             | 3    | Dixon±ZTE         | 2D         | U-net         | rig              |     13.8±1.4<br>12.6±1.5            | .76±.04<sup>b</sup><br>.80±.04<sup>b</sup> | <sup>1</sup>8F-FDG | <3 |    | [Gong2018](https://doi.org/10.1088/1361-6560/aac763)          | 2018-06-13 |
Pelvis| 15             |           | 4                | 4         | 3    | T1 GRE  Dixon    | 2D            | U-net         | def              | |  |<sup>1</sup>8F-FDG <br> 1.8±2.4 <br> | 1.7±2.0<sup></sup>f <br>   1.8±2.4<sup>s</sup> <br>   3.8±3.9<sup>b</sup> | mu-map diff       | [Torrado2019](https://doi.org/10.2967/jnumed.118.209288)          |  2018-08-30 |
Head  | 23             |           | 47               |                  | 3    | ZTE               | 3D   patch           | U-net         | def              |                 | .81±.03<sup>b</sup> |<sup>1</sup>8F-FDG | -0.2±5.6               | Jac  | [Blanc-Durand2019](https://doi.org/10.1371/journal.pone.0223141) |  2019-10-07|
Head  kids   | 60             |           | 19               | 4         | 3    | T1 GRE  mDixon, UTE         | 3D            | U-net         | rig              |   |  .90±.07<sup></sup>j  |<sup>1</sup>8F-FET | |  biol tumor    vol, SUV | [Ladefoged2019](https://doi.org/10.3389/fnins.2018.01005)      |   2019-01-07 |
Head  | 44             | 11           | 11               |                  | 1.5  | T1 GRE                | 2.5D          | U-net         | rig              |                 | |<sup>1</sup>1C-WAY  <sup>1</sup>1C-DASB | -0.49±1.7             | synt mu-map,   kin anal                   | [Spuhler2019](https://doi.org/10.2967/jnumed.118.214320)      | 2019-08-30 |
Head  | 40             |           |               | 2         | 3    | 3D T1  GRE        | 3D  patch            | GAN           | def              | 101±40   302±79<sup>b</sup>   407±228<sup>a</sup>   8±4<sup>s</sup> | .80±.07<sup>b</sup>              | <sup>1</sup>8F-FDG|3.2±3.4  1.2±13.8<sup>b</sup>   3.2±13.6<sup>s</sup>   3.2±13.6<sup>a</sup>           | rel vol dif   surf dist ME   RMSE PSNR   SSIM SUV | [Arabi2019](https://doi.org/10.1007/s00259-019-04380-x)              | 2019-07-01   |
Prostate      | 18             |           | 10               |                  | 3    | Dixon             | 2D            | GAN<sup>\*</sup>           | def              |                 | | <sup></sup>68Ga-PSMA              | 2.4±0.5            |  SSIM  SUV    | [Pozaruk2020](https://doi.org/10.1007/s00259-020-04816-9)   | 2020-05-11 |   
Head  | 35             |           |               | 5         | 3    | 3D T1 GRE   mDixon+UTE<sup></sup>c        | 2.5D          | U-net         | rig              |  11.94±0.01               | .87±.03<sup>b</sup>      | <sup>1</sup>1C-PiB  <sup>1</sup>8F-MK-6240 |   <2% |       | [Gong2020](https://doi.org/10.1007/s00259-020-05061-w)        | 2020-10-27 |
Head  | 32             |           |               | 4         | 3    | Dixon             | 3D   patch          | GAN<sup>\*</sup>   | def             |      16±2%          | .74±.05<sup>b</sup> | <sup>1</sup>8F-FDG| -1.0±13 |  SUV |     [Gong2020](https://doi.org/10.1109/TRPMS.2020.3006844)  | 2020-07-03 |   
Thorax| 14             |           |               | LoO                 | 3    | Dixon             | 2D            | GAN<sup>\*</sup>           |  No  def               | 68±10       |        |<sup>1</sup>8F-NaF        |                       | PSNR SSIM   RMSE              | [Baydoun2020](https://doi.org/10.1016/j.ibmed.2020.100010)    | 2020-12 |     
| |
Body | 100            |          |         28      |              PET, no att corrected      | 2D          | U-net         | Y<sup>i</sup>              |  111±16               | .94±.01<sup>b</sup>      | <sup>1</sup>8F-FDG |   -0.6±2.0% |    abs err   | [Liu2018](https://doi.org/10.1186/s40658-018-0225-8) |2018-11-12 |          
Body  | 100             |           |    25        |    PET, no att corrected        | 2.5D          | GAN         | Y<sup>i</sup>              |             |       | <sup>1</sup>8F-FDG | -0.8±8.6%   |   SUV ME    | [Armanious2020](https://doi.org/10.1186/s13550-020-00644-y0) | 2020-05-24 |          
Body  | 80             |           |    39           |            PET, no att corrected  | 3D   | GAN   | Y<sup>i</sup>               |  109±19               | .87±.03<sup>b</sup>      | <sup>1</sup>8F-FDG|  0.1<3.0% |  NCC PSNR ME     | [Dong2019](https://doi.org/10.1088/1361-6560/ab4eb7)    |  2019-11-4 |

**Super/subscripts**  
<sup>\*</sup>comparison with other architecture has been provided; <sup>a</sup>in air or bowel gas; <sup>b</sup>in the bony structures; <sup>s</sup>in the soft tissue; <sup>f</sup> in the fatty tissue; <sup>w</sup> in water; <sup>j</sup>expressed in terms of Jaccard index and not DSC; <sup>i</sup>intrinsically registered: PET-CT data; <sup>p</sup>data from another MRI sequence used as pre-training; <sup>c</sup> multiple combinations  (also ± Dixon reconstruction, where present) of the sequences were investigated but omitted;
**Abbreviations**  
H&N=head and neck ; val=validation;  x-fold=cross-fold ;conf=configuration; arch=architecture; GRE=gradient echo; (T)SE=(turbo) spin-echo, mDixon = multi-contrast Dixon reconstruction; LoO=leave-one-out; (R)MSE=(root) meas squared error; ME=mean error; DSC=dice score coefficient; (N)CC=normalized cross correlation; paed=paediatric
