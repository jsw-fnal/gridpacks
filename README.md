# gridpacks
Repository for generating gridpacks with reweighting with amcatnlo 

Card templates can be found in the path addons/cards/UFOMODEL_template and the corresponding UFO file in addons/models
to generate a gridpack run "source submit_madpack_ttbareft.sh"
this will copy the template and replace settings in the default templates if needded according to what is specified 
in the submit script 
modify customize card to change the corresponding operators you want to use
the example gridpack gluontop_rwgt_slc6_amd64_gcc630_CMSSW_9_3_0_tarball.tar.xz was tested in debug which 
also contains an example lhe output with EFT and systematics weights   

## Generate multiple gridpacks
To generate more than one gridpack use submit_gridpacks.sh

Before you start create a cms environment using the following commands:
```
cmsrel CMSSW_9_4_6_patch1
cd CMSSW_9_4_6_patch1/src
cmsenv
export CMSSW_BASE=
```
Define the following parameters in submit_gridpacks.sh:
```
states to analyze (e.g. ttZ ttgamma) <-- make sure you have all cards in addons/cards/
declare number of jets (--> cardname e.g. ttZ0j_rwgt)
declare polynomial order (e.g. 2nd, 3rd, 4th)
lxplus GRID (where to calculate)
dim6 operators and stepsize as string (e.g. 'ctZ 1 ctZI 1')
referencepoint as string (e.g. 'ctZ 4 ctZI 4')
```
  
  
## List of available gridpacks:  
  
The script will loop over all states to analyze and create a directory structure in the output directory containing the calculated gridpacks, customizecards (with defined reference point) and pkl file
Available gridpacks, pkl files, customize cards and STDOUTs stored at:  
```  
/afs/hephy.at/data/llechner01/TTXPheno/gridpacks/<date>/<process>/order<poly order>/  
```  
  
  
### xx/06/2018  
##### under construction!!!!  
##### Reference Point (directory xx062018_ref)  
4 Fermion WC gridpacks for 3rd gen quarks with 1st/2nd gen leps  
Reference Point: ctW = 4., ctWI = 4., ctZ = 4., ctZI = 4., ctG = 4., ctGI = 4., cQe = 4., cQl31 = 4., cQlM1 = 4., ctl1 = 4., cte1 = 4., ctlS1 = 4., ctlSI1 = 4., ctlT1 = 4., ctlTI1 = 4., cblS1 = 4., cblSI1 = 4., cQl32 = 4., cQlM2 = 4., ctl2 = 4., cte2 = 4., ctlS2 = 4., ctlSI2 = 4., ctlT2 = 4., ctlTI2 = 4., cblS2 = 4., cblSI2 = 4.  
  
| process  | poly order | # coeff | Wilson coefficients                                                                 | Link to gen. events |
|:--------:|:----------:|:----:|:------------------------------------------------:|:--------------------:|
| ttZ      | 2          | 29   | cpQM, cpt, ctW, ctWI, ctZ, ctZI, ctG, ctGI, cQe, cQl31, cQlM1, ctl1, cte1, ctlS1, ctlSI1, ctlT1, ctlTI1, cblS1, cblSI1, cQl32, cQlM2, ctl2, cte2, ctlS2, ctlSI2, ctlT2, ctlTI2, cblS2, cblSI2 | not (yet) processed  |
  
  
### 14/06/2018  
##### Reference Point (directory 14062018_ref)  
4 Fermion WC gridpacks (test)  
Reference Point: ctZ = 4., ctZI = 4., cQl31 = 4., cQlM1 = 4., cQl32 = 4., cQlM2 = 4.  
  
| process  | poly order | # coeff | Wilson coefficients                                                                 | Link to gen. events |
|:--------:|:----------:|:-------:|:------------------------------------------------:|:--------------------:|
| ttZ      | 2          | 8       | cpQM, cpt, ctZ, ctZI, cQl31, cQlM1, cQl32, cQlM2 | not (yet) processed  |
  
  
### 05/06/2018  
Background gridpacks (leptonic)  
W > l nu  
Z > l l  
t > b W > b l nu  

| process  | poly order | # coeff | Wilson coefficients                                                                 | Link to gen. events  |
|:--------:|:----------:|:-------:|:-----------------------------------------------------------------------------------:|:--------------------:|
| WZ (lep)     | 2           | 0       | no relevant WC                                                                      | [1M WZ events](https://cmsweb.cern.ch/das/request?input=%2FWZ_lep_rwgt_slc6_amd64_gcc630_CMSSW_9_3_0_tarball%2Fllechner-bg_lep_dim6top_05June18-6dade6042d6868e7bb87de85663e8a54%2FUSER&instance=prod%2Fphys03) | 
| ttbar (lep)  | 2           | 15      | ctp, ctpI, cpQM, cpQ3, cpt, cptb, cptbI, ctW, ctWI, ctZ, ctZI, cbW, cbWI, ctG, ctGI | [1M ttbar events](https://cmsweb.cern.ch/das/request?input=%2Ftt_lep_rwgt_slc6_amd64_gcc630_CMSSW_9_3_0_tarball%2Fllechner-bg_lep_dim6top_05June18-399ed716eb7225402bb4416ff36fe4d6%2FUSER&instance=prod%2Fphys03) | 
  
  
### 04/06/2018  
Background gridpacks (hadronic + leptonic)

| process  | poly order | # coeff | Wilson coefficients                                                                 | Link to gen. events  |
|:--------:|:----------:|:-------:|:-----------------------------------------------------------------------------------:|:--------------------:|
| WZ (all)     | 2           | 0       | no relevant WC                                                                      | [1M WZ events](https://cmsweb.cern.ch/das/request?input=%2FWZ_rwgt_slc6_amd64_gcc630_CMSSW_9_3_0_tarball%2Fllechner-bg_dim6top_04June18-a4eb1cf113188459e4c517c4aa52c31c%2FUSER&instance=prod%2Fphys03) | 
| ttbar (all)  | 2           | 15      | ctp, ctpI, cpQM, cpQ3, cpt, cptb, cptbI, ctW, ctWI, ctZ, ctZI, cbW, cbWI, ctG, ctGI | [1M ttbar events](https://cmsweb.cern.ch/das/request?input=%2Ftt_rwgt_slc6_amd64_gcc630_CMSSW_9_3_0_tarball%2Fllechner-bg_dim6top_04June18-db4155f01c4c21dc10125760597b536e%2FUSER&instance=prod%2Fphys03) | 
  
  
### 18/05/2018  

| process  | poly order | # coeff | Wilson coefficients                                                                 | Link to gen. events |
|:--------:|:----------:|:-------:|:-----------------------------------------------------------------------------------:|:------------------------:|
| ttZ      | 2          | 15      | ctp, ctpI, cpQM, cpQ3, cpt, cptb, cptbI, ctW, ctWI, ctZ, ctZI, cbW, cbWI, ctG, ctGI | [1M ttZ events](https://cmsweb.cern.ch/das/request?input=%2FttZ0j_rwgt_slc6_amd64_gcc630_CMSSW_9_3_0_tarball%2Fllechner-ttZ0j_order2_15weights_18052018-7a5fde3f5bf89006ee3acec926ca87d8%2FUSER&instance=prod%2Fphys03)  |
| ttW      | 2          | 15      | ctp, ctpI, cpQM, cpQ3, cpt, cptb, cptbI, ctW, ctWI, ctZ, ctZI, cbW, cbWI, ctG, ctGI | [1M ttW events](https://cmsweb.cern.ch/das/request?input=%2FttW0j_rwgt_slc6_amd64_gcc630_CMSSW_9_3_0_tarball%2Fllechner-ttW0j_order2_15weights_18052018-593ea75549b4c51667dffc93040bbda1%2FUSER&instance=prod%2Fphys03)  |
| ttgamma  | 2          | 15      | ctp, ctpI, cpQM, cpQ3, cpt, cptb, cptbI, ctW, ctWI, ctZ, ctZI, cbW, cbWI, ctG, ctGI | [1M ttgamma events](https://cmsweb.cern.ch/das/request?input=%2Fttgamma0j_rwgt_slc6_amd64_gcc630_CMSSW_9_3_0_tarball%2Fllechner-ttgamma0j_order2_15weights_18052018-10fcfa1a1c01204983ea66975abf2caf%2FUSER&instance=prod%2Fphys03)  |
  
##### Reference Point (directory 18052018_ref)
Reference Point: ctW = 4., ctWI = 4., ctZ = 4., ctZI = 4., ctG = 4., ctGI = 4.  
  
| process  | poly order | # coeff | Wilson coefficients                                                                 | Link to gen. events |
|:--------:|:----------:|:-------:|:-----------------------------------------------------------------------------------:|:------------------------:|
| ttZ      | 2          | 15      | ctp, ctpI, cpQM, cpQ3, cpt, cptb, cptbI, ctW, ctWI, ctZ, ctZI, cbW, cbWI, ctG, ctGI | [1M ttZ events](https://cmsweb.cern.ch/das/request?input=%2FttZ0j_rwgt_slc6_amd64_gcc630_CMSSW_9_3_0_tarball%2Fllechner-ttZ0j_order2_15weights_18052018_ref-7a5fde3f5bf89006ee3acec926ca87d8%2FUSER&instance=prod%2Fphys03)  |
| ttW      | 2          | 15      | ctp, ctpI, cpQM, cpQ3, cpt, cptb, cptbI, ctW, ctWI, ctZ, ctZI, cbW, cbWI, ctG, ctGI | [1M ttW events](https://cmsweb.cern.ch/das/request?input=%2FttW0j_rwgt_slc6_amd64_gcc630_CMSSW_9_3_0_tarball%2Fllechner-ttW0j_order2_15weights_18052018_ref-593ea75549b4c51667dffc93040bbda1%2FUSER&instance=prod%2Fphys03)  |
| ttgamma  | 2          | 15      | ctp, ctpI, cpQM, cpQ3, cpt, cptb, cptbI, ctW, ctWI, ctZ, ctZI, cbW, cbWI, ctG, ctGI | [1M ttgamma events](https://cmsweb.cern.ch/das/request?input=%2Fttgamma0j_rwgt_slc6_amd64_gcc630_CMSSW_9_3_0_tarball%2Fllechner-ttgamma0j_order2_15weights_18052018_ref-10fcfa1a1c01204983ea66975abf2caf%2FUSER&instance=prod%2Fphys03)  |

  
  
### 07/05/2018  
| process  | poly order | # coeff | Wilson coefficients                        | Link to gen. events   |
|:--------:|:----------:|:-------:|:------------------------------------------:|:---------------------:|
| ttZ      | 2          | 8       | cpQM, cpt, ctW, ctWI, ctZ, ctZI, ctG, ctGI | not (yet) processed!  |
| ttW      | 2          | 8       | cpQM, cpt, ctW, ctWI, ctZ, ctZI, ctG, ctGI | not (yet) processed!  |
| ttgamma  | 2          | 8       | cpQM, cpt, ctW, ctWI, ctZ, ctZI, ctG, ctGI | not (yet) processed!  |
  
| process  | poly order | # coeff | Wilson coefficients                        | Link to gen. events |
|:--------:|:----------:|:-------:|:------------------------------------------:|:-------------------:|
| ttZ      | 3          | 8       | cpQM, cpt, ctW, ctWI, ctZ, ctZI, ctG, ctGI | [1M ttZ events](https://cmsweb.cern.ch/das/request?input=%2FttZ0j_rwgt_slc6_amd64_gcc630_CMSSW_9_3_0_tarball%2Fllechner-ttZ0j_order3_8weights-7a5fde3f5bf89006ee3acec926ca87d8%2FUSER&instance=prod%2Fphys03) |
| ttW      | 3          | 8       | cpQM, cpt, ctW, ctWI, ctZ, ctZI, ctG, ctGI | [1M ttW events](https://cmsweb.cern.ch/das/request?input=%2FttW0j_rwgt_slc6_amd64_gcc630_CMSSW_9_3_0_tarball%2Fllechner-ttW0j_order3_8weights-593ea75549b4c51667dffc93040bbda1%2FUSER&instance=prod%2Fphys03) |
| ttgamma  | 3          | 8       | cpQM, cpt, ctW, ctWI, ctZ, ctZI, ctG, ctGI | [1M ttgamma events](https://cmsweb.cern.ch/das/request?input=%2Fttgamma0j_rwgt_slc6_amd64_gcc630_CMSSW_9_3_0_tarball%2Fllechner-ttgamma0j_order3_8weights-10fcfa1a1c01204983ea66975abf2caf%2FUSER&instance=prod%2Fphys03) |  
  
### 03/05/2018  
##### Error in the pdfHandler!  

| process  | poly order | # coeff | Wilson coefficients                        | Link to gen. events   |
|:--------:|:----------:|:-------:|:------------------------------------------:|:---------------------:|
| ttZ      | 2          | 8       | cpQM, cpt, ctW, ctWI, ctZ, ctZI, ctG, ctGI | not (yet) processed!  |
| ttW      | 2          | 8       | cpQM, cpt, ctW, ctWI, ctZ, ctZI, ctG, ctGI | not (yet) processed!  |
| ttgamma  | 2          | 8       | cpQM, cpt, ctW, ctWI, ctZ, ctZI, ctG, ctGI | not (yet) processed!  |
  
| process  | poly order | # coeff | Wilson coefficients                        | Link to gen. events   |
|:--------:|:----------:|:-------:|:------------------------------------------:|:---------------------:|
| ttZ      | 3          | 8       | cpQM, cpt, ctW, ctWI, ctZ, ctZI, ctG, ctGI | not (yet) processed!  |
| ttW      | 3          | 8       | cpQM, cpt, ctW, ctWI, ctZ, ctZI, ctG, ctGI | not (yet) processed!  |
| ttgamma  | 3          | 8       | cpQM, cpt, ctW, ctWI, ctZ, ctZI, ctG, ctGI | not (yet) processed!  |
  
