
# Diff-VS

- Diffusion-based vocal separation built on the EDM framework
- Achieves results on par with many discriminative models in both subjective and objective evaluations
- Requires as few as 7 steps to reach optimal performance

<br>
<br>

## Objective Evaluation

### Train and evaluate on MUSDB

| Model          | Type | Params | cSDR   | 
|:-------------  |:-----|:------ |:------ |
| HDemucs        | disc | 42 M   | 8.13   |
| TFC-TDF V3     | disc | 70 M   | 9.59   |
| BSRNN          | disc | 37 M   | 10.01  |
| BS-RoFormer-6L | disc | 72 M   | 10.66  |
| SCNet-L        | disc | 42 M   | 10.86  |
| <span class="highlight-word">Diff-VS</span>     | <span class="highlight-word">gen</span> | <span class="highlight-word">57 M</span>    | <span class="highlight-word">10.12</span>  |


### Train on MUSDB + MoisesDB and evaluate on MUSDB

| Model          | Type | Params | cSDR   | 
|:-------------  |:-----|:------ |:------ |
| SCNet-L        | disc | 42 M   | 11.11  |
| SGMSEVS        | gen  | 65 M   | 8.63   |
|<span class="highlight-word">Diff-VS</span>         |<span class="highlight-word">gen</span> |<span class="highlight-word">57 M</span>    | <span class="highlight-word">10.88</span>   |

<br>
<br>

## Subjective Evaluation

We use MERT-MSE as our proxy subjective metrics

| Model          | Type | Params | MERT MSE ↓ | 
|:-------------  |:-----|:------ |:------ |
| SCNet-L        | disc | 42 M   | 0.096  |
| SGMSEVS        | gen  | 65 M   | 0.089  |
| Mel-Roformer。 | disc | 105 M   | 0.071  |
| <span class="highlight-word">Diff-VS V2</span> |<span class="highlight-word">gen</span> | <span class="highlight-word">54 M</span> |<span class="highlight-word">0.083</span> |

<br>
<br>

## Listening Samples

Separated stems from MUSDB

- Enda Reilly - Cur An Long Ag Seol (**SDR 17.01**)
<div class="audio-row">
<audio controls><source src="./assets/audio/v1/Enda Reilly - Cur An Long Ag Seol.wav" type="audio/wav"></audio> 
</div>

- Little Chicago's Finest - My Own (**SDR 15.41**)
<div class="audio-row">
<audio controls><source src="./assets/audio/v1/Little Chicago's Finest - My Own.wav" type="audio/wav"></audio> 
</div>

- PR - Happy Daze (**SDR -0.58**)
<div class="audio-row">
<audio controls><source src="./assets/audio/v1/PR - Happy Daze.wav" type="audio/wav"></audio> 
</div>

- The Long Wait - Dark Horses (**SDR 11.62**)
<div class="audio-row">
<audio controls><source src="./assets/audio/v1/The Long Wait - Dark Horses.wav" type="audio/wav"></audio> 
</div>

- Timboz - Pony (**SDR 5.2**)
<div class="audio-row">
<audio controls><source src="./assets/audio/v1/Timboz - Pony.wav" type="audio/wav"></audio> 
</div>

- We Fell From The Sky - Not You (**SDR 8.44**)
<div class="audio-row">
<audio controls><source src="./assets/audio/v1/We Fell From The Sky - Not You.wav" type="audio/wav"></audio> 
</div>

<br>
<br>

## Teaser

Ongoing work on Diff-VS v2 can achieve on par results with BS-RoFormer and SCNet

### Train and evaluate on MUSDB

| Model          | Type | Params | cSDR   | 
|:-------------  |:-----|:------ |:------|
| SCNet-L        | disc | 42 M   | 10.86  |
| BS-RoFormer-12L| disc | 93 M   | 11.49  |
| Mel-Roformer   | disc | 105 M   | 12.08  |
|<span class="highlight-word">Diff-VS V2</span>        |<span class="highlight-word">gen</span>  | <span class="highlight-word">54 M</span>   |<span class="highlight-word">11.46</span>|

### Train with MoisesDB + MUSDB and evaluate on MUSDB

| Model          | Type | Params | cSDR   | 
|:-------------  |:-----|:------ |:------ |
| SCNet-L        | disc | 42 M   | 11.11  |
| SGMSEVS        | gen  | 65 M   | 8.63   |
| <span class="highlight-word">Diff-VS V2</span>| <span class="highlight-word">gen</span>  |<span class="highlight-word">54 M</span>| <span class="highlight-word">11.85</span>|


