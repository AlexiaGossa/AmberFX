# AmberFX
Natural cinematic camera shader for OBS, inspired by organic film-like color rendering.

This filter is inspired by the cinematic look of certain high-end cameras.
It was developed using the Sony IMX585 sensor, but it should be compatible with other sensors (like Sony IMX477) and camera (Sony FX3).

AmberFX uses obs-shaderfilter 2.6.0+ from exeldro (https://obsproject.com/forum/resources/obs-shaderfilter.1736/ or https://github.com/exeldro/obs-shaderfilter/)

## Processing
>     OBS
>       ↓
>       obs-shaderfilter
>         ↓
>         AmberFX
>           ↓
>           ReQuantification
>           ↓
>           Gamma correction
>           ↓
>           DeClipping
>           ↓
>           Film processing
>           ↓
>           Skin processing



**Re-quantization**  
- SNR improved from 4.46dB or +0.7bit on synthetic test patterns.
- SNR improved from 3.64dB or +0.6bit on real pictures.


**DeClipping**  
This process attempts to detect saturated and/or anomalous areas in order to correct chrominance errors.  
**Currently, this process has been disabled internally.**  
 

**Gamma correction**  
G4C gamma correction aims to make small variations in dark tones more visible without crushing the highlights.  


**Film control**  
The goal is to make the background and scenery look more natural, so that the visual experience is more pleasing.  
This processing does not affect skin tones.  


**Skin control**  
The processing of skin tones yields a more natural-looking image that also feels more lifelike and tactile.  
If the settings are excessive, the colors will appear washed out.  


## Parameters

### Dynamic Range  
`Normal 0-255` Use if your video source uses range from 0-255  
`Low 16-240` Use if your video source uses range from 16-240 (artefacts could appears if source is not 16-240)  
Default value is `Normal 0-255`  

### Gamma  
`2.0` use a gamma = 2.0  
`G4C` use a special gamma curve optimized for low and high luminance  
Default value is `G4C`  

### Gamma G4C HiLevel  
Vary from `0` to `100` : You could change the high luminance compensation.  
Original value for G4C is `91`  
Default value is `50`  

### ReQuanfifier  
`Enable` or `Disable` the ReQuantifier processing.  
Default value is `Enable`  

### DeClipping  
`Enable` or `Disable` the DeClipping processing.  
Default value is `Enable`  
**Note : The DeClipping is currently disabled internally.**  

### Film  
`Enable` or `Disable` the Film processing.  
Default value is `Enable`  

### Skin
`Enable` or `Disable` the Skin processing.  
Default value is `Enable`  

### Quantification
If used, try to recreate more bits from original source material.  
`Normal` Keep original quantification (no ReQuantification at all)  
`RGB ReQuantifier` Apply ReQuantifier on RGB components (if source is RGB only)  
`YCbCr ReQuantifier` Apply ReQuantifier on YCbCr components (if source is YCbCr only)  
`Check RGB ReQuant` Show effect on RGB ReQuantifier (use it to detect source mode - higher is better)  
`Check YCbCr ReQuant` Show effect on YCbCr ReQuantifier (use it to detect source mode - higher is better)  
Default is `RGB ReQuantifier`  

### ReQuant noise threshold
`Minimal` Apply original ReQuantifier  
`Low` Usefull with low noise video source  
`Medium` Usefull with medium noise video source  
`High` Usefull with high noise video source  
`Very high + Denoise` Add denoise effect  
`Absurd + Denoise` Totally silly denoise ! (just for testing and fun)  
Best results are observed with low noise input source and `Minimal` or `Low` value.  
Default is `Minimal`  

### Film lum/sat  
Desaturate high level of luminance.  
Vary from `0` to `100` : Compensation of saturation with high luminance level  
Default is `60`  

### Film over saturation  
Apply an over saturation on colors.  
Vary from `0` to `100` : Compensation of film over saturation  
Default is `80`  

### Film color temp  
Change the color temperature of image.  
`Neutral` No color temperature change.  
`Cold` Apply a 6500K to 9000K temperature change.  
`Warm` Apply a 6500K to 4000K temperature change.  
Default is `Neutral`  

### Skin processing
Vary from `0` to `100` : Hardness of skin processing.  
`0` No effect at all  
`100` Very hard and gray level  
Default is `25`  

### Advanced parameters

### Skin checker
`Normal` Normal skin processing mode  
`Show area` Allow you to show all detected and processed area (useful to set all parameters below)  

### SkinTone C_lo
`0.00` Minimal chroma value low threshold  
`0.01` Default chroma value low threshold  
`0.10` Maximal chroma value low threshold  

### SkinTone C_hi
`0.05` Minimal chroma value high threshold  
`0.12` Default chroma value high threshold  
`0.20` Maximal chroma value high threshold  

### SkinTone C_margin
`0.01` Minimal chroma value margin threshold  
`0.05` Default chroma value margin threshold  
`0.10` Maximal chroma value margin threshold  

### SkinTone h_lo
`0.05` Minimal hue value low threshold  
`0.10` Default hue value low threshold  
`0.50` Maximal hue value low threshold  

### SkinTone h_hi
`1.00` Minimal hue value high threshold  
`0.30` Default hue value high threshold  
`1.80` Maximal hue value high threshold  

### SkinTone h_margin
`0.01` Minimal hue value margin threshold  
`0.10` Default hue value margin threshold  
`0.30` Maximal hue value margin threshold  




