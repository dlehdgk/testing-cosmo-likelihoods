# Cosmological Likelihoods for MCMC runs on COBAYA

This repository contains likelihood yaml blocks to be used in producing a yaml script for cosmological MCMC runs using the [COBAYA](https://cobaya.readthedocs.io/en/latest/) package.

## Usage

To use the likelihoods, install all the respective likelihood packages in the home directory of COBAYA and add the following line to the input yaml file:

```
likelihood: !defaults [path/to/likelihood1, path/to/likelihood2, ...]
```

## List of Likelihoods

- `act.yaml`: ACT DR6 likelihood [ACT-lite](https://github.com/ACTCollaboration/DR6-ACT-lite)
    - to be used for analysis using ACT DR6 as the only primary CMB measurement or in combination with WMAP

- `desi.yaml`: [DESI DR2 likelihood](https://github.com/CobayaSampler/bao_data)

- `lensing.yaml`: [ACT DR6 lensing likelihood](https://github.com/ACTCollaboration/act_dr6_lenslike) using a combination of the ACT DR6 and the Planck 2018 lensing data
    - to be used in conjunction with a primary CMB measurement (e.g. ACT DR6 or Planck 2018)

- `lowEE.yaml`: the low $\ell$ EE measurements from Planck 2018
    - to be used in conjunction with other CMB measurements to obtain the full likelihood combination spanning TT, TE and EE
    - for ACT, one can replace the low EE planck data with a gaussian prior on $\tau$

- `p_act.yaml`: contains a combination of Planck 2018 low $\ell$ TT; Planck 2018 high $\ell$ TT, TE and EE measurements truncated to specific maximum $\ell$ to extend the data to the ACT measured scales; ACT-lite for higher $\ell$
    - it must be used with low $\ell$ EE measurements

- `pantheon.yaml`: pantheon+ SNIa data

- `desy5.yaml`: DES Y5 SNIa data

- `planck.yaml`: Planck 2018 low $\ell$ TT and high $\ell$ TT, TE and EE measurements
    - must be used with a Planck 2018 low $\ell$ EE measurement

- `sroll2.yaml`: Planck 2018 low $\ell$ EE Sroll2 likelihood
    - can be used instead of the new gaussian prior on $\tau$ with ACT DR6
