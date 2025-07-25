# Image Captioning with CLIP



This project leverages OpenAI's Contrastive Language-Image Pre-training (CLIP) model to perform image understanding and caption matching. Given an image and a set of candidate captions, the system identifies and ranks the captions that best describe the image based on their semantic similarity.



## Features



  * **Image Preprocessing**: Handles image loading and prepares them for the CLIP model.

  * **Image Understanding**: Utilizes CLIP to generate robust image embeddings.

  * **Caption Matching**: Calculates cosine similarity between image embeddings and text embeddings of candidate captions to find the best matches.

  * **Top Caption Retrieval**: Ranks and returns the most relevant captions along with their similarity scores.



## How it Works



The core of this project relies on the CLIP model. Here's a simplified breakdown of the process:



1.  **Load and Preprocess Image**: An input image is loaded and transformed into a format suitable for the CLIP model using `CLIPProcessor`.

2.  **Generate Image Embeddings**: The preprocessed image is fed into the CLIP model to produce a numerical representation (embedding) that captures its visual semantics.

3.  **Generate Text Embeddings**: Similarly, all candidate captions are tokenized and processed by the CLIP model to generate their respective text embeddings.

4.  **Calculate Similarity**: The cosine similarity between the image embedding and each text embedding is calculated. Cosine similarity measures the angle between two vectors, indicating how similar they are in direction. A higher similarity score means the caption is a better match for the image.

5.  **Rank and Present**: The captions are then ranked based on their similarity scores, with the highest-scoring captions being considered the best matches.



## Setup



### Prerequisites



  * Python 3.7+

  * `pip` (Python package installer)










## Usage



### Preparing Your Data



  * **Image**: Place your image file (e.g., `606e9263b79c6cc871c3fcaf40ec44d4.jpg`) in the project directory.



  * **Captions**: Create a JSON file (e.g., `captions.json`) containing your candidate captions. The format should be:



    

    {

      "captions": [

        "A black cat sitting on a couch.",

        "A dog running in a park.",

        "A person reading a book.",

        "A cat lounging on furniture.",

        "An animal resting indoors."

      ]

    }

    



### Running the Script



1.  Make sure your image file and JSON file are in the same directory as your Python script.



2.  Update the `filename` variable in the script to point to your JSON file (e.g., `filename = "captions.json"`).



3.  Update the image path in the `image_captioning` function call (e.g., `image_captioning("your_image.jpg", candidate_captions)`).



4.  Run the script:



   

    python image_caption.py

   




### Example Output



```

Top 5 Best Captions:

1. POV: i’m your Uber drive (Similarity: 0.3042)

2. omw (Similarity: 0.2726)

3. GPS said it’s my turn (Similarity: 0.2664)

4. they see me rollin (Similarity: 0.2642)

5. drive fast, don’t crash (Similarity: 0.2620)

```



## Project Structure



  * `Image_caption.py`: The main Python script containing the image captioning logic.

  * `example.jpg`: Example image file 

  * `captions.json`: Example JSON file containing candidate captions.



## Contributing



Feel free to fork this repository, open issues, or submit pull requests to improve the project.



-----

