# Camera calibration

This directory contains all calibration information for all cameras. All calibration has been generated with the opencv interactive calibration tool.

# Camera short overview list

This short list shows the calibration image size as well as the horizontal and vertical field of view of the corresponding camera. The field fx and fy are the focal lenght in both directions. 

                                   fx(px)     fy(px)      w(px)      h(px)  hfov(deg)  vfov(deg)
                       asus_c3  1045.0708  1044.9687       1920       1080      85.14      54.66 
                  aukey_pclm1e   978.6417   979.3902       1920       1080      88.90      57.74 
         conceptronic_amdis01B  1488.0650  1483.8750       1920       1080      65.65      39.99 
               elp_imx323+l297   612.4551   612.4551        800        600      66.30      52.19 
                    elp_mi5100  1443.5338  1452.2412       1920       1080      67.25      40.79 
               elp_mi5100+l100  1406.2382  1406.2382       2592       1944      85.33      69.30 
               elp_ov2710+h100   878.8000   878.8000       1920       1080      95.06      63.14 
               elp_ov2710+l297   940.5104   940.5104       1920       1080      91.18      59.73 
                     hama_c400  1491.5200  1491.8889       1920       1080      65.53      39.80 
                    hbv_ov2710   512.8428   512.8428        640        480      63.93      50.16 
                    hbv_ov9726  1006.2060  1006.2060       1280        800      64.92      43.36 
                   hyrican_dw1  1482.2573  1485.0318       1920       1080      65.86      39.97 
                   lincplus_c2  1118.0350  1118.2167       1920       1080      81.30      51.55 
                 logitech_c270  1351.1073  1353.6436       1280        960      50.69      39.05 
                 logitech_c920  1443.3697  1443.7168       1920       1080      67.26      41.02 
      logitech_quickcampro9000  1332.5822  1341.9257       1600       1200      61.96      48.18 
                   rapoo_xw170   691.2141   692.4286        640        480      49.68      38.23 
                  trust_fullhd  1881.7104  1881.7875       1920       1080      54.06      32.02 
                  trust_hd720p  1124.4064  1125.3102       1280        720      59.30      35.48 
                unknown_ov9732   729.4472   731.1125       1280        720      82.53      52.43 
                  victure_sc30  1037.7980  1037.4769       1920       1080      85.54      54.99 
                 xlayer_fullhd  1725.1031  1725.8725       1920       1080      58.19      34.75 


# Overview images

As quick impression here is an overview of the cameras with hardware default settings. The images are captured in similar but not identical conditions. They are illuminated by a Target Corona.

<table>
  <tr>
    <th>Name</th>
    <th>Automatic Image</th>
    <th>Manual Image</th>
    <th>Camera Image</th>
  </tr>
  <tr>
    <td>elp_mi5100+l100_000<br>recommended<br>15fps at max resolution</td>
    <td><img src="./elp_mi5100+l100_000/auto.jpg" alt="image" width="auto" height="120"></td>
    <td><img src="./elp_mi5100+l100_000/manual.jpg" alt="image" width="auto" height="120"></td>
    <td><img src="./elp_mi5100+l100_000/front.jpg" alt="image" width="auto" height="120"></td>
  </tr>
  <tr>
    <td>hbv_ov2710_000<br>not recommended<br>manual mode not working</td>
    <td><img src="./hbv_ov2710_000/auto.jpg" alt="image" width="auto" height="120"></td>
    <td><img src="./hbv_ov2710_000/manual.jpg" alt="image" width="auto" height="120"></td>
    <td><img src="./hbv_ov2710_000/front.jpg" alt="image" width="auto" height="120"></td>
  </tr>
  <tr>
    <td>elp_imx323+l297_000<br>recommended</td>
    <td><img src="./elp_imx323+l297_000/auto.jpg" alt="image" width="auto" height="120"></td>
    <td><img src="./elp_imx323+l297_000/manual.jpg" alt="image" width="auto" height="120"></td>
    <td><img src="./elp_imx323+l297_000/front.jpg" alt="image" width="auto" height="120"></td>
  </tr>
  <tr>
    <td>hbv_ov9726_000<br>recommended</td>
    <td><img src="./hbv_ov9726_000/auto.jpg" alt="image" width="auto" height="120"></td>
    <td><img src="./hbv_ov9726_000/manual.jpg" alt="image" width="auto" height="120"></td>
    <td><img src="./hbv_ov9726_000/front.jpg" alt="image" width="auto" height="120"></td>
  </tr>
  <tr>
    <td>elp_ov2710+l297_000<br>recommended</td>
    <td><img src="./elp_ov2710+l297_000/auto.jpg" alt="image" width="auto" height="120"></td>
    <td><img src="./elp_ov2710+l297_000/manual.jpg" alt="image" width="auto" height="120"></td>
    <td><img src="./elp_ov2710+l297_000/front.jpg" alt="image" width="auto" height="120"></td>
  </tr>
  <tr>
    <td>elp_ov2710+h100_000<br>recommended</td>
    <td><img src="./elp_ov2710+h100_000/auto.jpg" alt="image" width="auto" height="120"></td>
    <td><img src="./elp_ov2710+h100_000/manual.jpg" alt="image" width="auto" height="120"></td>
    <td><img src="./elp_ov2710+h100_000/front.jpg" alt="image" width="auto" height="120"></td>
  </tr>
  <tr>
    <td>trust_hd720p_000<br>recommended</td>
    <td><img src="./trust_hd720p_000/auto.jpg" alt="image" width="auto" height="120"></td>
    <td><img src="./trust_hd720p_000/manual.jpg" alt="image" width="auto" height="120"></td>
    <td><img src="./trust_hd720p_000/front.jpg" alt="image" width="auto" height="120"></td>
  </tr>
</table>






