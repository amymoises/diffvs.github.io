
# Diff-VS

- Diffusion-based vocal separation built on the EDM framework
- Achieves results on par with many discriminative models in both subjective and objective evaluations
- Requires as few as 7 steps to reach optimal performance

<br>
<br>

## Objective Evaluation

### Train and evaluate on MUSDB

| Model          | Type | Params | cSDR ↑   | 
|:-------------  |:-----|:------ |:------ |
| HDemucs [6]       | disc | 42 M   | 8.13   |
| TFC-TDF V3 [7]    | disc | 70 M   | 9.59   |
| BSRNN [5]         | disc | 37 M   | 10.01  |
| BS-RoFormer-6L [3] | disc | 72 M   | 10.66  |
| SCNet-L [2]       | disc | 42 M   | 10.86  |
| <span class="highlight-word">Diff-VS</span>     | <span class="highlight-word">gen</span> | <span class="highlight-word">57 M</span>    | <span class="highlight-word">10.12</span>  |


### Train on MUSDB + MoisesDB and evaluate on MUSDB

| Model          | Type | Params | cSDR ↑   | 
|:-------------  |:-----|:------ |:------ |
| SCNet-L [2]       | disc | 42 M   | 11.11  |
| SGMSEVS  [1]      | gen  | 65 M   | 8.63   |
|<span class="highlight-word">Diff-VS</span>         |<span class="highlight-word">gen</span> |<span class="highlight-word">57 M</span>    | <span class="highlight-word">10.88</span>   |

<br>
<br>

## Subjective Evaluation

We use MERT-MSE as our proxy subjective metrics [1]

| Model          | Type | Params | MERT MSE ↓ | 
|:-------------  |:-----|:------ |:------ |
| SCNet-L [2]       | disc | 42 M   | 0.096  |
| SGMSEVS  [1]      | gen  | 65 M   | 0.089  |
| Mel-Roformer [3] | disc | 105 M   | 0.071  |
| <span class="highlight-word">Diff-VS V2</span> |<span class="highlight-word">gen</span> | <span class="highlight-word">54 M</span> |<span class="highlight-word">0.083</span> |

<br>
<br>

## Listening Samples

Listening samples are randomly chosen from MUSDB test set

#### Little Chicago's Finest - My Own (**SDR 15.41**)

<div style="overflow-x: auto; width: 100%;" class="audio-row">
  <div style="display: flex; gap: 16px; min-width: max-content;">
    <div>
      <div>Mixture</div>
      <audio controls src="./assets/audio/groundtruth/Little Chicago's Finest - My Own_mix.wav"></audio>
    </div>
    <div>
      <div>Clean Vocals</div>
      <audio controls src="./assets/audio/groundtruth/Little Chicago's Finest - My Own_vocals.wav"></audio>
    </div>
    <div>
      <div>Diff-VS</div>
      <audio controls src="./assets/audio/v1/Little Chicago's Finest - My Own.wav"></audio>
    </div>
    <div>
      <div>Demucs</div>
      <audio controls src="./assets/audio/demucs/Little Chicago's Finest - My Own.wav"></audio>
    </div>
    <div>
      <div>SCNet</div>
      <audio controls src="./assets/audio/scnet/Little Chicago's Finest - My Own.wav"></audio>
    </div>
  </div>
</div>


#### PR - Happy Daze (**SDR -0.58**)

<div style="overflow-x: auto; width: 100%;" class="audio-row">
  <div style="display: flex; gap: 16px; min-width: max-content;">
    <div>
      <div>Mixture</div>
      <audio controls src="./assets/audio/groundtruth/PR - Happy Daze_mix.wav"></audio>
    </div>
    <div>
      <div>Clean Vocals</div>
      <audio controls src="./assets/audio/groundtruth/PR - Happy Daze_vocals.wav"></audio>
    </div>
    <div>
      <div>Diff-VS</div>
      <audio controls src="./assets/audio/v1/PR - Happy Daze.wav"></audio>
    </div>
    <div>
      <div>Demucs</div>
      <audio controls src="./assets/audio/demucs/PR - Happy Daze.wav"></audio>
    </div>
    <div>
      <div>SCNet</div>
      <audio controls src="./assets/audio/scnet/PR - Happy Daze.wav"></audio>
    </div>
  </div>
</div>


#### The Long Wait - Dark Horses (**SDR 11.62**)

<div style="overflow-x: auto; width: 100%;" class="audio-row">
  <div style="display: flex; gap: 16px; min-width: max-content;">
    <div>
      <div>Mixture</div>
      <audio controls src="./assets/audio/groundtruth/The Long Wait - Dark Horses_mix.wav"></audio>
    </div>
    <div>
      <div>Clean Vocals</div>
      <audio controls src="./assets/audio/groundtruth/The Long Wait - Dark Horses_vocals.wav"></audio>
    </div>
    <div>
      <div>Diff-VS</div>
      <audio controls src="./assets/audio/v1/The Long Wait - Dark Horses.wav"></audio>
    </div>
    <div>
      <div>Demucs</div>
      <audio controls src="./assets/audio/demucs/The Long Wait - Dark Horses.wav"></audio>
    </div>
    <div>
      <div>SCNet</div>
      <audio controls src="./assets/audio/scnet/The Long Wait - Dark Horses.wav"></audio>
    </div>
  </div>
</div>


#### Timboz - Pony (**SDR 5.2**)

<div style="overflow-x: auto; width: 100%;" class="audio-row">
  <div style="display: flex; gap: 16px; min-width: max-content;">
    <div>
      <div>Mixture</div>
      <audio controls src="./assets/audio/groundtruth/Timboz - Pony_mix.wav"></audio>
    </div>
    <div>
      <div>Clean Vocals</div>
      <audio controls src="./assets/audio/groundtruth/Timboz - Pony_vocals.wav"></audio>
    </div>
    <div>
      <div>Diff-VS</div>
      <audio controls src="./assets/audio/v1/Timboz - Pony.wav"></audio>
    </div>
    <div>
      <div>Demucs</div>
      <audio controls src="./assets/audio/demucs/Timboz - Pony.wav"></audio>
    </div>
    <div>
      <div>SCNet</div>
      <audio controls src="./assets/audio/scnet/Timboz - Pony.wav"></audio>
    </div>
  </div>
</div>

#### We Fell From The Sky - Not You (**SDR 8.44**)

<div style="overflow-x: auto; width: 100%;" class="audio-row">
  <div style="display: flex; gap: 16px; min-width: max-content;">
    <div>
      <div>Mixture</div>
      <audio controls src="./assets/audio/groundtruth/We Fell From The Sky - Not You_mix.wav"></audio>
    </div>
    <div>
      <div>Clean Vocals</div>
      <audio controls src="./assets/audio/groundtruth/We Fell From The Sky - Not You_vocals.wav"></audio>
    </div>
    <div>
      <div>Diff-VS</div>
      <audio controls src="./assets/audio/v1/We Fell From The Sky - Not You.wav"></audio>
    </div>
    <div>
      <div>Demucs</div>
      <audio controls src="./assets/audio/demucs/We Fell From The Sky - Not You.wav"></audio>
    </div>
    <div>
      <div>SCNet</div>
      <audio controls src="./assets/audio/scnet/We Fell From The Sky - Not You.wav"></audio>
    </div>
  </div>
</div>


<br>
<br>

## Teaser

Ongoing work on Diff-VS v2 can achieve on par results with BS-RoFormer and SCNet

### Train and evaluate on MUSDB

| Model          | Type | Params | cSDR ↑  | 
|:-------------  |:-----|:------ |:------|
| SCNet-L [2]       | disc | 42 M   | 10.86  |
| BS-RoFormer-12L [3]| disc | 93 M   | 11.49  |
| Mel-Roformer [4]  | disc | 105 M   | 12.08  |
|<span class="highlight-word">Diff-VS V2</span>        |<span class="highlight-word">gen</span>  | <span class="highlight-word">54 M</span>   |<span class="highlight-word">11.46</span>|

### Train with MoisesDB + MUSDB and evaluate on MUSDB

| Model          | Type | Params | cSDR ↑   | 
|:-------------  |:-----|:------ |:------ |
| SCNet-L [2]       | disc | 42 M   | 11.11  |
| SGMSEVS [1]       | gen  | 65 M   | 8.63   |
| <span class="highlight-word">Diff-VS V2</span>| <span class="highlight-word">gen</span>  |<span class="highlight-word">54 M</span>| <span class="highlight-word">11.85</span>|



#### Little Chicago's Finest - My Own 

<div style="overflow-x: auto; width: 100%;" class="audio-row">
  <div style="display: flex; gap: 16px; min-width: max-content;">
    <div>
      <audio controls src="./assets/audio/v2/Little Chicago's Finest - My Own.wav"></audio>
    </div>
  </div>
</div>

#### PR - Happy Daze 

<div style="overflow-x: auto; width: 100%;" class="audio-row">
  <div style="display: flex; gap: 16px; min-width: max-content;">
    <div>
      <audio controls src="./assets/audio/v2/PR - Happy Daze.wav"></audio>
    </div>
  </div>
</div>

#### The Long Wait - Dark Horses 

<div style="overflow-x: auto; width: 100%;" class="audio-row">
  <div style="display: flex; gap: 16px; min-width: max-content;">
    <div>
      <audio controls src="./assets/audio/v2/The Long Wait - Dark Horses.wav"></audio>
    </div>
  </div>
</div>

#### Timboz - Pony 

<div style="overflow-x: auto; width: 100%;" class="audio-row">
  <div style="display: flex; gap: 16px; min-width: max-content;">
    <div>
      <audio controls src="./assets/audio/v2/Timboz - Pony.wav"></audio>
    </div>
  </div>
</div>

#### We Fell From The Sky - Not You 
<div style="overflow-x: auto; width: 100%;" class="audio-row">
  <div style="display: flex; gap: 16px; min-width: max-content;">
    <div>
      <audio controls src="./assets/audio/v2/We Fell From The Sky - Not You.wav"></audio>
    </div>
  </div>
</div>

<br>
<br>

## Reference
[1] Bereuter, Paul A., et al., "Towards Reliable Objective Evaluation Metrics for Generative Singing Voice Separation Models", IEEE Workshop on Applications of Signal Processing to Audio and Acoustics (WASPAA), 2025.

[2] Tong, Weinan, et al. "Scnet: Sparse compression network for music source separation.", IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP), 2024.

[3] Lu, Wei-Tsung, et al. "Music source separation with band-split rope transformer.", IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP), 2024.

[4] Wang, Ju-Chiang, Wei-Tsung Lu, and Minz Won. "Mel-band roformer for music source separation." arXiv preprint arXiv:2310.01809.

[5] Luo, Yi, and Jianwei Yu. "Music source separation with band-split RNN." IEEE/ACM Transactions on Audio, Speech, and Language Processing 31 (2023): 1893-1901.

[6] Rouard, Simon, Francisco Massa, and Alexandre Défossez. "Hybrid transformers for music source separation.", IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP), 2023.

[7] Kim, Minseok, Jun Hyung Lee, and Soonyoung Jung. "Sound demixing challenge 2023 music demixing track technical report: Tfc-tdf-unet v3." arXiv preprint arXiv:2306.09382 (2023).
