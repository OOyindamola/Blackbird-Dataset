# The Blackbird Dataset: A large-scale dataset for UAV perception in aggressive flight

<!-- [![Video Link](https://img.youtube.com/vi/_VBww8YQuA8/0.jpg)](https://www.youtube.com/watch?v=_VBww8YQuA8) -->

The Blackbird Dataset was created by the [AgileDrones group](http://agiledrones.mit.edu) at the [MIT FAST Lab](http://karaman.mit.edu/group.html) and will be published in the proceedings of ISER 2018.

## Preview the Dataset

| Constant Yaw Trajectories<br>*Click for preview video*                                        |||||||||
| :-----------: | :------: | :------: | :------: | :------: | :------: | :------: | :------: | :------: |
| Top speed (m/s) |   0.5  |   1.0    |   2.0    |   3.0    |   4.0    |   5.0    |   6.0    |   7.0    |
|  3D Figure 8  |    ✓     |     ✓    |    ✓     |    ✓     |    ✓     |    ✓     |    \-    |    \-    |
|   Ampersand   |    \-    | [✓][b10] | [✓][b20] | [✓][b30] |    \-    |    \-    |    \-    |    \-    |
|   Bent Dice   |    \-    | [✓][c10] | [✓][c20] | [✓][c30] | [✓][c40] |    \-    |    \-    |    \-    |
|    Clover     |    \-    | [✓][d10] | [✓][d20] | [✓][d30] | [✓][d40] | [✓][d50] | [✓][d60] |    \-    |
|     Dice      |    \-    |    \-    | [✓][e20] | [✓][e30] | [✓][e40] |    \-    |    \-    |    \-    |
| Flat Figure 8 |    ✓     |    ✓     |    ✓     |    ✓     |    \-    |    ✓     |    \-    |    \-    |
|   Half-Moon   |    \-    | [✓][g10] | [✓][g20] | [✓][g30] | [✓][g40] |    \-    |    \-    |    \-    |
|     Mouse     |    \-    | [✓][h10] | [✓][h20] | [✓][h30] | [✓][h40] | [✓][h50] | [✓][h60] | [✓][h70] |
|     Oval      |    \-    |    \-    | [✓][i20] | [✓][i30] | [✓][i40] |    \-    |    \-    |    \-    |
|    Patrick    |    \-    | [✓][j10] | [✓][j20] | [✓][j30] | [✓][j40] | [✓][j50] |    \-    |    \-    |
|    Picasso    | [✓][k05] | [✓][k10] | [✓][k20] | [✓][k30] | [✓][k40] | [✓][k50] | [✓][k60] |    \-    |
|      Sid      |    \-    | [✓][l10] | [✓][l20] | [✓][l30] | [✓][l40] | [✓][l50] | [✓][l60] | [✓][l70] |
|    Sphinx     |    \-    | [✓][m10] | [✓][m20] | [✓][m30] | [✓][m40] |    \-    |    \-    |    \-    |
|     Star      |    \-    | [✓][n10] | [✓][n20] | [✓][n30] | [✓][n40] | [✓][n50] |    \-    |    \-    |
|    Thrice     |    \-    | [✓][o10] | [✓][o20] | [✓][o30] | [✓][o40] | [✓][o50] | [✓][o60] | [✓][o70] |
| Tilted Thrice |    \-    | [✓][p10] | [✓][p20] | [✓][p30] | [✓][p40] | [✓][p50] | [✓][p60] | [✓][p70] |
|    Winter     |    \-    | [✓][q10] | [✓][q20] | [✓][q30] | [✓][q40] | [✓][q50] |    \-    |    \-    |

## Download the Dataset

```bash
# Clone this repo into your dataset destination folder
git clone https://github.com/AgileDrones/Blackbird-Dataset.git
cd Blackbird-Dataset
mkdir data

# Install python dependencies for included utilities
pip install -r requirements.txt

# EX: download subset of the dataset via HTTP/BitTorrent hybrid method (fastest)
./downloaderUtility.py downloadSubset flights='(trajectory in ["tiltedThrice"] and topSpeed >= 6.0)' files='["videoPreview", "bagfile"]' data/

# EX: download all preview videos of the dataset via HTTP/BitTorrent hybrid method (fastest).
# WARNING: total size of preview videos is 69GB. If you'd like to preview the dataset, please refer to the table above.
./downloaderUtility.py downloadSubset files='["videoPreview"]' data/


```
## Downloader Documentation

`./downloaderUtility.py downloadSubset flights='(python_boolean_expression)' files='[filetype_list]' <output_location>`

* Options for `files=[...]` (string):
    * `["videoPreview", "bagfile", "lcmLog", "Camera_L_Images","Camera_R_Images", "Camera_D_Images" ]`
    * NOTE: small supportive files (such as CSVs) will be automatically downloaded.

* Options for `flights=(...)` filter expression. Note: selects all flights by default.
    * `trajectory` (string) in `["3dFigure8", "ampersand", "bentDice", "clover", "dice", "figure8", "halfMoon", "mouse", "oval", "patrick", "picasso", "sid", "sphinx", "star", "thrice", "tiltedThrice", "winter"]`
    * `topSpeed` (m/s float) in `[0.5, 1.0, 2.0, 3.0, 4.0, 5.0, 6.0, 7.0]`
    * `difficulty` (string) in `["easy", "medium", "hard", "extreme"]`
    * `yawType` (string) in `["yawConstant", "yawForward"]`
    * `location` (string) in `["Ancient_Egypt_Museum_Room", "Small_Apartment", "Large_Apartment_Night_Near_Column", "Outdoor_Patio_Night", "Large_Apartment_Day_Near_Kitchen", "Large_Apartment_Night_Near_Couches", "Ancient_Asia_Museum_Room"]` # Useful for specifying environment to download for flights rendered in multiple environments.
    * `environment` (string) in `["Museum_Day", "Museum_Day_Small", "Butterfly_World", "Hazelwood_Loft_Full_Night", "Hazelwood_Loft_Full_Day", "NYC_Subway", "NYC_Subway_Station"]`

## Citation
If you find this work useful for your research, please cite:
```bibtex
@inproceedings{antonini2018blackbird,
  title={The Blackbird Dataset: A large-scale dataset for UAV perception in aggressive flight},
  author={Antonini, Amado and Guerra, Winter and Murali, Varun and Sayre-McCord, Thomas and Karaman, Sertac},
  booktitle={2018 International Symposium on Experimental Robotics (ISER)},
  year={2018}
}
```

<!-- Constant yaw trajectory preview links for table -->
[b10]: http://blackbird-dataset.mit.edu/data/ampersand/yawConstant/maxSpeed1p0/videos/
[b20]: http://blackbird-dataset.mit.edu/data/ampersand/yawConstant/maxSpeed2p0/videos/
[b30]: http://blackbird-dataset.mit.edu/data/ampersand/yawConstant/maxSpeed3p0/videos/

[c10]: http://blackbird-dataset.mit.edu/data/bentDice/yawConstant/maxSpeed1p0/videos/
[c20]: http://blackbird-dataset.mit.edu/data/bentDice/yawConstant/maxSpeed2p0/videos/
[c30]: http://blackbird-dataset.mit.edu/data/bentDice/yawConstant/maxSpeed3p0/videos/
[c40]: http://blackbird-dataset.mit.edu/data/bentDice/yawConstant/maxSpeed4p0/videos/

[d10]: http://blackbird-dataset.mit.edu/data/clover/yawConstant/maxSpeed1p0/videos/
[d20]: http://blackbird-dataset.mit.edu/data/clover/yawConstant/maxSpeed2p0/videos/
[d30]: http://blackbird-dataset.mit.edu/data/clover/yawConstant/maxSpeed3p0/videos/
[d40]: http://blackbird-dataset.mit.edu/data/clover/yawConstant/maxSpeed4p0/videos/
[d50]: http://blackbird-dataset.mit.edu/data/clover/yawConstant/maxSpeed5p0/videos/
[d60]: http://blackbird-dataset.mit.edu/data/clover/yawConstant/maxSpeed6p0/videos/

[e10]: http://blackbird-dataset.mit.edu/data/dice/yawConstant/maxSpeed1p0/videos/
[e20]: http://blackbird-dataset.mit.edu/data/dice/yawConstant/maxSpeed2p0/videos/
[e30]: http://blackbird-dataset.mit.edu/data/dice/yawConstant/maxSpeed3p0/videos/
[e40]: http://blackbird-dataset.mit.edu/data/dice/yawConstant/maxSpeed4p0/videos/

[g10]: http://blackbird-dataset.mit.edu/data/halfMoon/yawConstant/maxSpeed1p0/videos/
[g20]: http://blackbird-dataset.mit.edu/data/halfMoon/yawConstant/maxSpeed2p0/videos/
[g30]: http://blackbird-dataset.mit.edu/data/halfMoon/yawConstant/maxSpeed3p0/videos/
[g40]: http://blackbird-dataset.mit.edu/data/halfMoon/yawConstant/maxSpeed4p0/videos/

[h10]: http://blackbird-dataset.mit.edu/data/mouse/yawConstant/maxSpeed1p0/videos/
[h20]: http://blackbird-dataset.mit.edu/data/mouse/yawConstant/maxSpeed2p0/videos/
[h30]: http://blackbird-dataset.mit.edu/data/mouse/yawConstant/maxSpeed3p0/videos/
[h40]: http://blackbird-dataset.mit.edu/data/mouse/yawConstant/maxSpeed4p0/videos/
[h50]: http://blackbird-dataset.mit.edu/data/mouse/yawConstant/maxSpeed5p0/videos/
[h60]: http://blackbird-dataset.mit.edu/data/mouse/yawConstant/maxSpeed6p0/videos/
[h70]: http://blackbird-dataset.mit.edu/data/mouse/yawConstant/maxSpeed7p0/videos/

[i20]: http://blackbird-dataset.mit.edu/data/oval/yawConstant/maxSpeed2p0/videos/
[i30]: http://blackbird-dataset.mit.edu/data/oval/yawConstant/maxSpeed3p0/videos/
[i40]: http://blackbird-dataset.mit.edu/data/oval/yawConstant/maxSpeed4p0/videos/

[j10]: http://blackbird-dataset.mit.edu/data/patrick/yawConstant/maxSpeed1p0/videos/
[j20]: http://blackbird-dataset.mit.edu/data/patrick/yawConstant/maxSpeed2p0/videos/
[j30]: http://blackbird-dataset.mit.edu/data/patrick/yawConstant/maxSpeed3p0/videos/
[j40]: http://blackbird-dataset.mit.edu/data/patrick/yawConstant/maxSpeed4p0/videos/
[j50]: http://blackbird-dataset.mit.edu/data/patrick/yawConstant/maxSpeed5p0/videos/

[k05]: http://blackbird-dataset.mit.edu/data/picasso/yawConstant/maxSpeed0p5/videos/
[k10]: http://blackbird-dataset.mit.edu/data/picasso/yawConstant/maxSpeed1p0/videos/
[k20]: http://blackbird-dataset.mit.edu/data/picasso/yawConstant/maxSpeed2p0/videos/
[k30]: http://blackbird-dataset.mit.edu/data/picasso/yawConstant/maxSpeed3p0/videos/
[k40]: http://blackbird-dataset.mit.edu/data/picasso/yawConstant/maxSpeed4p0/videos/
[k50]: http://blackbird-dataset.mit.edu/data/picasso/yawConstant/maxSpeed5p0/videos/
[k60]: http://blackbird-dataset.mit.edu/data/picasso/yawConstant/maxSpeed6p0/videos/

[l10]: http://blackbird-dataset.mit.edu/data/sid/yawConstant/maxSpeed1p0/videos/
[l20]: http://blackbird-dataset.mit.edu/data/sid/yawConstant/maxSpeed2p0/videos/
[l30]: http://blackbird-dataset.mit.edu/data/sid/yawConstant/maxSpeed3p0/videos/
[l40]: http://blackbird-dataset.mit.edu/data/sid/yawConstant/maxSpeed4p0/videos/
[l50]: http://blackbird-dataset.mit.edu/data/sid/yawConstant/maxSpeed5p0/videos/
[l60]: http://blackbird-dataset.mit.edu/data/sid/yawConstant/maxSpeed6p0/videos/
[l70]: http://blackbird-dataset.mit.edu/data/sid/yawConstant/maxSpeed7p0/videos/

[m10]: http://blackbird-dataset.mit.edu/data/sphinx/yawConstant/maxSpeed1p0/videos/
[m20]: http://blackbird-dataset.mit.edu/data/sphinx/yawConstant/maxSpeed2p0/videos/
[m30]: http://blackbird-dataset.mit.edu/data/sphinx/yawConstant/maxSpeed3p0/videos/
[m40]: http://blackbird-dataset.mit.edu/data/sphinx/yawConstant/maxSpeed4p0/videos/

[n10]: http://blackbird-dataset.mit.edu/data/star/yawConstant/maxSpeed1p0/videos/
[n20]: http://blackbird-dataset.mit.edu/data/star/yawConstant/maxSpeed2p0/videos/
[n30]: http://blackbird-dataset.mit.edu/data/star/yawConstant/maxSpeed3p0/videos/
[n40]: http://blackbird-dataset.mit.edu/data/star/yawConstant/maxSpeed4p0/videos/
[n50]: http://blackbird-dataset.mit.edu/data/star/yawConstant/maxSpeed5p0/videos/

[o10]: http://blackbird-dataset.mit.edu/data/thrice/yawConstant/maxSpeed1p0/videos/
[o20]: http://blackbird-dataset.mit.edu/data/thrice/yawConstant/maxSpeed2p0/videos/
[o30]: http://blackbird-dataset.mit.edu/data/thrice/yawConstant/maxSpeed3p0/videos/
[o40]: http://blackbird-dataset.mit.edu/data/thrice/yawConstant/maxSpeed4p0/videos/
[o50]: http://blackbird-dataset.mit.edu/data/thrice/yawConstant/maxSpeed5p0/videos/
[o60]: http://blackbird-dataset.mit.edu/data/thrice/yawConstant/maxSpeed6p0/videos/
[o70]: http://blackbird-dataset.mit.edu/data/thrice/yawConstant/maxSpeed7p0/videos/

[p10]: http://blackbird-dataset.mit.edu/data/tiltedThrice/yawConstant/maxSpeed1p0/videos/
[p20]: http://blackbird-dataset.mit.edu/data/tiltedThrice/yawConstant/maxSpeed2p0/videos/
[p30]: http://blackbird-dataset.mit.edu/data/tiltedThrice/yawConstant/maxSpeed3p0/videos/
[p40]: http://blackbird-dataset.mit.edu/data/tiltedThrice/yawConstant/maxSpeed4p0/videos/
[p50]: http://blackbird-dataset.mit.edu/data/tiltedThrice/yawConstant/maxSpeed5p0/videos/
[p60]: http://blackbird-dataset.mit.edu/data/tiltedThrice/yawConstant/maxSpeed6p0/videos/
[p70]: http://blackbird-dataset.mit.edu/data/tiltedThrice/yawConstant/maxSpeed7p0/videos/

[q10]: http://blackbird-dataset.mit.edu/data/winter/yawConstant/maxSpeed1p0/videos/
[q20]: http://blackbird-dataset.mit.edu/data/winter/yawConstant/maxSpeed2p0/videos/
[q30]: http://blackbird-dataset.mit.edu/data/winter/yawConstant/maxSpeed3p0/videos/
[q40]: http://blackbird-dataset.mit.edu/data/winter/yawConstant/maxSpeed4p0/videos/
[q50]: http://blackbird-dataset.mit.edu/data/winter/yawConstant/maxSpeed5p0/videos/