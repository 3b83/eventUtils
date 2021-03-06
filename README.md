# eventUtils
Event-based vision utility scripts.
* **preprocess.py:** Preprocessing of frames. Consists of resizing, downsampling and cropping, all in batches.
* **bag2hdf5.py:** Converts a .rosbag file containing events into a .hdf5. [MVSEC dataset](https://daniilidis-group.github.io/mvsec/) is taken as a guideline for the data organization.
* **bag2img.py:** Extracts image_raw data from a rosbag file.
* **img2hdf5.py:** Writes grayscale image data read from a directory into an existing hdf5 file.
* **flow2hdf5.py:** Writes .flo files read from a directory into a new hdf5 file, with their corresponding timestamps to the output of bag2hdf5.py.
* **metrics.py** Includes some optical flow evaluation metrics.
* **bin_events.py** Using count_data output of [Spike-FlowNet](https://github.com/chan8972/Spike-FlowNet), generates accumulated binary event images.
* **auto.bash:** Runs all necessary scripts for:
    * Pre-processing (resizing, downsampling etc.) high framerate images and their flow files
    * Generating events in .rosbag format via [ESIM](https://github.com/uzh-rpg/rpg_esim) using processed high framerate images & flows 
    * Converting .rosbag dataset into .hdf5, taking [MVSEC dataset](https://daniilidis-group.github.io/mvsec/) as a guideline
    * Split encoding of data in hdf5 file (part of [Spike-FlowNet](https://github.com/chan8972/Spike-FlowNet))
        * Before running auto.bash, roscore should be run beforehand, and paths should be changed accordingly.
