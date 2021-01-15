
# Overview sCT



Repository to collect all the references on generation of synthetic computed tomography (sCT) with deep learning/convolutional networks. Generated from Spadea MF, Maspero M et al Med. Phys. 2021 (submitted).

## License
[![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa] 

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

## MRI without dose evaluation

| Tumour site   | train | val | test | x-fold | field [T] | sequence | conf | arch | pair reg | MAE [HU] | PSNR [dB] | SSIM | others |  reference    | pub date |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
Brain	|	18	|		|		|	6x	|	1.5 |	3D T1 GRE		|	2D	|	U-net		|	rig	|	85±17	|		|		|	MSE ME	| [Han2017](https://doi.org/10.1002/mp.12155)	| 2017-02-13 |
Brain <br>Prostate	|	16<br>22	|		|		|	LoO	|	n.a.	|	T1	|	2.5D patch	|		CNN+ 	|	rig	|	85±9<br>43±2	|	27.3±1.1<br>33.5±0.8	|		| | [Xiang2018](https://doi.org/10.1016/j.media.2018.03.011)	| 2018-03-30   
Brain	|	15	|		|		|	x5	|	1.0	|	T1 Gd	|	2D	|		GAN<sup>\*</sup> 	|	def	|	89±10	|	26.6±1.2	|	.83±.03	| tissues | [Emami2018](https://doi.org/10.1002/mp.13047)	| 2018-06-14    
Prostate	|	20	|		|		|	5x	|	1.5	|	2D T1 TSE	|	2D<br>3D	|		U-net	|	def	|	41±5<br>38±5	|		|		|	DSC bone 	| [Fu2019](https://doi.org/10.1002/mp.13672)| 2019-06-20 |
Brain	|	98CT 84MR 	|		|	10	|		|	3	|	3D T2	|	2D |		GAN	|	no	|	19±3	|	65.4±0.9	|	.25±.01	|		| [Jin2019](https://doi.org/10.3390/s19102361) | 2019-05-22 |
Pelvis human <br> Pelvis canine	|	27<br>18	|		|		|	3x	|	3<br>1.5	|	3D T1 GRE mDixon 	|	3D	|		U-net	|	def	|	32±8	|	36.5±1.6	|		|	MAE/DSC bone surf dist<0.5 mm |  [Florkow2020](https://doi.org/10.1002/mrm.28008) | 2019-10-08 |
H&N	|	23	|		|	10	|		|	1.5|	T2	|		|	U-net	|	def	|	131±24	|		|		|	MAE, ME soft tis./bone | [Wang2019](https://doi.org/10.3389/fonc.2019.01333) | 2019-11-29|
Abdomen |	10<sup>v</sup>	|		|	10	|	LoO	|		|	mDixon |	2D	|	GAN |	def	|	61±3	|		|		|	CC |  [Xu2019](https://doi.org/10.1109/ACCESS.2019.2951924) | 2019-11-06 |
Brain <br> Pelvis	|	24<br>20	|		|		|	LoO	|	n.a. <br>n.a.	|	T1<br>3D T2  |	3D patch	|	GAN	|	rig	|	56±9<br>51±16	|	26.6±2.3<br>24.5±2.6	|		|	NCC, Hausdorff on body	|  [Lei2019](https://doi.org/10.1002/mp.13617) | 2019-05-21 |
Breast	|	14	|		|	2	|	LoO	|	n.a. |	n.a.  |	2D	|	U-net<sup></sup>1	|	def	|	|	 |	 | DSC .74-.76 	|  [Jeon2019](https://doi.org/10.14407/jrpr.2019.44.4.149) | 2019-12-31 |
Brain<br>Abdomen	|	33<br>160	|		|		|	LoO	|	n.a.<br>n.a.	|	T1<sup>b</sup><br>n.a.	|	2D	|	GAN	|	yes<br>no	|	9.0±0.8<br> 5.1±0.5	|		|	.75±0.77<br>.90±.43	| FSIM MSIM IS SWD FID experts	| [Xu2020](https://doi.org/10.1016/j.neunet.2020.05.001) | 2020-05-08 |
Brain	|	28	|		|	6	|		|	1.5	|	T2	|	2D	|	U-net<br> GAN	| rig <br>no	|	65±4<br>94±6	|	28.8±0.6<br> 26.3±0.6	| .972±.004<br>.955±0.007	| same metrics for synth MRI |[Li2020](https://doi.org/10.1155/2020/5193707) | 2020-11-05|
Brain	|	81	|		|	11	|	8x	|	1.5	|	3D T1 GRE<br> 3D T1 GRE Gd<br>2D T2 SE<br>2D T2 FLAIR 	|	2D	|	U-net 	|	aff |  45.4±8.5<br>44.6±7.4 <br>45.7±8.8 <br>51.2±4.5 | 43.0±2.0<br>43.4±1.2 <br>43.4±1.2 <br>44.9±1.2	| .65±.05<br>.63±.03 <br> .64±.03<br>.61±.04	|	metrics for air bone, soft tissue, DSC bones	|  [Massa2020](https://doi.org/10.1088/1361-6560/abc5cb) | 2020-11-27|
Pelvis	|	15	|		|	4	|	5x	|	3	|	3D T2	|	2D	|	CNN <br> U-net		|	def	|	38±6 <br>43±9	|	29.5±1.2<br>28.2±1.6 	|	.96±.01<br>.95±.01	|	ME, PCC	|  [Bahrami2020](https://doi.org/10.1002/mp.14418) | 2020-07-30 |
H&N	|	60			|	30	|		|	3	|	T1	|	2D	|	GAN	|	no	|	19.6±0.7	|	62.4±0.5	|	.78±0.2	|		| | [Kearney2020](https://doi.org/10.1148/ryai.2020190027) | 2020-03-25 |
H&N	|	32	|		|	8	|	5x	|	3	|	3D UTE	|	2D	|	U-net	|	def	|	104±21	|		|		|	DSC, spatial corr	|  [Su2020](https://doi.org/10.3174/ajnr.A6758) | 2020-10-06 |
Pelvis	|	100	|		|	 |		|	3	|	2D T2 FSE	|	2D	|	GAN	|	no	|		|		|		|	FID	|  [Fetty2020](https://doi.org/10.1016/j.zemedi.2020.05.001) | 2020-11 |
H&N	|	28	|	4	|		|	8x	|	1.5	|	2D T1±Gd, T2	|	2D	|	GAN	|	aff	|	75.7±14.6	|	29.1±1.6	|	.92±.02	|	DSC, MAE on bone	|  [Tie2020](https://doi.org/10.1002/mp.14062)|2020-02-03 |
H&N	|	7	|		|	8	|	LoO	|	1.5	|	3D T1, T2	|	2D	|		GAN	|	def	|	83±49	|		|		|	ME	|	[Largent2020](https://doi.org/10.1016/j.canrad.2020.01.008)| 2020-03-14 |
H&N	|	10	|		|		|	LoO	|	1.5	|	3D T1, T2	|	2D	|	GAN	|	def	|	42-62	|		|		|	RMSE, CC	|  [Qian2020](https://doi.org/10.1007/s10723-020-09513-3) | 2020-03-10 |
Brain	|	28	|	2	|	15 |		|	1.5	|	n.a.	|	2D	|	GAN<sup></sup\*		|	aff	|	134±12 | 24.0±0.9	| .76±.02	|		|  [Yang2020](https://doi.org/10.1109/tmi.2020.3015379) | 2020-11-30 |

**Super/subscripts**  
v=volunteers, not patients; ^1=to segment CT into several classes;  ^b =dataset from http://www.med.harvard.edu/AANLIB/ ; ^\*=comparison with other architecture has been provided; ^+ trained in 2D on multiple view and aggregated after inference
^t robustness to training size was investigated
^c multiple combinations  (also $\pm$ Dixon reconstruction, where present) of the sequences were investigated but omitted;
^m data from multiple centers  
**Abbreviations**  
H&N=head and neck ; val=validation;  x-fold=cross-fold ;conf=configuration; arch=architecture; GRE=gradient echo; (T)SE=(turbo) spin-echo, mDixon = multi-contrast Dixon reconstruction; LoO=leave-one-out; (R)MSE=(root) meas squared error; ME=mean error; DSC=dice score coefficient; (N)CC=normalized cross correlation; FSIM, MSIM, IS, SWD, FID, PCC look up the references ;)
