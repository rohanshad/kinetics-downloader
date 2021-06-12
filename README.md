# kinetics-downloader

Simple tool to download videos from [kinetics dataset](https://deepmind.com/research/open-source/open-source-datasets/kinetics/).

Also have functionality to trim downloaded videos to the length of action. To support trimming, ffmpeg should be installed and added to environment variable PATH.

## Usage
Install requirements first
```
pip install -r requirements.txt
```

You should download and unzip csv files with links to videos. You can download such files [here](https://deepmind.com/research/open-source/open-source-datasets/kinetics/).

### Downloading
```
cd kinetics-downloader
python download.py /path/to/kinetic_train.csv /path/to/videos/
```

### Downloading and trimming
```
cd kinetics-downloader
python download.py /path/to/kinetic_train.csv /path/to/videos/ --trim
```

### Parallel processing
One can run downloading and trimming in several processes. To do so, just add flag --num-jobs with number of jobs running in parallel.
For example:
```
cd kinetics-downloader
python download.py /path/to/kinetic_train.csv /path/to/videos/ --trim --num-jobs 10
```

### Additional Notes

This requires ffmpeg to work, on clusters like Sherlock remember to load the relevant modules before starting the script

```
module load system ffmpeg
```
