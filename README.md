```markdown

## Installation

Ensure you have Python 3 installed.

Clone the repository 

Install the required packages:

```
pip install git+https://github.com/huggingface/diffusers
pip install -q transformers accelerate controlnet-aux
```

## Usage

### Stable Diffusion + ControlNet + Inpaint + IP Adapter

Set the following variables to the paths of the images you want to use in the `sd1_5.py` script:

```python
init_image_path = load_image("./test/model.png")
mask_image = load_image("./test/mask.png")
ip_image = load_image("./test/garment.png") 
prompt = "a woman wearing a dress, best quality, high quality"
```

Note: The mask image should be a black and white image with the same dimensions as the init image. The white pixels in the mask image will be replaced. The head, hands, and feet should be black in the mask image. Currently, we're working on a script to automatically generate the mask image from the init image.

Then run the script:

```
python sd1_5.py
```

The script will process the inputs and generate an output image of the model wearing the specified garment.
```
