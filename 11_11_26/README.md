## Goal of today:
- See how data (a photo, a face, the temperature along a metal rod) can be thought of as a single point in a very high-dimensional space, and why such data can be compressed
- Learn the singular value decomposition (SVD), which finds the best low-dimensional subspace for a cloud of data points, and principal component analysis (PCA), which is the SVD of mean-centered data
- See them in action: compress a photo, describe each face with a few dozen numbers instead of 32,256 pixels, and describe the temperature of a heated metal rod with a handful of numbers
- Leave with a toolbox of NumPy commands for using the SVD and PCA on your own data

**Reading:** Chapter 1 of the book (Singular Value Decomposition).

## Getting started
1. Open VS Code with the `DataDrivenGroup` folder, open a terminal (**Terminal → New Terminal**), and run:
   ```
   git pull
   ```
1. Check that the `DATA` folder at the top of the repo contains `dog.jpg` and `allFaces.mat`. (`allFaces.mat` is 57 MB, so the pull may take a minute.)
1. Open the `11_11_26` folder and make your own copy of `svd_pca.ipynb` (right-click it, choose **Copy**, then right-click and choose **Paste**). Keep your copy in the `11_11_26` folder, so it can find the `DATA` folder.
1. Open your copy, select the same kernel as last time, and run the **Setup** cell. There's nothing new to install: NumPy, SciPy and Matplotlib from our first session are all you need.

## The notebook
We'll go through it together on the screen, and you're welcome to run the cells along with us:
1. **Data as vectors:** a photo as a matrix of numbers, and as a single point in a space with 3 million dimensions
1. **The goal of compression:** replacing points in the plane by their positions along the best line
1. **The SVD and PCA:** the SVD finds the best subspaces through the origin, PCA the best ones through the data's mean
1. **The mathematics:** the key theorems, with proofs in **Proof** dropdowns (click to expand), followed by a **toolbox** with every command you need
1. **Applications:**
   - compressing a photo, and how many times smaller it gets
   - eigenfaces: describing each face by a few coordinates
   - "hot rods": temperature data from a small physics problem

## Troubleshooting
- **`FileNotFoundError` mentioning `../DATA`:** your notebook isn't in the `11_11_26` folder, or the `DATA` folder is missing. Move your copy into `11_11_26` and run `git pull`.
- **The eigenfaces step takes forever, or the notebook crashes:** your laptop may be low on memory. Close other programs, set `N_TRAIN_PEOPLE = 20` at the top of the cell that computes the eigenfaces, and run it again.
- Still stuck? Ask one of us!
