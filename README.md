# ml-based-document-classifier
Liabraries needed: pdf2image, PyPDF2, os, numpy, subprocess, csv, sklearn, cv2, tensorflow

# Files to download
retrained_graph.pb
retrained_labels.txt
count_ops.py
evaluate.py
graph_pb2tb.py
__init__.py
label_image.py
retrain.py
quantize_graph.py
show_image.py
net_tester.py

# To retrain the model
> python scripts/retrain.py  --image_dir ./tf_files/train --output_graph=tf_files/retrained_graph.pb --output_labels=tf_files/retrained_labels.txt --how_many_training_steps=1000
Adjust the training steps accordingly.

# Testing on data
- To test it on unlabelled data (single file)
> python3 scripts/label_image.py --graph=tf_files/retrained_graph.pb --image=test.png
- To test it on labelled data and drawing statistics (should have a .csv file with labels and file name)
> python3 tester.py
- Adjust src_label, src_graph, folder_name, csv_file file locations
- The tester.py returns the classification report and the confusion matrix.
