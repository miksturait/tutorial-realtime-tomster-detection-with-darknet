# Tomster recognition with Darknet

![Tomster image](http://macdown.uranusjr.com/static/images/logo-160.png)

## 1. Collecting the data
  - images/photos
  - movie
  ```
  ffmpeg -i INPUT -filter:v fps=FRAMES/SECONDS %02d.jpg
  ```

## 2. Scaling
  500px x 500px MAX
  ```
  convert -resize 25% *.jpg
  ```

## 3. Labeling
  https://github.com/puzzledqs/BBox-Label-Tool

## 4. Convert to VOC format
  - script here

## 5. Spliting dataset
  10% testing data
  - script here

## 6. Create input file
  - script here

## 7. Configuration
  - tomster.names(labels/classes)
  ```
  tomster
  ```
  - tomster.data(sources)
  ```
  classes = 1
  train = /abs/path/to/train.txt
  valid = /abs/path/to/test.txt
  names = /abs/path/to/*.names
  backup = backup/
  ```
  - tomster.cfg(hyperparams)
  ```
  soon
  ```

## 8. Training
  Minimize AVG loss > 0.2
  ```
  darknet detector train path/to/*.data path/to/*.cfg path/to/*.weights >> training.log
  ```

## 9. Testing
  ```
  darknet detector demo path/to/*.data path/to/*.cfg path/to/*.weights
  ```
  optional:
  ```
  thresh 0.X
  ```
