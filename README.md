# postcards-from-my-jungle

1. The Name: Aetherfauna
Aether (in Latin, ether in English) was considered the fifth element that fills the space. In this project, aether becomes a metaphor for computational space, filled with creatures born from the invisible medium of computation.

2. Ecosystem Structure
The world of Aetherfauna contains:
- 4 aquatic species,
- 3 aerial species,
- 5 terrestrial species,
- 1 hybrid specie capable of surviving in any environment.
Each species are restricted to its natural habitat, for example air and terrestrial creatures cannot enter water. Only hybrids can move across all environments.

3. Temporal System 
The environment follows real-world clock time (GMT-5):
- sunrise: 7:00–8:00 
- sunset: 18:00–19:00

4. User Interaction
Users can click on each specie to:
- view its linguistic,
- listen to its generated sound,
- see its image,
- rename the species.

5. Image Generation
Because the world was fictional, lower-resolution training was sufficient for stylistic purposes, as it allowed faster generation (though CUDA processing remained slow). Different free datasets from Hugging Face were used to generate images with varying numbers of epochs and batch sizes (see image-generation.ipynb for more information). Batch size and dataset size directly influenced the image resolution, visual sharpness, and style consistency.

6. Sound Generation
Audio was generated using stabilityai/stable-audio-open-1.0 (from Hugging Face), which produces stereo audio at 44.1kHz sample rate and up to 47 seconds of duration. Differences in audio generation using the same model were perceived by changing num_inference_steps (more steps → cleaner audio), audio_end_in_s (output duration), and num_waveforms_per_prompt (generates multiple variations per prompt). Prompt engineering details are documented in sound_generation.ipynb.

7. Language System
The same prompt was tested using GPT-4.1 and GPT-5.1, applying the same temperatures and top_p, leading to the final choice of GPT-4.1 as a purely artistic decision. Prompt engineering details are documented in Language.ipynb.

8. On Image and Sound Quality
Image quality could be improved by:
- increasing epochs number,
- using larger datasets.

Sound quality could improve through:
- higher inference steps,
- prompt refinement.

9. Future Ideas
- allow users to generate creatures via an LLM-based entry point,
- make species react dynamically to background music,
- introduce environmental changes,
- allow users to create and archive species,
- change the species numbers over time.