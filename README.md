# Interior Object Recommendation System in Latent Space
## Team Members:
Bill Chen (gc2677)
Nana Takada (nt2483)

## Project Overview:
The goal of this project is to develop a recommendation system that suggests interior objects based on room images, utilizing a style-matching algorithm within a latent space. The system extracts style information from images of rooms and objects and performs style matching in an unsupervised manner. The challenge is to extract latent space information that reflects the room's style without relying on labeled datasets.

Key Objectives:
Build a recommendation system based on latent space embeddings.
Utilize unsupervised learning techniques such as Autoencoders and VAE.
Test different methods to project room and object images into a shared latent space.
Achieve a higher accuracy in recommending objects that match the style of rooms.
Dataset:
We used two primary datasets:

Room Images Dataset: Collected from sources like iStock, LSUN, and Flickr, featuring various room styles such as Japanese, Scandinavian, and Modern rooms.
Paired Room-Object Dataset: Scraped from MADE, an interior objects marketplace. This dataset includes room images and corresponding objects, allowing the model to learn style-matching relationships.
You can access the datasets via the following links:

Room Images Dataset
Paired Room-Object Dataset
Methodologies Tested:
We experimented with several methods to extract the style embeddings and match room images to corresponding objects:

Autoencoders: Built to create embeddings for images, but found that rooms and objects were projected into different latent spaces, affecting recommendation accuracy.
Variational Autoencoders (VAE): Applied to regularize the latent space, but the results were similar to the basic autoencoder.
VGG19 + Random Projection: Extracted style features using VGG19 and used random projection to reduce dimensionality. This method achieved a recommendation accuracy of 29.8%.
Room-to-Room & Object-to-Object Matching: Used KNN to find closest matches for rooms and their corresponding objects. Achieved a top-10 recommendation accuracy of 33.5%.
Dense Layer Mapping: Added dense layers to map room embeddings to object embeddings, aligning them in a shared latent space.
Results:
The most effective method was using the VGG19 style extractor with random projection, combined with room-to-room and object-to-object matching. This approach achieved an accuracy of 33.5% in top-10 recommendations. The Dense Layer model also performed well, with a recommendation accuracy of 30%.

Future Work:
Implement contrastive learning to improve the alignment of room and object embeddings in the latent space.
Explore more advanced methods to regularize the style space and improve clustering of different room styles.
Project Files:
Main Notebook: The core implementation of Autoencoders, VAEs, and the VGG19-based style extractor.
Experiment Notebook: Contains additional experiments on various embeddings and hyperparameter tuning.
Presentation: Available on YouTube: Project Presentation.
Libraries and Tools:
TensorFlow & Keras
Scikit-learn for random projections
BeautifulSoup for web scraping
Matplotlib for visualizations
How to Run the Project:
Clone the project and download the necessary datasets from the links provided above.
Run the Jupyter notebook One_main.ipynb, which contains the full implementation of the project.
Modify the dataset paths as needed and ensure that TensorFlow and other required libraries are installed.
References:
Variational Autoencoder Tutorial: https://blog.keras.io/building-autoencoders-in-keras.html
Johnson-Lindenstrauss Lemma: https://cseweb.ucsd.edu/~dasgupta/papers/jl.pdf
Multi-Modal Joint Embedding for Fashion Product Retrieval: http://www.iri.upc.edu/files/scidoc/1904-Multi-Modal-Joint-Embedding-for-Fashion-Product-Retrieval.pdf
