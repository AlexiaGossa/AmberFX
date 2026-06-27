# AmberFX
Natural cinematic camera shader for OBS, inspired by organic film-like color rendering.

This filter is inspired by the cinematic look of certain high-end cameras.
It was developed using the Sony IMX585 sensor, but it should be compatible with other sensors.

Work-in-progress !
The filter is not optimized but runs perfect.

Internal processing
- Re-quantization
- De-clipping correction
- Gamma correction (Gamma 2.0 or G4C)
- Skin saturation control
- Film saturation control


Re-quantization
- SNR improved from 4.46dB or 0.7bit on synthetic test patterns.
- SNR improved from 3.64dB or +0.6bit on real pictures.


## Parameters

### Gamma
"2.0" use a gamma = 2.0  
"G4C" use a special gamma curve optimized for low and high luminance  

### Quantification
If used, try to recreate more bits from original source data.  
"Normal" Keep original quantification (no ReQuantification at all)  
"RGB ReQuantifier" Apply ReQuantifier on RGB components (if source is RGB only)  
"YCbCr ReQuantifier" Apply ReQuantifier on YCbCr components (if source is YCbCr only)  
"Check RGB ReQuant" Show effect on RGB ReQuantifier (use it to detect source mode - higher is better)  
"Check YCbCr ReQuant" Show effect on YCbCr ReQuantifier (use it to detect source mode - higher is better)  

### ReQuant noise threshold
"Minimal" Apply original ReQuantifier  
"Low" Usefull with low noise video source  
"Low" Usefull with low noise video source  
"Medium" Usefull with medium noise video source  
"High" Usefull with high noise video source  
"Very high + Denoise" Add denoise effect  
"Absurd + Denoise" Totally silly denoise !  

### Dynamic Range
"Normal 0-255" Use if your video source uses range from 0-255  
"Low 16-240" Use if your video source uses range from 16-240  

### Film lum/sat
Desaturate high level of luminance.
"0.00" No effect at all  
"0.20" Default value  
"1.00" Maximal effect (desature more high luminance)  

### Skin processing
Hardness of skin processing.
"0.00" No effect at all  
"0.30" Default value  
"1.00" Very hard and gray level  

### Skin checker
"Normal" Normal processing mode  
"Show area" Allow you to show all detected and processed area (useful to set all parameters below)  

### SkinTone C_lo
"0.00" Minimal chroma value low threshold  
"0.01" Default chroma value low threshold  
"0.10" Maximal chroma value low threshold  

### SkinTone C_hi
"0.05" Minimal chroma value high threshold  
"0.12" Default chroma value high threshold  
"0.20" Maximal chroma value high threshold  

### SkinTone C_margin
"0.01" Minimal chroma value margin threshold  
"0.05" Default chroma value margin threshold  
"0.10" Maximal chroma value margin threshold  

### SkinTone h_lo
"0.05" Minimal hue value low threshold  
"0.10" Default hue value low threshold  
"0.50" Maximal hue value low threshold  

### SkinTone h_hi
"1.00" Minimal hue value high threshold  
"0.30" Default hue value high threshold  
"1.80" Maximal hue value high threshold  

### SkinTone h_margin
"0.01" Minimal hue value margin threshold  
"0.10" Default hue value margin threshold  
"0.30" Maximal hue value margin threshold  




