# OCT Segmentation

Open [`Code/reproduce.ipynb`](Code/reproduce.ipynb) and run all cells in order:

1. **Data preparation:** Load the training, validation, and test images and masks.
2. **Y-Net training:** Train the segmentation model.
3. **Test inference:** Predict segmentation masks for the test images.
4. **Image-level metrics:** Calculate Dice, thickness/MAE, and SRF area for new predictions and the saved 12-case comparison.
5. **Display:** Show grouped summaries and image-level results.

Y-Net learns pixel labels from the training images and predicts a segmentation mask for each test OCT. Weights, predictions, and results stay in memory; the notebook does not save a checkpoint or export tables. Run from the top after restarting the kernel.

Place the dataset under `Data/`. The notebook searches for `ynet_model.py` in the configured local model folders; edit `MODEL_CODE_CANDIDATES` in the setup cell if your copy is elsewhere. The OCT data are not included.

## Reference and license

The retinal OCT Y-Net paper is Farshad et al., [“Y-Net: A Spatiospectral Network for Retinal OCT Segmentation,” MICCAI 2022](https://doi.org/10.1007/978-3-031-16434-7_56) — not CVPR. The [official implementation](https://github.com/azadef/ynet) is marked [Apache-2.0](https://github.com/azadef/ynet/blob/master/LICENSE).

The notebook loads a separate local `ynet_model.py`, whose license is not included in the inspected folder. Confirm that file's redistribution rights before publishing it. Confirm data-sharing permission before publishing OCT images or masks.
