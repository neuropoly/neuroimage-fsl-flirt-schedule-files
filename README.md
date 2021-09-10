# Schedule files to use with FSL FLIRT

The file `schedule_TxTy.sch` is the schedule file referenced by the following passage from [Duval, Tanguy et al. “In vivo mapping of human spinal cord microstructure at 300mT/m.”](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4562035/#idm139707147392480title):

> ## 2. Preprocessing
> 
> ### Eddy-current correction
> 
> Reversed-gradients technique was used for correcting eddy-current artifacts (Bodammer et al., 2004). This technique consists of estimating the transformation between two images acquired with opposite diffusion gradient directions. To improve accuracy, each slice was corrected independently, assuming only rigid transformation (Tx, Ty). No scaling or shearing was estimated, which, to our preliminary data, was a satisfactory assumption, given that the spinal cord occupies a relatively small region (~1×1 cm2), and hence is minimally affected by transformations that scales with X and Y. The slice-wise correction was preferred to the volume-based correction because the amplitude of eddy-current artifacts varied along Z, yielding non-rigid deformations. _**Transformations were estimated with FSL FLIRT (Jenkinson et al., 2002), using a custom-made schedule file [1]**_. A 2D Gaussian mask centered on the spinal cord was used as a weighting mask in order to register the spinal cord independently from the rest of the body (e.g., surrounding muscles, fat). All transformations were then saved (for final combination with motion correction transformations) and applied (for estimating motion correction, see below).
>
> ### Motion Correction
>
> _**After correcting for eddy-current distortions, subject motion was estimated on a slice-by-slice basis using the same schedule file as before (Tx, Ty) and the same Gaussian mask.**_ Contrary to previous studies (Cohen-Adad et al., 2008), interspersed b=0 images were not used to estimate subject motion, because CSF flow affected some b=0 images differently and hence could have introduced spurious motion correction parameters. Instead, motion was estimated based on the diffusion-weighted images that ranged between b-values of 430 s/mm2 and b-values of 4000 s/mm2. These values were empirically chosen so that images presented sufficient SNR and no visible CSF contamination (see Figure 3). The first image was used as the reference image for registration (i.e., target image).
