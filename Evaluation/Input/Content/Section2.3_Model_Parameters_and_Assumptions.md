### Absorption <a id="model-parameters-and-assumptions-absorption"></a>

LNG administration was further expanded by incorporating
aqueous solubility, intestinal permeability, and drug dissolution
to simulate LNG exposure after oral administration. The permeability of LNG (`specific intestinal permeability`), and dissolution-related parameters were optimized by comparing model prediction with observed plasma PK data following oral administration. Dissolution was implemented with Lint80 or Weibull dissolution parameters depending on the formulation used in each study (`T80%` ot `T50%`, `dissolution shape`, `dissolution time` and/or `lag time`).

### Distribution <a id="model-parameters-and-assumptions-distribution"></a>

Unbound fraction (fu) was described with a specific binding process of levonogestrel to albumin and sex-hormone binding globulin (SHBG) as binding partners. Protein binding parameters (`Kd` and `Koff`) for albumin and SHBG were estimated by optimizing the model to subject-level data following IV administration of 0.09 mg of levonogestrel-only contraceptive to 18 women ([Cicali 2021](#main-references)).

Systemic levels of albumin and SHBG were based on the built-in expressed sequence tags database and on the clinical results
by [Kuhnz 1994](#main-references).

After testing the available organ-plasma partition coefficient and cell permeability calculation methods built in PK-Sim, observed clinical data was best described by choosing the partition coefficient calculation by `Rodgers and Rowland` and cellular permeability calculation by `PK-Sim Standard`. 

### Metabolism and Elimination <a id="model-parameters-and-assumptions-metabolism-and-elimination"></a>

The contribution of CYP3A4 to unbound levonogestrel hepatic
clearance was back-calculated from a clinical DDI study
comparing the systemic exposure of a combined levonorgestrel and ethynilestradiol (LNG-EE)
contraceptive administered with and without the strong
CYP3A4 inhibitor telithromycin (i.e., net levonogestrel fraction metabolized by CYP3A4 when administered in combination with Ethinylestradiol). However, levonogestrel metabolic clearance was estimated to be ~ 30% lower for the Levonogestrel and Ethynilestradiol combined hormonal therapy compared with levonogestrel-only formulations. Only a fraction of the levonogestrel metabolic pathway (70%) was subject to a subsequent interaction with a second strong CYP3A4 inhibitor, namely telithromycin ([Cicali 2021](#main-references)). Thus, the back calculated area under the concentration-time curve ratio (AUCR) resulting from the concomitant interaction on LNG exposure (i.e., eethynilestradiol and telithromycin) would be 2.1 (i.e., AUCR/0.7), which is equivalent to an levonogestrel fraction metabolized by CYP3A4 of 47%. Given the lack of mechanistic information, the current model lumps the contribution of phase II enzymes to levonogestrel into a nonspecific hepatic clearance ([Cicali 2021](#main-references)). The simulated levonogestrel fraction metabolized by CYP3A4 (fmCYP3A4) was verified by comparing to published clinical DDI studies. Relative tissue distribution of CYP3A4 implemented into the model was loaded from the 'PK-Sim® Ontogeny Database Version 7.3' (PK-Sim Ontogeny Database Version 7.3) using RT-PCR as data source. 
Both `CYP3A4 CLspec/[enzyme]` and `Plasma Clearance` were optimized against Cicali et al datasets [Cicali 2021](#main-references) . 

### Observer for Levonogestrel concentrations <a id="model-parameters-and-assumptions-parameter-observer"></a>

LNG concentrations in peripheral venous blood plasma at any specific time points were obtained by adding the simulated concentrations of LNG, LNG bound to SHBG, and LNG bound to albumin, at the corresponding time points to generate the LNG PK profiles, according to the following formula:

fQ_art*(C_pls_art+C_pls_art_ALB+C_pls_art_SHBG)+fQ_bon*(C_pls_bon+C_pls_bon_ALB+C_pls_bon_SHBG)+fQ_fat*(C_pls_fat+C_pls_fat_ALB+C_pls_fat_SHBG)+fQ_mus*(C_pls_mus+C_pls_mus_ALB+C_pls_mus_SHBG)+fQ_skn*(C_pls_skn+C_pls_skn_ALB+C_pls_skn_SHBG)

### Automated Parameter Identification <a id="model-parameters-and-assumptions-parameter-identification"></a>

This is the result of the final parameter identification.

| Model Parameter      | 
| -------------------- | 
| `logP` | 
| `CYP3A4 CLspec/[enzyme]` |     
| `Plasma Clearance` |      
| `Kd Albumin` |         
| `koff Albumin` |    
| `Dissolution T80%` |  
| `Dissolution T50%` |  
| `Dissolution shape` |  
| `Lag Time` |  


