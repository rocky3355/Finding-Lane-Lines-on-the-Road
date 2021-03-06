# Finding Lane Lines on the Road

This project aims to perform a simple line detection on a stream of images. Those lines will be drawn onto the input stream and then written to a new video file. In this repository, 'Main.ipynp' contains all the code, 'test.mp4' is the input video and 'test_with_lines.mp4' is the output with lines.

Most of the image processing part is taken from the previous lectures. The parameters have been adjusted and the color filtering now happens also for yellow lines. Filtering all the lines that were detected using the OpenCV Hough algorithm is the only part that is completely new. Currently, the algorithm searches for similar lines, until only two remain (the two lanes). Until this is achieved, for each pair of similar lines, the shorter one gets discarded. A better approach would be some kind of merging them instead of filtering and discarding them. But I felt that this was a bit too much for the first project, which aimed only for a simple line detection.

Unfortunately, I was not able to detect the yellow line when it was rather dark (i.e. when in shadow). The color filtering discarded the dark parts of the line and I was not sure how to handle this. I thought about brightening up the whole image, but I am pretty sure that would have led to more parts of the image passing the white color filtering, which is not desired.
