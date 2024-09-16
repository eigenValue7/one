# Interior Object Recommendation System in Latent Space

## Team Members:
- Nana Takada
- Bill Chen

## Project Overview:
This project aims to develop a recommendation system that suggests interior objects based on room images, leveraging a style-matching algorithm in latent space. The system extracts style information from images of rooms and objects and performs style matching in an unsupervised manner. The main challenge is to extract latent space information that reflects the room's style without relying on labeled datasets.

### Key Objectives:
- Build a recommendation system based on latent space embeddings.
- Utilize unsupervised learning techniques such as Autoencoders and VAE.
- Test different methods to project room and object images into a shared latent space.
- Achieve higher accuracy in recommending objects that match the style of rooms.

## Dataset:
Two primary datasets were used in this project:
1. **Room Images Dataset**: Collected from sources like iStock, LSUN, and Flickr, featuring various room styles (e.g., Japanese, Scandinavian, Modern).
2. **Paired Room-Object Dataset**: Scraped from the interior object marketplace MADE. This dataset includes room images paired with corresponding objects, allowing the model to learn style-matching relationships.

## Methodologies:
The following methods were tested to extract style embeddings and match room images to corresponding objects:

1. **Autoencoders**: Created embeddings for images, but rooms and objects were projected into different latent spaces.
2. **Variational Autoencoders (VAE)**: Applied to regularize the latent space, producing similar results to the Autoencoder.
3. **VGG19 + Random Projection**: Used VGG19 to extract style features and random projection to reduce dimensionality, achieving a recommendation accuracy of 29.8%.
4. **Room-to-Room & Object-to-Object Matching**: Used KNN to match rooms with corresponding objects, achieving a top-10 recommendation accuracy of 33.5%.
5. **Dense Layer Mapping**: Added dense layers to map room embeddings to object embeddings, aligning them in a shared latent space.

## Results:
The most effective method involved using the **VGG19 style extractor** with **Random Projection** combined with room-to-room and object-to-object matching, achieving a top-10 recommendation accuracy of 33.5%. The dense layer model also performed well, with a recommendation accuracy of 30%.

## Future Work:
- Implement **contrastive learning** to better align room and object embeddings.
- Explore more advanced regularization techniques to improve clustering of different room styles.

## Project Files:
1. **Main Notebook**: Contains the core implementation of Autoencoders, VAEs, and the VGG19-based style extractor.
2. **Experiment Notebook**: Contains additional experiments on various embeddings and hyperparameter tuning.
3. **Presentation**: Available on YouTube: [Project Presentation](https://www.youtube.com/watch?v=NFOlRiD8pnY&feature=youtu.be).

## Libraries and Tools:
- TensorFlow & Keras
- Scikit-learn for random projections
- BeautifulSoup for web scraping
- Matplotlib for visualizations

## How to Run the Project:
1. Clone the project and download the necessary datasets from the links provided above.
2. Run the Jupyter notebook `One_main.ipynb`, which contains the full implementation of the project.
3. Modify the dataset paths as needed and ensure that TensorFlow and other required libraries are installed.

## References:
- Variational Autoencoder Tutorial: https://blog.keras.io/building-autoencoders-in-keras.html
- Johnson-Lindenstrauss Lemma: https://cseweb.ucsd.edu/~dasgupta/papers/jl.pdf
- Multi-Modal Joint Embedding for Fashion Product Retrieval: http://www.iri.upc.edu/files/scidoc/1904-Multi-Modal-Joint-Embedding-for-Fashion-Product-Retrieval.pdf
