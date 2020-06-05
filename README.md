# Late Sodium 

This code is an investigation of the effect of late sodium current on action potential duration and EAD formation in LQT2 myocytes, described in:

* Late INa blocker GS967 Reduced Early Afterdepolarization and Polymorphic VT in a Transgenic Rabbit Model of Long QT Type 2 Jungmin Hwang, Tae Yun Kim, Dmitry Terentyev, Mingwang Zhong, Anatoli Kabakov, Karuppiah Arunachalam, Luiz Belardinelli, Sridharan Rajamani, Yukiko Kunitomo, Zachary Pfeiffer, Yichun Lu, Xuwen Peng, Katja Odening, Zhilin Qu, Alain Karma, Gideon Koren, Bum-Rak Choi (2018)

This code is based on an earlier implementation of a similar model described in:

* Restrepo, J. G., Weiss, J. N., & Karma, A. (2008). Calsequestrin-mediated mechanism for cellular calcium transient alternans. *Biophysical journal*, 95(8), 3767-3789.
* Terentyev, D., Rees, C. M., Li, W., Cooper, L. L., Jindal, H. K., Peng, X., ... & Bist, K. (2014). Hyperphosphorylation of RyRs underlies triggered activity in transgenic rabbit model of LQT2 syndrome. *Circulation research*, 115(11), 919-928.
* Zhong, Mingwang, Colin M. Rees, Dmitry Terentyev, Bum-Rak Choi, Gideon Koren, and Alain Karma. "NCX-mediated subcellular Ca2+ dynamics underlying early afterdepolarizations in LQT2 cardiomyocytes." *Biophysical journal* 115, no. 6 (2018): 1019-1032.

This software is free software, distributed under the 2-clause BSD license. A copy of the license is included in the LICENSE file.
We cordially ask that any published work derived from this code, or utilizing it references the above-mentioned published works.

## Implementation
#### Compile the code
```
nvcc cell.cu -O3 -lm -arch sm_30  -o cell -w
```

#### Run the code

LQT2 myocyte with normal I<sub>NaL</sub> at [Na<sup>+</sup>]<sub>i</sub> = 10.75 mM:
```
./cell  0  0.08  486 1 10.8 0.34 1.17 0.01
```

LQT2 myocyte with fully blocked I<sub>NaL</sub> at [Na<sup>+</sup>]<sub>i</sub> = 5.34 mM:
```
./cell  0  0.08  374 1 5.2 0.34 1.17 0
```

### Results
The above two sets of parameters produce the thick blue and thin red lines in the following figure.

![Alt text](Figure6.pdf)

<object data="Figure6.pdf" type="application/pdf" width="700px" height="700px">
    <embed src="Figure6.pdf">
        <p>This browser does not support PDFs. Please download the PDF to view it: <a href="Figure6.pdf">Download PDF</a>.</p>
    </embed>
</object>
