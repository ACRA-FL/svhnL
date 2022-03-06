Usage
*****

.. _installation:

Installation
============

To use schnL, first install it using pip:

.. code-block:: console

   (.venv) $ pip install svhnl

Functionalities
===============

Dataset Download & extract
--------------------------

To download SVHN dataset [train, test or extra] from `the original svhn dataset <http://ufldl.stanford.edu/housenumbers/>`
and extract the downloaded .tar.gz file. you can use ``svhnl.download()`` function:

.. autofunction:: svhnl.download

Code Example:

>>>> import svhnl
>>>> train_dt_filename = svhnl.download(extract=False)
'./data/train.tar.gz'
>>>> test_dt_folder_path = svhnl.download(dataset_type='test', save_path='../dataset/svhn', extract=True, force=False, del_zip=False)
'../dataset/svhn/test'

For further instruction follow to API page; :ref:`download`

Convert Annotation file into JSON
---------------------------------

To read the .mat annotation file provided with `the original svhn dataset <http://ufldl.stanford.edu/housenumbers/>`
and generate more flexible and light-weight .json annotation file.

.. autofunction:: svhnl.ann_to_json

Code Example:

>>>> import svhnl
>>>> svhnl.ann_to_json(file_path='./train/digitStruct.mat', save_path='./svhn_ann.json', bbox_type='normalize')

The function supports both Normalilzed {top, left, width, height} format and KITTI {xmin, ymin, xmax, ymax} format.
For further instruction follow to API page; :ref:`ann_to_json`


Convert Annotation file into csv
--------------------------------

To read the .mat annotation file provided with `the original svhn dataset <http://ufldl.stanford.edu/housenumbers/>`
and generate more operatable and light-weight .csv annotation file.

.. autofunction:: svhnl.ann_to_csv

Code Example:

>>>> import svhnl
>>>> svhnl.ann_to_csv(file_path='./train/digitStruct.mat', save_path='./svhn_ann.csv', bbox_type='normalize')

The function supports both Normalilzed {top, left, width, height} format and KITTI {xmin, ymin, xmax, ymax} format.
For further instruction follow to API page; :ref:`ann_to_csv`


Generate MDR dataset
--------------------

Easy use of the SVHN dataset in any MDR task [defined number of digit recognition or without restriction object detection]
with digit cropping, RGB to Gray-scale conversion and number of digit limiting and etc.

.. autofunction:: svhnl.gen_dataset

Code Example:

>>>> import svhnl
>>>> image_np, ann_dict = svhnl.gen_dataset(image_path='../data/svhn/train', mat_path='../data/svhn/train/digitStruct.mat')

For further instruction follow to API page; :ref:`gen_dataset`

