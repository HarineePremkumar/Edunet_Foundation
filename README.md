# Edunet_Foundation
AICTE internship
# Stable Diffusion GUI in Google Colab

This repository contains a Python script that runs a Stable Diffusion image generation GUI within a Google Colab notebook. It leverages `tkinter` and `customtkinter` for the interface, `diffusers` for Stable Diffusion, and `pyvirtualdisplay` to handle display issues in the Colab environment.

## Prerequisites

* A Google Colab notebook.
* GPU runtime recommended for faster image generation.

## Installation

1.  Open a new Google Colab notebook.
2.  Copy and paste the following code into a cell and run it:

    ```python
    !apt-get install -y xvfb # Install Xvfb
    !pip install pyvirtualdisplay # Install pyvirtualdisplay
    !pip install diffusers transformers accelerate scipy safetensors customtkinter Pillow
    ```

## Usage

1.  Copy and paste the `stable_diffusion_gui.py` code into a new cell in your Colab notebook. Or copy the python code from the previous response.
2.  Run the cell.
3.  A GUI window will appear within the Colab output.
4.  Enter your prompt in the text box.
5.  Click the "Generate" button.
6.  The generated image will be displayed in the GUI, and a download prompt will appear, allowing you to save the image to your local machine.

## Code Explanation

* **Virtual Display:**
    * `xvfb` and `pyvirtualdisplay` are used to create a virtual display, allowing the GUI to run in the headless Colab environment.
* **Stable Diffusion:**
    * The script uses the `diffusers` library and the `"runwayml/stable-diffusion-v1-5"` model for image generation.
    * It automatically detects and uses GPU acceleration if available.
* **GUI:**
    * `tkinter` and `customtkinter` are used to create a simple GUI with a text input for the prompt and a label to display the generated image.
* **Image Handling:**
    * The generated PIL `Image` is converted to a `PhotoImage` for display in the Tkinter GUI.
    * The generated image is downloaded to the users local device.
* **Dependencies:**
    * The script requires `diffusers`, `transformers`, `accelerate`, `scipy`, `safetensors`, `customtkinter`, and `Pillow`.

## Notes

* Using a GPU runtime will significantly speed up image generation.
* The first time you run the script, it may take a few minutes to download the Stable Diffusion model.
* The virtual display is started and stopped within the python code, so it will not cause issues with other colab tasks.
* If you encounter any issues with the GUI, make sure you have installed all the required libraries and that your Colab runtime is set to GPU.
* The line `lmain.image = img` is crucial. Without it, the image can be garbage collected and not displayed.

## Contributing

Feel free to contribute to this project by submitting pull requests or opening issues.
