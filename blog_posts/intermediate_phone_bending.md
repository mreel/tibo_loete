---
title: Intermediate Phone Bending
date: 2025-03-19
tags:
  - blog_post
  - apple
  - iphone
  - follow_up
author: Tibo Loete
---
<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-MML-AM_CHTML">
</script>
# Intermediate Phone Bending

After reading [Dr. Drang's post](https://leancrew.com/all-this/2025/03/simple-phone-bending/) about the 10% additional bending stress for the rumored iPhone Air if it was the plus size, I felt the analysis could go further. Rather than complain, why not do it myself? Unlike Dr. Drang, I'm not a structural engineer, but I did learn this stuff in uni a few years ago. Still, my knowledge is limited and a little rusty as I've never used it in real life, so I invite any criticism and corrections.  

Continuing from Dr. Drang's post, the peak moment is at the center of the 'beam' and is  

\\[M_{\text{max}} = \frac{P L}{4}\\]  

The relevant variable to consider whether or not bendgate will return is the maximum bending stress \\(σ_{\text{max}}\\) . Let's start with the current crop of iPhones, and then speculate about the rumoured Air.

## Current iPhones
Maximum bending stress is independent of material[^1], and the dimensions of the pro/non-pro phones are close enought to combine the calculations.

### Base & Pro
Dimensions (\\(h \times w \times d\\)):  
Base: \\(147.6mm \times 71.6mm \times 7.80mm\\)   
Pro: \\(149.6mm \times 71.5mm \times 8.25mm\\)  

For our calculations:  
\\(148.6mm \times 71.5mm \times 8mm = 0.1486m \times 0.0715m \times 0.008m\\)[^2]

For a force \\(P\\) at the midpoint of the base iPhone, the peak moment is:  
\\[M_{\text{max}} = \frac{P\times0.1486m}{4} = 0.03715m \times P\\]  
Bending stress is calculated using \\(σ_{\text{max}} = \frac{M}{S}\\). With \\(M\\) the moment and \\(S\\) the section modulus. This value is dependent on the shape of the cross section of the beam. In this case a rectangle and equals \\(S = \frac{b \times h^2}{6}\\). For our average iPhone that means:  
\\[S = \frac{b \times h^2}{6} = \frac{0.0715m \times 0.008^2m^2}{6} \approx 0.000000763m^3\\]  
With our maximum bending stress coming to:  
\\[σ_{\text{max}} = \frac{M}{S} = \frac{0.03715m  \times  P}{0.000000763m^3} \approx 4.87  \times  10^4 m^{-2}  \times  P\\]    

### Plus & Pro Max
Dimensions (\\(h \times w \times d\\)):  
Plus: \\(160.9mm \times 77.8mm \times 7.80mm\\)   
Pro Max: \\(163mm \times 77.6mm \times 8.25mm\\)  

For our calculations:  
\\(162mm \times 77.7mm \times 8mm = 0.162m \times 0.0777m \times 0.008m\\)  

Analogous to the previous section we can calculate the peak moment:  
\\[M_{\text{max}} = \frac{P \times 0.162m}{4} = 0.0405m  \times  P\\]  
The section modulus:  
\\[S = \frac{b \times h^2}{6} = \frac{0.0777m \times 0.008^2m^2}{6} \approx 0.000000829m^3\\]  
And the maximum bending stress:  
\\[σ_{\text{max}} = \frac{M}{S} = \frac{0.0405m  \times  P}{0.000000829m^3} \approx 4.89  \times  10^4 m^{-2}  \times  P\\]  

As it turns out, while the bigger phones do experience a higher peak moment, in this simplification it comes to a very similar maximum bending stress due to the added width.  
In practice, most of the strength comes from the frame which doesn't widen with the phone. If we assume an equal section modulus (bending resistance), Dr. Drang's estimate of bending stress increasing by ~10% is still spot on:  
\\[σ_{\text{max}} = \frac{M}{S} = \frac{0.0405m  \times  P}{0.000000763m^3} \approx 5.31  \times  10^4 m^{-2}  \times  P\\]  
\\[4.89  \times  1.1 = 5.38 \approx 5.31\\]  

## iPhone Air  
Dimensions (\\(h \times w \times d\\)):  
Air: \\(160.9mm \times 77.8mm \times 5.5mm = 0.1609m \times 0.0778m \times 0.0055m\\)  

The dimensions are based on the latest rumors about thickness and display size, and using the same aspect ratio as our average big phone.  

Analogous to the previous section we can calculate the peak moment:  
\\[M_{\text{max}} = \frac{P \times 0.1609m}{4} = 0.0402m  \times  P\\]  
As discussed previously, it makes more sense to use the width of the base phones as a proxy for strength as the structural frame provides most of the bending resistance, which doesn't scale linearly with a bigger phone:
\\[S = \frac{b \times h^2}{6} = \frac{0.0715m \times 0.0055^2m^2}{6} \approx 0.000000361m^3\\]  
And the maximum bending stress:  
\\[σ_{\text{max}} = \frac{M}{S} = \frac{0.0402m  \times  P}{0.000000361m^3} \approx 11.1  \times  10^4 m^{-2}  \times  P\\]  
\\[11.1/5.31= 2.09 \quad | \quad 11.1/4.89= 2.27\\]  

## Conclusion  
As rumored, if the iPhone air has a similar internal frame, it would experience about twice the peak bending stress as the big phones, and ~x2.25 the bending stress of the base phones for an equal force applied at the center of the phone —and thus bend at half the force applied.  

### What does this mean?
As Dr. Drang noted, the phone size alone doesn't make a huge difference. However, since the thinness of the phone does make a huge difference, that extra 10% could be the difference between "bendgate is a not really a concern" and "bendgate is a big concern".  

All in all this was just a bit of fun for me, dusting off my math skills while killing a bit of time. There’s only so much reading, music, and podcast listening I can do on Southeast Asian buses —this was a nice change of pace.

[^1]: I imagine a titanium vs aluminum frame matters a fair bit.

[^2]: Converting mm to m makes the numbers less pretty but means we don't need to worry about units.
