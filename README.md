# OCT Segmentation

Open [`Code/reproduce.ipynb`](Code/reproduce.ipynb) and run all cells in order:

1. **Data preparation:** Load the training, validation, and test images and masks.
2. **Y-Net training:** Train the segmentation model.
3. **Test inference:** Predict segmentation masks for the test images.
4. **Image-level metrics:** Calculate Dice, thickness/MAE, and SRF area for new predictions and the saved 12-case comparison.
5. **Display:** Show grouped summaries and image-level results.

The notebook defines Y-Net internally, learns pixel labels from the training images, and predicts a segmentation mask for each test OCT. No project-specific `.py` module is imported. Weights, predictions, and results stay in memory; the notebook does not save a checkpoint or export tables. The committed notebook includes the latest run's displayed outputs.

Place the dataset under `Data/`. OCT data are not included. Python libraries such as PyTorch, NumPy, SciPy, pandas, Pillow, and IPython are still required.

Thickness is reported over all 512 columns and the centered 3 mm range (columns `[136, 376)`).

## Reference and license

The retinal OCT Y-Net paper is Farshad et al., [“Y-Net: A Spatiospectral Network for Retinal OCT Segmentation,” MICCAI 2022](https://doi.org/10.1007/978-3-031-16434-7_56) — not CVPR. The [official implementation](https://github.com/azadef/ynet) is marked [Apache-2.0](https://github.com/azadef/ynet/blob/master/LICENSE).

The embedded model code follows the [official Y-Net implementation](https://github.com/azadef/ynet) and uses FFC code from [pkumivision/FFC](https://github.com/pkumivision/FFC); both repositories are marked Apache-2.0. This repository includes the Apache-2.0 license. Confirm data-sharing permission before publishing OCT images or masks.
