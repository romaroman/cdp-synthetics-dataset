### [Download link](https://sipcloud.unige.ch/index.php/s/r5jawqmpqXW8bnF)

### Dataset description

This dataset was created in a scope of the project related to the publication R. Chaban et al., "*Assessing the Viability of Synthetic Physical Copy Detection Patterns on Different Imaging Systems*" in Proc. 16th IEEE WIFS, Roma, Italy, 2024.
This dataset contains only postprocessed versions of images, aligned with respect to the digital template and cropped. The original images may be available upon request.

### Dataset structure

> tree . -L 4


.
├── fake_phone
│   ├── HPI55_printrun1_session2_InvercoteG_EHPI76
│   │   ├── iPhone12Pro_LAB_run1_scale3_wide_2x_RC_office
│   │   │   └── rcod
│   │   │   ...
│   │   └── iPhoneXS_LAB_run1_scale3_wide_2x_RC_office
│   │       └── rcod
│   └── HPI76_printrun1_session2_InvercoteG_EHPI55
│       ├── iPhone12Pro_LAB_run1_scale3_wide_2x_RC_office
│       │   └── rcod
│       │   ...
│       └── iPhoneXS_LAB_run1_scale3_wide_2x_RC_office
│           └── rcod
├── fake_scan
│   ├── HPI55_printrun1_session0_InvercoteG_EHPI76
│   │   └── EpsonV850_run1_scandpi2400_scale3
│   │       └── rcod
│   │       ...
│   └── HPI76_printrun1_session2_InvercoteG_EHPI55
│       └── EpsonV850_run2_scandpi2400_scale3
│           └── rcod
│           ...
├── orig_phone
│   ├── HPI55_printrun1_session2_InvercoteG
|   |   ...
│   └── HPI76_printrun1_session2_InvercoteG
│       ....
└── orig_scan
    ├── HPI55_printrun1_session0_InvercoteG
    |   ...
    └── HPI76_printrun1_session2_InvercoteG
        ...


#### 0th level
In root directory there are 5 folders:
 - `orig_scan` - contains scans of original CDP acquired with Epson V850 scanner;
 - `fake_scan` - contains scans of fakes;
 - `orig_phone` - contains photos of original CDP acquired with different smartphones;
 - `fake_phone` - contains photos of fakes;
 - `orig_templates` are self-explanatory, they are digital templates of CDPs used for printing originals.

#### 1st level
In each directory of the 0th level there are subdirectories of manufacturing, each corresponds to actual physical set of samples.
The name of subdirectory consists of 4 (or 5 if fake) terms separated by `_`. Their names can be decoded as following:
 - 1st term is the name of the printer used to print the CDP (e.g. `HPI76`);
 - 2nd term is the print run number, putting it simply - number of physical copy (e.g. `printrun1`);
 - 3rd term is the session number, the arbitrary timepoint of printing (e.g. `session2`);
 - 4th term is the type of printing substrate (e.g. `InvercoteG`);
 - if it is a directory with fakes then 5th term is the name of the printer used for estimation of digital template before printing them (e.g. `EHPI55`).

#### 2nd level
In each directory of the 1st level there are subdirectories of acquisition, each corresponds to the instance of acquisition of the same set of samples. The naming is more complicated, but the important information is present in the following terms:
 - 1st term is the name of acquisition device (e.g. `EpsonV850` or `iPhoneXS`);
 - term with keyword `run` is the order of acquisition;
 - term with keyword `scale` is the scale of acquired CDP with respect to digital template (e.g. `scale3` means that area `3x3` pixels in photo approximately corresponds to `1x1` pixel in digital template);
 - term with keywords `wide` or `uwide` denote the used camera module, respectively wide or ultra-wide (macro);
 - term with suffix `x` denotes the digital zoom used during acquisition (e.g. `x1` means no zoom and `x2.5` means 2.5x digital zoom);


#### 3rd level
This level simply contains 1 directory named `rcod`.

#### 4th level
This level contains many subdirectories, each named after CDP unique identifier. Each subdirectory contains images of the same CDP acquired *N* times.